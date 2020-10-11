# 单例模式的双重检查锁模式为什么必须加volatile

## Double Check Lock(DCL) 实现单例

DCL 方式实现单例模式的优点是既能够在需要时才初始化单例，又能够保证线程安全，且单例对象初始化后调用 getInstance 不进行同步锁。代码如下所示：

```java
public class Singleton {
     /**
     * 构造私有函数
     */
    private Singleton() {
    }
    //第一层锁：保证变量可见性
    private volatile static Singleton instance = null;
    /**
     * 公有的静态函数，对外暴露获取单例对象的接口
     */
    public static synchronized Singleton getInstance() {
        if (instance == null) {//第一次判空：无需每次都加锁，提高性能
            synchronized (Singleton.class){//第二层锁：保证线程同步
                if (instance == null) {//第二次判空:避免多线程同时执行getInstance()产生多个single对象
                    instance = new Singleton();
                }
            }
        }
        return instance;
    }
}
```

getInstance 方法中对 instance 进行了两次判空：第一次判断主要是为了避免不必要的同步，第二层是为了在 null 的情况下创建实例。

假设线程 A执行到 instance = new Singleton(); 语句，这里看起来是一句代码，但实际上并不是一个原子操作，这句代码最终被编译成多条汇编指令，它大致做了3件事：

1. 给 Singleton 的实例分配内存
2. 调用 Singleton 的构造函数，初始化成员字段
3. 将 instance 对象指向分配的内存空间（此时 instance 就不是 null 了）

由于 Java 编译器允许处理器乱序执行，以及 JDK 1.5 之前JMM(Java Memory Model 即Java 内存模型）中 Cache、寄存器到主内存回写顺序的规定，上面的第（2）（3）顺序是无法保证的。也就是说，执行顺序可能是 1-2-3 也可能是 1-3-2。如果是后者，并且在（3）执行完毕、（2）为执行之前，被切换到线程 B 上，这时候 instance 因为已经在线程 A 内执行过了第三点，instance 已经是非空了，所以 B 线程直接取走 instance，在使用时就会出错，这就是 DCL 失效问题。

在 JDK 1.5 之后，SUN 官方已经注意到这种问题，调整了 JVM ，具体化了 volatile 关键字，如果是1.5 或之后的巴安阿伯，只需要将 sInstance 的定义改成 private volatile static Singleton sInstance = null 就可以保证 sInstance 对象每次都是从主内存中读取，就可以使用 DCL 的写法来完成单例模式。(内部原理，内存屏障防止CPU指令重排序)
