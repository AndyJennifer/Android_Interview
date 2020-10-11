# Lock 为什么要在 finally 中释放锁

我们在使用 Lock 锁时，基本范式为如下代码：

```java
    lock.lock();
    try{
    ......
    }finally{
        lock.unlock();
    }
```

我们采用如上方式来实现 Lock 加解锁的原因有如下两点：

## 第一点

如果在 lock 方法与 try 代码块之间的方法调用抛出异常，那么无法解锁，造成其它线程无法成功获取锁。也就是如下这样：

```java
 lock.lock();
    //doSomeThting.... 抛出异常。
    //👇下面的代码都不会执行
    try{
    .....
    }finally{
        lock.unlock();
    }
```

因为当程序抛出异常后，那么异常后的代码就不会执行了，也就是说，如果某个线程持有了锁，那么其他线程就永远都无法成功获取到锁。因为获取锁的线程就没有释放过锁。

## 第二点

如果 lock 方法在 try 代码块之内，可能由于其它方法抛出异常，导致在 finally 代码块中，unlock 对未加锁的对象解锁。

```java
    try{
    //doSomeThting.... 抛出异常。
    //👇下面的代码都不会执行
    lock.lock();
    .....
    }finally{
        lock.unlock();
    }
```

在上述代码中，Lock 会调用 AQS 的 tryRelease 方法（取决于具体实现类），抛出 IllegalMonitorStateException 异常。在 Lock 对象的 lock方法实现中可能抛出 unchecked 异常。而在使用尝试机制来获取锁的方式中，比如 tryLock()，在进入业务代码块之前，必须先判断当前线程是否持有锁。
