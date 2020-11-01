# Android 面试知识总结

## Activity相关

- 典型状况下的生命周期
- 异常情况下的生命周期
- 异常情况下的数据保存
- 各种情况下跳转到某个Activity时目标Activity及当前Activity的生命周期
- Activity的启动模式及应用场景
- 进程和应用生命周期

推荐阅读：

- 《Android开发艺术探索》 第一章 Activity的生命周期和启动模式
- 《Android开发艺术探索》 第九章 9.2节Activity的工作过程
- [Google-进程和应用生命周期](https://developer.android.google.cn/guide/components/activities/process-lifecycle)
- [Google-任务和返回栈](https://developer.android.google.cn/guide/components/activities/tasks-and-back-stack)
- [Android 是如何通过 Activity 进行交互的](/Android/Android是如何通过Activity进行交互的.md)

## Service相关

- Service的定义及作用
- Service两种启动方式  startService、 bindService 区别及生命周期
- Service绑定服务的三种实现方式，扩展Binder类、使用Messenger、使用AIDL
- 关于启动服务与绑定服务间的转换问题 先绑定服务后启动服务、先启动服务后绑定服务
- 服务Service与线程Thread的区别
- Android 5.0以上的隐式启动问题及其解决方案
- 如何保证服务不被杀死
- IntentService的使用及原理

推荐阅读：

- 《Android开发艺术探索》 第九章 9.3节Service的工作过程
- [关于Android Service真正的完全详解，你需要知道的一切](https://blog.csdn.net/javazejian/article/details/52709857)
- [Android 多线程之IntentService 完全详解](https://blog.csdn.net/javazejian/article/details/52426425)
- [Android 多线程之HandlerThread 完全详解](https://blog.csdn.net/javazejian/article/details/52426353)

## BroadcastReceiver相关

- BroadcastReceiver定义及作用、应用场景
- BroadcastReceiver的注册方式，静态方式、动态方式
- BroadcastReceiver注册与取消的时机
- BroadcastReceiver的不同类型，普通广播，系统广播、有序广播、粘性广播、应用类广播

推荐阅读：

- 《Android开发艺术探索》 第九章 9.4节BroadcastReceiver 的工作过程
- [BroadcastReceiver史上最全面解析](https://www.jianshu.com/p/ca3d87a4cdf3)
- [广播在7.0、8.0、9.0下的适配](https://developer.android.google.cn/guide/components/broadcasts)

## Fragment相关

- Fragment生命周期
- Fragment的懒加载
- Fragment之间的通信
- FragmentPagerAdapter与FragmentStatePagerAdapter的区别
- 为什么不建议直接通过使用new Fragment的方式传入数据

推荐阅读：

- [Fragment全解析系列（一）：那些年踩过的坑](https://www.jianshu.com/p/d9143a92ad94)
- [Google-Fragment概览](https://developer.android.google.cn/guide/components/fragments)
- [Google-与其他Fragment通信](https://developer.android.google.cn/training/basics/fragments/communicating)

## 序列化相关

- 序列化与反序列化的定义及区别
- Serializable中serialVersionUID及transient关键字的作用
- 序列化：Parcelable和Serializable差异

推荐阅读：

- [序列化与反序列化之Parcelable和Serializable浅析](https://blog.csdn.net/javazejian/article/details/52665164)
- 《Android开发艺术探索》 第二章 IPC基础概念介绍

## IPC相关

- 在Android中什么样的情况下会使用多进程模式，如何开启多进程
- Android为什么采用Binder做为IPC机制
- IPC常用方式 使用Bundle、使用文件共享、使用Messenger、使用AIDL、使用ContentProvider、使用Socket
- AIDL的语义
- AIDL如何创建
- AIDL生成Java文件详细分析

推荐阅读：

- 《Android开发艺术探索》 第二章 IPC机制
- 《深如理解LINUX内核 第三版涵盖2.6版》 第三章 进程 3.2节进程描述符
- [写给 Android 应用工程师的 Binder 原理剖析](https://www.jianshu.com/p/429a1ff3560c)
- [如果需要深入了解，推荐GitYuan大大的 Binder 系列文章](http://gityuan.com/2015/10/31/binder-prepare/)
- [听说你Binder机制学的不错，来面试下这几个问题（一）](https://www.jianshu.com/p/adaa1a39a274)

## View事件机制相关

- View的坐标体系
- View滑动的几种方式，使用ScrollTo/ScrollBy、使用动画、改变布局参数
- 弹性滑动的原理及实现
- View的事件分发机制，点击事件的传递规则，事件分发的源码解读
- 处理滑动冲突的场景及解决方法

推荐阅读：

- [彻底掌握Android事件分发机制](/Android/彻底掌握Android事件分发机制.md)
- [安卓自定义View进阶-MotionEvent详解](https://www.gcssloop.com/customview/motionevent)
- 《Android开发艺术探索》 第三章 View的事件体系

## View绘制相关

- DecorView、Window、ViewRootImpl等概念
- MeasureSpec概念
- View的工作流程，measure过程、layout过程、draw过程
- 自定义View需要注意的事项
- Activity、Window、View三者之间的关系

推荐阅读：

- 《Android开发艺术探索》第四章 View的工作原理
- 《Android开发艺术探索》第八章 理解Window和WindowManager
- [Android自定义控件三部曲文章索引](https://blog.csdn.net/harvic880925/article/details/50995268)
- [Android 如何通过 View 进行渲染](/Android/Android如何通过View进行渲染.md)

## View动画相关

- 常用动画View动画（补间动画）、属性动画与帧动画
- 补间动画与属性动画区别
- 差值器和估值器理解
- 属性动画的工作原理

推荐阅读：

- [Android自定义控件三部曲文章索引](https://blog.csdn.net/harvic880925/article/details/50995268)
- 《Android开发艺术探索》 第七章 Android动画深入分析

## Handler 相关

- Handler机制之ThreadLocal
- Handler机制之Looper、Handler、消息队列如何理解
- Handler机制之Message的发送与取出
- Handler机制之Message及Message的回收机制
- Handler机制之循环消息队列的退出
- Handler机制之内存泄漏
- Handler机制之IdleHandle的理解及使用

推荐阅读：

- 《Android开发艺术探索》第十章 10.2节 Android的消息机制
- IdleHandle的奇思妙想----->[你知道android的MessageQueue.IdleHandler吗？](https://mp.weixin.qq.com/s/KpeBqIEYeOzt_frANoGuSg)
- Handler面试常问题目----->[你真的懂Handler吗？Handler问答](https://www.jianshu.com/p/f70ee1765a61)
- 如果大家不嫌弃，可以看看我的Handler机制总结----->[Anroid Handler机制总目录](https://juejin.im/post/5ba65f57e51d4539701e47d6)

## AsyncTask相关

- AsyncTask的使用和注意事项
- AsyncTask几个重要的方法 doInBackgound、onProgressUpdate、onPostExecute等
- AsyncTask的工作原理及源码理解

推荐阅读：

- Android开发艺术探索》第十一章 Android的线程和线程池
- 《Java并发编程的艺术》第九章 Java中的线程池，第十章 Executor框架

## Bitmap压缩机回收相关

- Bitmap所占内存
- 常用压缩图片方式
- LruCache原理
- DiskLruCache原理
- LinkedHashMap原理

## WebView 优化

推荐阅读：

- [WebView性能、体验分析与优化](https://tech.meituan.com/2017/06/09/webviewperf.html)
- [手把手教你构建 Android WebView 的缓存机制 & 资源预加载方案](https://blog.csdn.net/carson_ho/article/details/71402764- )
- [70%以上业务由H5开发，手机QQ Hybrid 的架构如何优化演进？](https://mp.weixin.qq.com/s/evzDnTsHrAr2b9jcevwBzA)

## Android屏幕适配知识点

- 今日头条适配方式
- 宽高限定符适配方式
- smallestWidth适配

推荐阅读：

- [Google 官方屏幕适配教程](https://developer.android.google.cn/guide/practices/compatibility)
- [拉丁吴老师的--Android 目前稳定高效的UI适配方案](https://mp.weixin.qq.com/s/X-aL2vb4uEhqnLzU5wjc4Q)
- [今日头条适配方式](https://mp.weixin.qq.com/s/d9QCoBP6kV9VSWvVldVVwA)
- [Android 屏幕适配：最全面的解决方案](https://www.jianshu.com/p/ec5a1a30694b)

## Android开源框架知识点

### OkHttp相关

- OkHttp的优点
- OkHttp执行请求的整个流程
- OkHttp中的拦截器
- OkHttp中的同步请求与异步请求的理解及其源码
- OkHttp中涉及到的设计模式
- OkHttp底层网络请求实现，socket还是URLConnection

推荐阅读：

[拆轮子系列-拆OkHttp](https://blog.piasy.com/2016/07/11/Understand-OkHttp/index.html)

### Retrofit相关

- Retrofit执行请求的整个流程
- Retrofit中ConverterFactory、CallAdapterFactory的理解
- Retrofit中CallAdapter的适配器模式

推荐阅读：

[拆轮子系列：拆Retrofit](https://blog.piasy.com/2016/06/25/Understand-Retrofit/index.html)

### RxJava相关

- RxJava常用创建操作符 create、from、just、interval、range等
- RxJava常用组合、合并操作符 combineLatest、join、merge、zip等
- RxJava错误处理操作符 onErrorReturn、onErrorResumeNext、onExceptionResumeNext等
- RxJava过滤操作符 filter、ofType、sample、take等
- Rxjava背压相关理解
- RxJava实际开发中的使用：网络请求轮询、网络请求嵌套回调、从磁盘 / 内存缓存中 获取缓存数据等

推荐阅读：

1. [Android Rxjava：这是一篇 清晰 & 易懂的Rxjava 入门教程](https://www.jianshu.com/p/a406b94f3188)
1. 如果大家想直接写Demo，这里我已经写好了一份--->[RxJava操作符总结](https://github.com/AndyJennifer/RxJavaSummary)

### Glide相关

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

## 实战常见问题

- [面对内存泄漏，如何进行优化](/Android/面对内存泄漏，如何进行优化.md)
- [面对UI卡顿，如何入手分析解决问题](/Android/面对UI卡顿，如何入手分析解决问题.md)
- [网络编程，做过哪些优化](/Android/网络编程，做过哪些优化.md)

## Android 源码分析

- [startActivivty启动过程分析](/Android/startActivivty启动过程分析.md)
- [底层剖析 Window、Activity、View 三者关系](/Android/底层剖析Window、Activity、View的关系.md)
- [Android 是如何通过 Activity 进行交互的](/Android/Android是如何通过Activity进行交互的.md)
- [Android App 的安装过程](/Android/Android%20App%20的安装过程.md)

## Android打包知识点

- 安卓签名的理解
- Gradle多渠道打包

推荐阅读：

- 《Android Gradle权威指南》
- [项目构建速度优化](/Android/项目构建速度优化.md)

## 设计模式知识点

- 单例模式
- Builder模式
- 装饰模式
- 策略模式
- 模板方法
- 观察者模式
- 等.....

推荐阅读：
《Android源码设计模式解析与实战》
