
# Android 面试知识总结

## Handler 相关

- Handler问题三连：是什么？有什么用？为什么要用Handler，不用行不行？
- 真的只能在主(UI)线程中更新UI吗？
- 真的不能在主(UI)线程中执行网络操作吗？
- Handler怎么用？
- 为什么建议使用Message.obtain()来创建Message实例？
- 为什么子线程中不可以直接new Handler()而主线程中可以？
- 主线程给子线程的Handler发送消息怎么写？
- HandlerThread实现的核心原理？
- 当你用Handler发送一个Message，发生了什么？
- Looper是怎么拣队列里的消息的？
- 分发给Handler的消息是怎么处理的？
- IdleHandler是什么？
- Looper在主线程中死循环，为啥不会ANR？
- Handler泄露的原因及正确写法
- Handler中的同步屏障机制

## Bitmap压缩机回收相关

- Bitmap所占内存
- 常用压缩图片方式
- LruCache原理
- DiskLruCache原理
- LinkedHashMap原理

## Activity 相关

- 典型状况下的生命周期
- 异常情况下的生命周期
- 异常情况下的数据保存
- 各种情况下跳转到某个Activity时目标Activity及当前Activity的生命周期
- Activity的启动模式及应用场景
- 进程和应用生命周期
- startActivity 启动过程分析
- 底层剖析 Window、Activity、View 三者关系
  
推荐阅读：

- [Android 是如何通过 Activity 进行交互的](/Android/Android是如何通过Activity进行交互的.md)

## View事件机制相关

- View的坐标体系
- View滑动的几种方式，使用ScrollTo/ScrollBy、使用动画、改变布局参数
- 弹性滑动的原理及实现
- View的事件分发机制，点击事件的传递规则，事件分发的源码解读
- 处理滑动冲突的场景及解决方法

推荐阅读：

- [彻底掌握Android事件分发机制](/Android/彻底掌握Android事件分发机制.md)
- [安卓自定义View进阶-MotionEvent详解](https://www.gcssloop.com/customview/motionevent)
- Android开发艺术探索》 第三章 View的事件体系

## WebView 优化

推荐阅读：

- [WebView性能、体验分析与优化](https://tech.meituan.com/2017/06/09/webviewperf.html)
- [手把手教你构建 Android WebView 的缓存机制 & 资源预加载方案](https://blog.csdn.net/carson_ho/article/details/71402764- )
[70%以上业务由H5开发，手机QQ Hybrid 的架构如何优化演进？](https://mp.weixin.qq.com/s/evzDnTsHrAr2b9jcevwBzA)
