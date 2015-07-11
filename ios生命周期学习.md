#IOS生命周期学习
##1.AppDelegate学习
#####1.1 - application:WillFinishLauchingWithOptions
```
//objective-c

-(BOOL)application:(UIApplication*)application willFinishLauchingWithOptions:(NSDictionary*)lauchOptions

//swift

- optional func application(_ application: UIApplication, willFinishLaunchingWithOptions launchOptions: [NSObject: AnyObject]?) -> Bool
```
告诉代理进程启动但还没进入状态保存，此时处于Inactive状态。
一般做一些程序启动加载初始化，makeKeyAndVisible 使得window上viewcontroller可见。
######1.2 - application:didFinishLauchingWithOptions
告诉代理进程已经完毕，app准备开始运行，一般做一些在willFinishLauchingWithOptions里面没有做完的事。
######1.3 - applicationWillResignActive:
程序将要进入Inactive，在此期间app不接收消息或事件，比如来电话了。可以在这时做一些挂起前的工作，比如关闭网络，保存数据。
######1.4 - applicationDidBecomeActive:
程序进入活动状态。可以做一些恢复数据的事
######1.5 - applicationDidEnterBackground:
进入后台，由于苹果仅允许（local,music,voip,notifaction）机制在后台运行，可以在此方法申请后台时间.beginBackgroundTaskWithExpirationHandler方法去请求后台运行时间和启动线程来运行长时间运行的任务。
######1.6 - applicationWillEnterForeground:
进入前台
######1.7 - applicationWillTerminate:
程序退出，通常用来保存一些退出前的清理工作。
######1.8 - applicationDidFinishLaunching:
程序载入后执行
##2.程序状图

![image](a1)
##3.常见优化
####3.1 当App中断时，我们可以做些什么呢？
```
*停止timer和其他周期性任务
*停止任何正在运行的请求
*暂停视频的播放
*如果是游戏就暂停
*挂起任何分发的队列和不重要的操作队列
```
####3.2 当App进入后台，我们可以做什么呢？
```
*保存用户数据或状态信息，没写到磁盘的文件或信息，赶紧写，因为可能会在后台被杀死
*释放尽可能的内存
```

