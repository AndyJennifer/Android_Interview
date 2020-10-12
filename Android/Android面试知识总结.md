
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
