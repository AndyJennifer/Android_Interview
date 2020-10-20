# Android 是如何通过 Activity 进行交互的

本篇文章中我们主要讲解 Android 通过 Activity 进行交互时的一些问题。

相信对于 Android 工程师来说，startActivity 就如同初恋一般，要求低、见效快。是每一个 Android 工程师从青葱少年迈向成熟大叔必经阶段。遥想 2010 年，我也是凭着一手 startActivity 技能玩的特别好，成功俘获了多家公司的芳心。这么多年过去了，在谷歌的调教下，startActivity 也变得越发成熟和丰满，对工程师的要求也越来越高。这节课就来看下使用 startActivity 时都有哪些需要注意的点。

## taskAffinity

对于 Activity 的启动模式，每一个 Android 工程师都非常熟悉。通过设置不同的启动模式可以实现调配不同的 Task。但是 taskAffinity 在一定程度上也会影响任务栈的调配流程。

每一个 Activity 都有一个 Affinity 属性，如果不在清单文件中指定，默认为当前应用的包名。taskAffinity 主要有以下几点需要注意。

### taskAffinity 会默认使 Activity 在新的栈中分配吗

可以通过一个例子来验证一下，在一个 Android 项目 LagouTaskAffinity 中，创建两个 Activity：First 和 Second，它们的具体配置如下：

![img14](../img/安卓/img14.png)

除了 Activity 类名之外，其他都是默认配置。这种情况下，点击 First 中的 Button，从 First 页面跳转到 Second 页面。

然后在命令行执行以下命令：

```java
adb shell dumpsys activity activities
```

上述命令会将系统中所有存活中的 Activity 信息打印到控制台，具体结果如下：

![img15](../img/安卓/img15.png)

上图中的 TaskRecord 代表一个任务栈，在这个栈中存在两个 Activity 实例：First 和 Second，并且 Second 处于栈顶。
接下来将 Second 的 taskAffinity 修改一下，如下所示：

![img16](../img/安卓/img16.png)

我将 Second 的 taskAffinity 修改为 ”lagou.affinity“，使它和 First 的 taskAffinity 不同。重新运行代码，并再次查看任务栈中的情况，结果如下：

![img17](../img/安卓/img17.png)

可以看出，虽然 First 和 Second 的 taskAffinity 不同，但是它们都被创建在一个任务栈中。

但如果我再将 Second 的 launchMode 改为 singleTask，再次重新运行则会发现两个 Activity 会被分配到不同的任务栈中，如下所示：

![img18](../img/安卓/img18.png)

>结论：单纯使用 taskAffinity 不能导致 Activity 被创建在新的任务栈中，需要配合 singleTask 或者 singleInstance！

### taskAffinity + allowTaskReparenting

allowTaskReparenting 赋予 Activity 在各个 Task 中间转移的特性。一个在后台任务栈中的 Activity A，当有其他任务进入前台，并且 taskAffinity 与 A 相同，则会自动将 A 添加到当前启动的任务栈中。这么说比较抽象，举一个生活中的场景：

1. 在某外卖 App 中下好订单后，跳转到支付宝进行支付。当在支付宝中支付成功之后，页面停留在支付宝支付成功页面。
2. 按 Home 键，在主页面重新打开支付宝，页面上显示的并不是支付宝主页面，而是之前的支付成功页面。
3. 再次进入外卖 App，可以发现支付宝成功页面已经消失。

造成上面现象的原因就是 allowTaskReparenting 属性，还是通过代码案例来演示。

分别创建 2 个 Android 工程：First 和 TaskAffinityReparent：

- 在 First 中有 3 个 Activity：FirstA、FirstB、FirstC。打开顺序依次是 FirstA -> FirstB -> FirstC。其中 FirstC 的 taskAffinity 为”lagou.affinity“，且 allowTaskReparenting 属性设置为true。FirstA 和 FirstB 为默认值；
- TaskAffinityReparent 中只有一个 Activity--ReparentActivity，并且其 TaskAffinity 也等于”lagou.affinity“。

将这两个项目分别安装到手机上之后，打开 First App，并从 FirstA 开始跳转到 FirstB，再进入 FirstC 页面。然后按 Home 键，使其进入后台任务。此时系统中的 Activity 信息如下：

![img19](../img/安卓/img19.png)

接下来，打开 TaskAffinityReparent 项目，屏幕上本应显示 ReparentActivity 的页面内容，但是实际上显示的却是 FirstC 中的页面内容，并且系统中 Activity 信息如下：

![img20](../img/安卓/img20.png)

可以看出，FirstC 被移动到与 ReparentActivity 处在一个任务栈中。此时 FirstC 位于栈顶位置，再次点击返回键，才会显示 ReparentActivity 页面。

## 通过 Binder 传递数据的限制

### Binder 传递数据限制

Activity 界面跳转时，使用 Intent 传递数据是最常用的操作了。但是 Intent 传值偶尔也会导程序崩溃，比如以下代码：

![img21](../img/安卓/img21.png)

在 startFirstB 方法中，跳转 FirstB 页面，并通过 Intent 传递 Bean 类中的数据。但是执行上述代码会报如下错误：

![img22](../img/安卓/img22.png)

上面 log 日志的意思是 Intent 传递数据过大，最终原因是 Android 系统对使用 Binder 传数据进行了限制。通常情况为 1M，但是根据不同版本、不同厂商，这个值会有区别。

解决办法：

- 减少通过 Intent 传递的数据，将非必须字段使用 transient 关键字修饰。
  
比如上述 Bean 类中，假如 byte[] data 并非必须使用的数据，则需要避免将其序列化，如下所示：

![img23](../img/安卓/img23.png)

添加 transient 修饰之后，再次运行代码则不会再报异常。

- 将对象转化为 JSON 字符串，减少数据体积。

因为 JVM 加载类通常会伴随额外的空间来保存类相关信息，将类中数据转化为 JSON 字符串可以减少数据大小。比如使用 Gson.toJson 方法。

大多时候，将类转化为 JSON 字符串之后，还是会超出 Binder 限制，说明实际需要传递的数据是很大的。这种情况则需要考虑使用本地持久化来实现数据共享，或者使用 EventBus 来实现数据传递。

## process 造成多个 Application

一直以来，我们经常会在自定义的 Application 中做一些初始化的操作。比如 App 分包、推送初始化、图片加载库的全局配置等，如下所示：

![img24](../img/安卓/img24.png)

但实际上，Activity 可以在不同的进程中启动，而每一个不同的进程都会创建出一个 Application，因此有可能造成 Application 的 onCreate 方法被执行多次。比如以下代码：

![img25](../img/安卓/img25.png)

RemoteActivity 的 process 为“lagou.process”，这将导致它会在一个新的进程中创建。当在 MainActivity 中跳转到 RemoteActivity 时，LagouApplication 会被再次创建，其代码如下：

![img26](../img/安卓/img26.png)

最终打印日志如下：

![img26](../img/安卓/img27.png)

可以看出 LagouApplication 的 onCreate 方法被创建了 2 次，因此各种初始化的操作也会被执行 2 遍。

针对这个问题，目前有两种比较好的处理方式：

- onCreate 方法中判断进程的名称，只有在符合要求的进程里，才执行初始化操作；
- 抽象出一个与 Application 生命周期同步的类，并根据不同的进程创建相应的 Application 实例。
  
更多详细介绍可以参考这篇文章：[解决 Android 多进程导致 Application 重复创建问题](https://conorlee.top/2017/02/21/Multi-Process-Dispatch/)

## 后台启动 Activity 失效

试想一下，如果我们正在玩着游戏，此时手机后台可能有个下载某 App 的任务在执行。当 App 下载完之后突然弹出安装界面，中断了游戏界面的交互，这种情况会造成用户体验极差，而最终用户的吐槽对象都会转移到 Android 手机或者 Android 系统本身。

为了避免这种情况的发生，从 Android10（API 29）开始，Android 系统对后台进程启动 Activity 做了一定的限制。官网对其介绍如下：

![img28](../img/安卓/img28.png)

主要目的就是尽可能的避免当前前台用户的交互被打断，保证当前屏幕上展示的内容不受影响。

但是这也造成了很多实际问题，在我们项目中有 Force Update 功能，当用户选择升级之后会在后台进行新的安装包下载任务。正常情况下下载成功需要弹出 apk 安装界面，但是在某一版升级时突然很多用户反馈无法弹出下载界面。经过查看抓取的 log 信息，最终发现有个特点就是都发生在 Android 10 版本，因此怀疑应该是版本兼容问题，最终谷歌搜索，发现果然如此。

解决办法：
Android 官方建议我们使用通知来替代直接启动 Activity 操作：

![img29](../img/安卓/img29.png)

也就是当后台执行的任务执行完毕之后，并不会直接调用 startActivity 来启动新的界面，而是通过 NotificationManager 来发送 Notification 到状态栏。这样既不会影响当前使用的交互操作，用户也能及时获取后台任务的进展情况，后续的操作由用户自己决定。
