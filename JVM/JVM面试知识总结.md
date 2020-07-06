# JVM 面试知识总结

## JVM 内存模型

- JVM 有哪些内存区域
- Java 的内存模型是什么
- 请你谈谈 OOM 的认识
- 你都有哪些手段用来排除内存溢出

## 垃圾回收场景

### 垃圾回收算法

- Java 垃圾回收时如何确定垃圾，什么是 GC Roots
- 能够找到 Reference Chain 的对象，就一定会存活吗
- 强引用，软引用，弱引用，虚引用 是什么，及其回收时机
- GC 垃圾回收算法有哪些
- Minnor GC、Major GC、Full Gc 都什么时候发生

### 垃圾收集器

- GC 垃圾回收器有哪些，这些垃圾器有什么优缺点

## 类加载机制

### 类加载器

- Java 类加载器有哪几类
- 如何自定义类加载器

### 双亲委派模型

- Java 的双亲委托机制是什么
- Java 的双亲委托机制的破坏
- 我们能通过一定的手段，覆盖 HashMap 类的实现吗？(Java endorsed，非java.lang包下的类，如果非要，需要自定义类加载器)
- 如何加载一个远程的 .class 文件？怎么加密 .class 文件
- `<cinit>` 和 `<init>` 方法的区别(类初始化与对象初始化)

### 类加载声明周期

- Java 类加载过程分为及几个阶段

## Android 小伙伴可能会需要了解的知识

- DVM 以及 ART 是如何对 JVM 进行优化的

https://www.kancloud.cn/alex_wsc/androids/473611
https://www.jianshu.com/p/33968db4b08d

https://www.cnblogs.com/renhui/p/11716975.html multieDex 优化的细节
  