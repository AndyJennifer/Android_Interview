---
title: 'BAT大厂Android面试知识点,图文篇'
tags:
  - 面试
categories:
  - 面试
---

### Java基础知识点

#### Jvm相关

- Java内存结构及分区
- Java对象的创建、存储及访问
- Java判断对象是否存活及垃圾回收算法（GC）
- Jvm中的常见的垃圾回收器
- Java类加载过程
- Java类加载器（双亲委派模型）

推荐阅读：

1. 《深入理解Java虚拟机JVM高级特性及最佳实践》 第二章 Java内存区域与内存溢出异常
2. 《深入理解Java虚拟机JVM高级特性及最佳实践》 第三章 垃圾收集器与内存分配策略
3. 《深入理解Java虚拟机JVM高级特性及最佳实践》 第六章 类文件结构
4. 《深入理解Java虚拟机JVM高级特性及最佳实践》 第七章 虚拟机类加载机制
5. 《Java虚拟机规范 JAVA SE 8版》

#### 集合相关

- ArrayList分析
- LinkedList分析
- HashMap分析
- HashTable分析
- LinkedHashMap分析
- HashSet分析
- LinkedHashSet分析
- ArrayMap、SparseMap、与HashMap的对比
- ConcurrentHashMap分析

推荐阅读:

1. 如果大家不嫌弃，可以看看我的-->[ArrayList分析](https://juejin.im/post/5acf49316fb9a028e33bd6d7)
2. 如果大家不嫌弃，可以看看我的-->[LinkedList分析](https://juejin.im/post/5acf49606fb9a028cd457c8c)
3. 如果大家不嫌弃，可以看看我的-->[哈希表初识](https://juejin.im/post/5b0e99f9518825155401feca)
4. [彻头彻尾理解 HashTable](https://blog.csdn.net/justloveyou_/article/details/72862373)
5. [美团技术团队-Java8系列之重新认识HashMap](https://mp.weixin.qq.com/s?__biz=MjM5NjQ5MTI5OA==&mid=504261609&idx=1&sn=cdc762fe7c9050e7e9a2554d8c3337a4&mpshare=1&scene=23&srcid=0217AGtnvS7RimagXJQkmTXc#rd)
6. [Map 综述（二）：彻头彻尾理解 LinkedHashMap](https://blog.csdn.net/justloveyou_/article/details/71713781)
7. 《Java并发编程的艺术》第六章6.1节CocurrrentHashMap（基于JDK 1.6，1.7分析的）实现原理及使用
8. [深入浅出ConcurrentHashMap1.8](https://www.jianshu.com/p/c0642afe03e0)

#### 并发相关

- Java内存模型
- volatile原理
- Synchronized的原理
- AQS原理
- Condition原理
- ReentrantLock 原理
- 公平锁与非公平锁
- ReentrantReadWriteLock原理

推荐阅读：

1. 《Java并发编程的艺术》第二章 Java并发机制的底层实现原理
2. 《Java并发编程的艺术》第三章 内存模型
3. 《Java并发编程的艺术》第五章 Java中的锁
4. [Java并发编程之Java内存模型](https://juejin.im/post/5ba668b4e51d450e686787cc)
5. [Java并发编程之Java CAS操作](https://juejin.im/post/5ba66a7ef265da0abb1435ae)
6. [Java并发编程之Volatile](https://juejin.im/post/5ba66c7be51d450e576703f0)
7. [Java并发编程之synchronized](https://juejin.im/post/5ba66e42f265da0aa664c19d)
8. [Java并发编程之锁机制之引导篇](https://juejin.im/post/5bbf040df265da0ac446ccab)
9. [Java并发编程之锁机制之Lock接口](https://juejin.im/post/5bbf0498f265da0aba70d9a7)
10. [Java并发编程之锁机制之AQS(AbstractQueuedSynchronizer)](https://juejin.im/post/5bbf04d5f265da0ad947f05b)
11. [Java并发编程之锁机制之LockSupport工具](https://juejin.im/post/5bdc1142e51d45052c6fede7)
12. [Java并发编程之锁机制之Condition接口](https://juejin.im/post/5be94044f265da61542d27d8)
13. [Java并发编程之锁机制之重入锁](https://juejin.im/post/5bf791ec51882512d444e3d2)
14. [Java并发编程之锁机制之读写锁](https://juejin.im/post/5c18da5c5188254caf18a58f)

#### 线程相关

- 线程的启动和终止
- 线程间通信
- 等待/通知机制

推荐阅读：

《Java并发编程的艺术》第四章 Java并发编程基础

#### 线程池相关

- 使用线程池的原因
- 线程池内部原理
- 线程池中的几种重要的参数及流程说明
- 线程池中几种常见的工作队列
- 几种常见的线程池及使用场景。

推荐阅读：
《Java并发编程的艺术》第九章 Java中的线程池

#### IO相关

- IO相关面试问题-Socket
- IO相关面试问题-BIO／NIO

推荐阅读：

1. [NIO相关基础篇一](https://blog.csdn.net/lirenzuo/article/details/78764696)
1. [NIO相关基础篇二](https://blog.csdn.net/lirenzuo/article/details/78838717)
1. [NIO相关基础篇三](https://blog.csdn.net/lirenzuo/article/details/78898430)
1. 《UNIX 网络编程，卷1：套接字联网API 第三版》第六章 I/O复用：select和poll
1. 《深入理解Java虚拟机JVM高级特性及最佳实践》 第二章 Java内存区域与内存溢出异常 2.7节 直接内存介绍

### Android基础知识点

#### Activity相关

- 典型状况下的生命周期
- 异常情况下的生命周期
- 异常情况下的数据保存
- 各种情况下跳转到某个Activity时目标Activity及当前Activity的生命周期
- Activity的启动模式及应用场景
- 进程和应用生命周期

推荐阅读：

1. 《Android开发艺术探索》 第一章 Activity的生命周期和启动模式
1. 《Android开发艺术探索》 第九章 9.2节Activity的工作过程
1. [Google-进程和应用生命周期](https://developer.android.google.cn/guide/components/activities/process-lifecycle)
1. [Google-任务和返回栈](https://developer.android.google.cn/guide/components/activities/tasks-and-back-stack)

#### Service相关

- Service的定义及作用
- Service两种启动方式  startService、 bindService 区别及生命周期
- Service绑定服务的三种实现方式，扩展Binder类、使用Messenger、使用AIDL
- 关于启动服务与绑定服务间的转换问题 先绑定服务后启动服务、先启动服务后绑定服务
- 服务Service与线程Thread的区别
- Android 5.0以上的隐式启动问题及其解决方案
- 如何保证服务不被杀死
- IntentService的使用及原理

推荐阅读：

1. 《Android开发艺术探索》 第九章 9.3节Service的工作过程
1. [关于Android Service真正的完全详解，你需要知道的一切](https://blog.csdn.net/javazejian/article/details/52709857)
1. [Android 多线程之IntentService 完全详解](https://blog.csdn.net/javazejian/article/details/52426425)
1. [Android 多线程之HandlerThread 完全详解](https://blog.csdn.net/javazejian/article/details/52426353)

#### BroadcastReceiver相关

- BroadcastReceiver定义及作用、应用场景
- BroadcastReceiver的注册方式，静态方式、动态方式
- BroadcastReceiver注册与取消的时机
- BroadcastReceiver的不同类型，普通广播，系统广播、有序广播、粘性广播、应用类广播

推荐阅读：

1. 《Android开发艺术探索》 第九章 9.4节BroadcastReceiver 的工作过程
1. [BroadcastReceiver史上最全面解析](https://www.jianshu.com/p/ca3d87a4cdf3)
1. [广播在7.0、8.0、9.0下的适配](https://developer.android.google.cn/guide/components/broadcasts)

#### Fragment相关

- Fragment生命周期
- Fragment的懒加载
- Fragment之间的通信
- FragmentPagerAdapter与FragmentStatePagerAdapter的区别
- 为什么不建议直接通过使用new Fragment的方式传入数据

推荐阅读：

1. [Fragment全解析系列（一）：那些年踩过的坑](https://www.jianshu.com/p/d9143a92ad94)
1. [Google-Fragment概览](https://developer.android.google.cn/guide/components/fragments)
1. [Google-与其他Fragment通信](https://developer.android.google.cn/training/basics/fragments/communicating)

#### 序列化相关

- 序列化与反序列化的定义及区别
- Serializable中serialVersionUID及transient关键字的作用
- 序列化：Parcelable和Serializable差异

推荐阅读：

1. [序列化与反序列化之Parcelable和Serializable浅析](https://blog.csdn.net/javazejian/article/details/52665164)
1. 《Android开发艺术探索》 第二章 IPC基础概念介绍

#### IPC相关

- 在Android中什么样的情况下会使用多进程模式，如何开启多进程
- Android为什么采用Binder做为IPC机制
- IPC常用方式 使用Bundle、使用文件共享、使用Messenger、使用AIDL、使用ContentProvider、使用Socket
- AIDL的语义
- AIDL如何创建
- AIDL生成Java文件详细分析

推荐阅读：

1. 《Android开发艺术探索》 第二章 IPC机制
1. 《深如理解LINUX内核 第三版涵盖2.6版》 第三章 进程 3.2节进程描述符
1. [写给 Android 应用工程师的 Binder 原理剖析](https://www.jianshu.com/p/429a1ff3560c)
1. [如果需要深入了解，推荐GitYuan大大的 Binder 系列文章](http://gityuan.com/2015/10/31/binder-prepare/)

#### View事件机制相关

- View的坐标体系
- View滑动的几种方式，使用ScrollTo/ScrollBy、使用动画、改变布局参数
- 弹性滑动的原理及实现
- View的事件分发机制，点击事件的传递规则，事件分发的源码解读
- 处理滑动冲突的场景及解决方法

推荐阅读：

《Android开发艺术探索》 第三章 View的事件体系

#### View绘制相关

- DecorView、Window、ViewRootImpl等概念
- MeasureSpec概念
- View的工作流程，measure过程、layout过程、draw过程
- 自定义View需要注意的事项
- Activity、Window、View三者之间的关系

推荐阅读：

1. 《Android开发艺术探索》第四章 View的工作原理
1. 《Android开发艺术探索》第八章 理解Window和WindowManager
1. [Android自定义控件三部曲文章索引](https://blog.csdn.net/harvic880925/article/details/50995268)

#### View动画相关

- 常用动画View动画（补间动画）、属性动画与帧动画
- 补间动画与属性动画区别
- 差值器和估值器理解
- 属性动画的工作原理

推荐阅读：

1. [Android自定义控件三部曲文章索引](https://blog.csdn.net/harvic880925/article/details/50995268)
1. 《Android开发艺术探索》 第七章 Android动画深入分析

#### Handler相关

- Handler机制之ThreadLocal
- Handler机制之Looper、Handler、消息队列如何理解
- Handler机制之Message的发送与取出
- Handler机制之Message及Message的回收机制
- Handler机制之循环消息队列的退出
- Handler机制之内存泄漏
- Handler机制之IdleHandle的理解及使用

推荐阅读：

1. 《Android开发艺术探索》第十章 10.2节 Android的消息机制
1. IdleHandle的奇思妙想----->[你知道android的MessageQueue.IdleHandler吗？](https://mp.weixin.qq.com/s/KpeBqIEYeOzt_frANoGuSg)
1. Handler面试常问题目----->[你真的懂Handler吗？Handler问答](https://www.jianshu.com/p/f70ee1765a61)
1. 如果大家不嫌弃，可以看看我的Handler机制总结----->[Anroid Handler机制总目录](https://juejin.im/post/5ba65f57e51d4539701e47d6)

#### AsyncTask相关

- AsyncTask的使用和注意事项
- AsyncTask几个重要的方法 doInBackgound、onProgressUpdate、onPostExecute等
- AsyncTask的工作原理及源码理解

推荐阅读：

1. 《Android开发艺术探索》第十一章 Android的线程和线程池
1. 《Java并发编程的艺术》第九章 Java中的线程池，第十章 Executor框架

#### Bitmap压缩回收相关

- Bitmap所占内存
- 常用压缩图片方式
- LruCache原理
- DiskLruCache原理
- LinkedHashMap原理

推荐阅读：

1. [图片占内存公式：分辨率 * 每个像素大小，严谨吗？](https://mp.weixin.qq.com/s/ufOjtKURP8QERWw1pn_m1Q)
1. [鲁班图片压缩](https://github.com/Curzibn/Luban)
1. [Map 综述（二）：彻头彻尾理解 LinkedHashMap](https://blog.csdn.net/justloveyou_/article/details/71713781)

#### ListView与RecyclerView相关

- ListView的原理和复用机制
- ListView和RecyclerView的区别

推荐阅读：

1. [Android ListView工作原理完全解析，带你从源码的角度彻底理解](https://blog.csdn.net/guolin_blog/article/details/44996879)
1. [深入理解Android中的缓存机制(二)RecyclerView跟ListView缓存机制对比](https://juejin.im/post/5a7569676fb9a063435eaf4c)
1. [RecyclerView的新机制：预取（Prefetch）](http://www.jcodecraeer.com/a/anzhuokaifa/androidkaifa/2017/0214/7113.html)
1. [Android 屏幕刷新机制](https://juejin.im/post/6844903585424097293)

#### 数据存储相关

- 常用数据库框架GreenDao,官方Room
- 数据库数据迁移问题
- GreenDao中一对一，一对多，多对多关系
- SharedPreferences使用及源码，commit与apply()方法的区别

推荐阅读：

1. [数据库基础1](https://code.tutsplus.com/articles/sql-for-beginners--net-8200)
1. [数据库基础2](https://code.tutsplus.com/articles/sql-for-beginners-part-2--net-8274)
1. [数据库基础3](https://code.tutsplus.com/articles/sql-for-beginners-part-3-database-relationships--net-8561)
1. [GreenDao官方帮助文档](http://greenrobot.org/greendao/documentation/)
1. [面试高频题：一眼看穿 SharedPreferences](https://juejin.im/post/5c34615bf265da614171bf8a)
1. [GreenDao数据库迁移帮助类 MigrationHelper](https://stackoverflow.com/questions/13373170/greendao-schema-update-and-data-migration/30334668#30334668)

### Android开源框架知识点

#### OkHttp相关

- OkHttp的优点
- OkHttp执行请求的整个流程
- OkHttp中的拦截器
- OkHttp中的同步请求与异步请求的理解及其源码
- OkHttp中涉及到的设计模式
- OkHttp底层网络请求实现，socket还是URLConnection

推荐阅读：

[拆轮子系列-拆OkHttp](https://blog.piasy.com/2016/07/11/Understand-OkHttp/index.html)

#### Retrofit相关

- Retrofit执行请求的整个流程
- Retrofit中ConverterFactory、CallAdapterFactory的理解
- Retrofit中CallAdapter的适配器模式

推荐阅读：

[拆轮子系列：拆Retrofit](https://blog.piasy.com/2016/06/25/Understand-Retrofit/index.html)

#### RxJava相关

- RxJava常用创建操作符 create、from、just、interval、range等
- RxJava常用组合、合并操作符 combineLatest、join、merge、zip等
- RxJava错误处理操作符 onErrorReturn、onErrorResumeNext、onExceptionResumeNext等
- RxJava过滤操作符 filter、ofType、sample、take等
- Rxjava背压相关理解
- RxJava实际开发中的使用：网络请求轮询、网络请求嵌套回调、从磁盘 / 内存缓存中 获取缓存数据等

推荐阅读：

1. [Android Rxjava：这是一篇 清晰 & 易懂的Rxjava 入门教程](https://www.jianshu.com/p/a406b94f3188)
1. 如果大家想直接写Demo，这里我已经写好了一份--->[RxJava操作符总结](https://github.com/AndyJennifer/RxJavaSummary)

#### Glide相关

- Glide的执行流程
- Glide的缓存机制
- Glide图片转换
- Glide带进度的图片加载功能
- Glide内存、磁盘缓存，优先级使用

推荐阅读：

1. [Android图片加载框架最全解析（一），Glide的基本用法](https://blog.csdn.net/guolin_blog/article/details/53759439)
1. [Android图片加载框架最全解析（二），从源码的角度理解Glide的执行流程](https://blog.csdn.net/guolin_blog/article/details/53939176)
1. [Android图片加载框架最全解析（三），深入探究Glide的缓存机制](https://blog.csdn.net/guolin_blog/article/details/54895665)
1. [Android图片加载框架最全解析（四），玩转Glide的回调与监听](https://blog.csdn.net/guolin_blog/article/details/70215985)
1. [Android图片加载框架最全解析（五），Glide强大的图片变换功能](https://blog.csdn.net/guolin_blog/article/details/71524668)
1. [Android图片加载框架最全解析（六），探究Glide的自定义模块功能](https://blog.csdn.net/guolin_blog/article/details/78179422)

#### ButterKnife相关

- Java注解相关Annotation
- Java注解相关之APT工具
- ButterKnife注解框架原理

推荐阅读：

1. [Android 注解系列之APT工具（三）](https://www.jianshu.com/p/fcba7013b0b0)
1. [Android 注解系列之Annotation（二）](https://www.jianshu.com/p/65c4af2ce8f0)
1. [ButterKnife 原理解析](https://www.jianshu.com/p/39fc66aa3297)

#### EventBus相关

- EventBus原理，及索引类的使用

推荐阅读：

1. [Android 注解系列之APT工具（三）](https://www.jianshu.com/p/fcba7013b0b0)
1. [Android 注解系列之Annotation（二）](https://www.jianshu.com/p/65c4af2ce8f0)
1. [腾讯Bugly干货-老司机教你“飙”EventBus3](https://blog.csdn.net/Tencent_Bugly/article/details/51354693)

### Android性能优化

- 性能优化:布局优化、绘制优化、线程优化等
- ANR异常:主线程执行了耗时操作，如BroadcastReceiver(前台广播10s,后台广播为60s)、Service(前台20s,后台200s)没有处理完相关任务等
- OOM异常：内存溢出的原因
- 内存泄漏：内存泄露的几种场景，如单例模式引出的泄露、静态变量导致的泄露、属性动画导致的内存泄露等

推荐阅读：

1. 《Android开发艺术探索》第十五章 Android性能优化
1. [Memory Profiler的使用](https://developer.android.google.cn/studio/profile/memory-profiler.html#record-allocations)
1. [LeakCanary库相关介绍](https://github.com/square/leakcanary)

### Android屏幕适配知识点

- 今日头条适配方式
- 宽高限定符适配方式
- smallestWidth适配

推荐阅读：

1. [Google 官方屏幕适配教程](https://developer.android.google.cn/guide/practices/compatibility)
1. [拉丁吴老师的--Android 目前稳定高效的UI适配方案](https://mp.weixin.qq.com/s/X-aL2vb4uEhqnLzU5wjc4Q)
1. [今日头条适配方式](https://mp.weixin.qq.com/s/d9QCoBP6kV9VSWvVldVVwA)
1. [Android 屏幕适配：最全面的解决方案](https://www.jianshu.com/p/ec5a1a30694b)

### Android打包知识点

- 安卓签名的理解
- Gradle多渠道打包

推荐阅读：
《Android Gradle权威指南》

### Android架构知识点

- MVC架构设计模式面试问题讲解
- MVP架构设计模式面试问题讲解
- MVVM架构设计模式面试问题讲解

推荐阅读：

1. [mvp架构设计](https://en.wikipedia.org/wiki/Model–view–presenter)
1. [mvvm架构设计](https://en.wikipedia.org/wiki/Model–view–viewmodel)
1. [googlesamples/android-architecture](https://github.com/googlesamples/android-architecture)

### Android不同版本特性知识点

推荐阅读：

1. [Android不同版本下的特性](https://developer.android.google.cn/about/versions/pie/)
1. [广播在7.0、8.0、9.0下的适配](https://developer.android.google.cn/guide/components/broadcasts)
1. [Android 6.0 权限下的适配](https://developer.android.google.cn/guide/topics/permissions/overview)
1. [Android 7.0 应用共享文件（FileProvider)](https://developer.android.google.cn/about/versions/nougat/android-7.0-changes)
1. [Android 7.0 共享文件的使用方式](https://developer.android.google.cn/reference/android/support/v4/content/FileProvider.html)

### 网络知识点

- 计算机网络三种体系架构，OSI体系架构（7层）、TCP/IP体系架构(4层)，五层体系架构
- TCP的连接管理（三报文握手，四报文握手）
- TCP与UDP的理解与区别
- Http（HyberText Transfer Protocol）基本概念及报文结构
- Http常见错误码
- Http1.0与Http1.1与Http2.0的区别
- Http中get请求与post请求的区别
- Http中cookie与session的区别
- Http与Https的区别
- Https加密算法相关面试问题，签名证书，公钥私钥、数字摘要的理解

推荐阅读：

1. 体系架构--->《计算机网络第七版 谢希仁》第一章 1.7.1节到1.7.5节
2. TCP三报文握手与四报文握手--->《计算机网络第七版 谢希仁》第五章 5.9节 TCP的运输连接管理
3. TCP与UDP理解--->《计算机网络第七版 谢希仁》 第五章 运输层
4. 《计算机网络第七版 谢希仁》 第六章 应用层 第七章 网络安全
5. [HTTP1.0、HTTP1.1 和 HTTP2.0 的区别](https://mp.weixin.qq.com/s/GICbiyJpINrHZ41u_4zT-A)
6. [清晰的计算机网络基础 学习指南](https://www.jianshu.com/p/45d27f3e1196)

### 设计模式知识点

- 单例模式
- Builder模式
- 装饰模式
- 策略模式
- 模板方法
- 观察者模式
- 等.....

推荐阅读：
《Android源码设计模式解析与实战》

### 算法知识点

- 常见的八大排序方式
- 时间复杂度的计算
- 链表相关算法，链表翻转，链表合并等
- 二叉树相关算法前序、中序、后序遍历（递归，迭代）
- 红黑树与BL树
- 等

推荐阅读：

1. 《Java 数据结构和算法 第二版》
1. [时间复杂度学习（上)](https://juejin.im/post/5bbb5754e51d450e8d769e80)
1. [时间复杂度学习（下)](https://juejin.im/post/5bbd79a0f265da0aa74f46a6)
1. 刷题---->[LeetCode](https://leetcode.com/)
