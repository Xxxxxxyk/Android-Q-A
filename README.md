# Android-Q-A

Android的面试题整理

# last update 2024.04.08

立个flag , 每天至少更新一道已经理解的面试题, 直到跳槽完成

## Java基础

### Q: Java中 == 和 equals的区别是什么?&#x20;

A: Java中 == 是比较运算符, 它在比较基础数据类型时, 比较的是值的本身, 在比较对象时, 比较的是对象的地址值, equals在默认的情况下, 调用的是Object的equals方法, 与 == 作用一致, 但在比较对象时, 如果重写了对象的equals和hashcode方法时, 它会根据对象的equals方法进行比较, 而hashcode方法, 其目的是生成一个hash码, 用于查找对象, 如果两个对象的equals方法返回true, 那么这两个对象的hashcode一定相等, 如果是hashcode相等, 不代表equals一定相等, 只能代表这两个对象在一个散列存储结构中, 所以当equals方法被重写时, hashcode方法也要被重写

### Q: 以下代码的输出结果是什么, 为什么?&#x20;

```java
public static void main(String[] args) {
    Integer a = 127;
    Integer b = 127;
    Integer c = 128;
    Integer d = 128;
    System.out.println(a == b);
    System.out.println(a.equals(b));
    System.out.println(c == d);
    System.out.println(c.equals(d));
}
```

#### A: 会输出true, true, false, false&#x20;

因为Integer内部的IntegerCache

缓存了-128 - 127之间的数进行重用, 内存指向同一个位置, 所以返回的是true, 而128不在缓存池内, ==对比的两个对象的地址值, 所以是false, equals对比的是Integer内部的equals方法, 所以返回的是true

### Q: int和Integer的区别

A: Integer是int的包装类, JDK1.5引入了自动拆箱/装箱的概念, 两者可以相互转化, 不同的是Integer的默认是是null, int的默认值是0, int和Integer比较时, Integer会自动拆箱为int进行比较

### Q: String, StringBuffer, StringBuilder的区别

A: String是字符串常量, 拼接时是不同的两个空间, StringBuffer和StringBuilder是字符串变量, 拼接时直接append在字符串的后边, StringBuff是线程安全的, 执行效率低, StringBuilder是线程不安全的, 执行效率高.

### Q: 什么是堆, 什么是栈 , 有什么区别?

## Android

## Q: Activity, Fragment, Service的生命周期都是什么?

A: Activity的生命周期有多种情况

#### 在正常情况下:

生命周期依次是 onCreate -> onStart - > onResume -> 页面可见&#x20;

#### 进入后台后:

onPause -> onStop

#### 由后台再进入前台:

onPause -> onResume

#### 低内存情况下页面被回收

onPause -> onStop -> onSaveInstanceState -> onDestory onCreate -> onStart -> onRestoreInstanceState -> onResume

#### 受启动模式影响:

启动模式是singleTop或者singleTask时, 重复开启activity会走onNewIntent方法

#### Fragment的生命周期:

部分与Activity一致, 除此之外它有几个独立的生命周期方法是 onAttach, onCreateView, onActivityCreated, onDestroyView, onDetach

#### onAttach和onDetach:

是在Fragment与Activity建立关联和取消关联时调用的, 在这个方法里可以获取到关联的activity的引用和销毁

#### onCreateView和onDestroyView

是Fragment创建/移除view时调用的

#### onActivityCreated(已过时)

关联的activity的oncreate方法执行完毕时被调用.

### Q:Activity的启动模式

### A:Activity的启动模式分为5种

#### standard

默认的启动模式, 新建的activity会盖在前一个activity的上边, 返回时一层一层的返回

A1 → A2 → A3 → A4    A4 → A3 → A2 → A1

#### singleTop

栈顶复用模式, 新建activity时会正常创建, 再次启动时, 会查看当前栈顶是不是存在该activity的实例, 如果存在, 则直接复用, 并调用activity的onNewIntenet方法, 如果栈顶不存在, 则新建, 举例, A2是singleTop

A1 → A2 → A3 → A2 → A2     A2 → A3 → A2 → A1

#### singleTask

栈内复用模式, 新建activity时会正常创建, 再次启动时,会查看当前栈内是不是存在该activity的实例,如果存在, 则直接复用,  并调用activity的onNewIntenet方法, 同时将该activity顶上的所有activity弹栈. 举例: A2是singleTask

A1 → A2 → A3 → A2     A2 → A1

#### singleInstance

独立栈模式, 新建的activity在一个单独的栈中, 并且栈中只能存在该activity, 新开启的activity归属于父栈, 举例: A2是singleInstance

A1 → A2 → A3 → A2 → A3   A2独立栈   A3 → A3 → A1

#### singleInstancePerTask

android12加入的新启动模式, 与singleInstance一致, 不同的是栈中可以存在不同的activity. 举例: A2是singleInstancePerTask

A1 → A2 → A3 → A2 → A3   栈1: A3 → A2   栈2: A3 → A1

### Q: JetPack全家桶都是什么, 都有什么作用

A: JetPack包括 架构, 基础, 行为和UI, 旨让开发者更轻松的编写优质应用, 摆脱样板代码, 简化复杂任务, 把精力更好的放在业务逻辑中.

其中架构包括: viewModel数据模型, Room数据库, Lifecycles生命周期管理, Livedata数据通知更改, Paging加载数据源, WorkManager后台管理, Navigation导航

基础包括: KTX Kotlin, AppCompat, Benchmark代码检查, Multidex分包, Security安全性, Auto, TV和Test单元测试

行为包括: CameraX相机管理, DownloadManager下载器, Media媒体, Notifications通知, Permission权限, Sharing共享, Slices切片器

UI包括: Fragment, Animation动画, Layout布局, Emoji表情, Palette调色板&#x20;

## Flutter

### Q: Flutter的生命周期

### A: Flutter的生命周期

Flutter分为StatelessWidget, StatefulWidget和APP的生命周期

#### StatelessWidget

StatelessWidget是无状态组件, 它的生命周期只有createState和build, 只渲染一次

#### StatefulWidget

StatefulWidget是有状态组件, 它的生命周期包含:

createState initState didChangeDependencies build didiUpdateWidget deactivate dispose

createState用于创建state

initState在初始化时被调用,只会执行一次

didChangeDependencies 在依赖的对象发生变化时调用, 在Widget 第一次创建时,会在 initState 之后立即调用一次.

build 构建build树, 决定了页面的样式

didUpdateWidget：在组件重建时调用, 比如热重载时.

deactivate当Widget被移除时调用

dispose 当state被销毁时调用,释放资源

#### APP的生命周期

APP的生命周期分两种 Flutter3.13之前是WidgetsBindingObserver, 3.13(含)之后是AppLifecycleListener

#### WidgetsBindingObserver

通过给state with WidgetsBindingObserver 实现didChangeAppLifecycleState方法, 状态在AppLifecycleState中获取,包含5中

```dart
// 应用程序在初始化之前默认处于此状态
 // 视图还没有显示在屏幕上，或者 视图从屏幕上分离后
 detached,
 // 可见，并且可以响应用户操作
 resumed,
 // 可见，但无法响应用户操作
 inactive,
 // 隐藏，不可见，应用程序可以在后台运行
 hidden,
 // 暂停，不可见，并且无法响应用户操作
 paused,
```

#### AppLifecycleListener

构建一个AppLifecycleListener对象,设置不同生命周期回调的方法,包含

```dart
/// 可见，并且可以响应用户操作时的回调
onResume() {
  debugPrint('---onResume');
}
/// 可见，但无法响应用户操作时的回调
onInactive() {
  debugPrint('---onInactive');
}
/// 隐藏时的回调
onHide() {
  debugPrint('---onHide');
}
/// 显示时的回调。
onShow() {
  debugPrint('---onShow');
}
/// 暂停时的回调
onPause() {
  debugPrint('---onPause');
}
/// 暂停后恢复时的回调
onRestart() {
  debugPrint('---onRestart');
}
/// 这两个回调，不是所有平台都支持，
/// 当退出 并将所有视图与引擎分离时的回调（IOS 支持，Android 不支持）
onDetach() {
  debugPrint('---onDetach');
}
/// 在退出程序时，发出询问的回调（IOS、Android 都不支持）
/// 响应 [AppExitResponse.exit] 将继续终止，响应 [AppExitResponse.cancel] 将取消终止。
Future<AppExitResponse> onExitRequested() async {
  debugPrint('---onExitRequested');
  return AppExitResponse.exit;
}
```

### Q: Flutter与原生怎么通信

### A: 通信方式

#### MethodChannel

通过在flutter层创建MethodChannel ,原生层注册同名MethodChannel

```dart
static Future<String> getData() async {
    String data = "";
    const platform = MethodChannel("com.test/methodChannel");
    try {
      data = await platform.invokeMethod("getData");
      return dbPath;
    } on Exception catch (e) {
      return '';
    }
  }
```

```kotlin
override fun configureFlutterEngine(flutterEngine :FlutterEngine) {
   flutterEngine.getPlugins().add(FlutterNativePlugin(this));
}
```

```kotlin
class FlutterNativePlugin : FlutterPlugin, MethodChannel.MethodCallHandler {

    val context: Context

    constructor(context: Context) {
        this.context = context
    }

    override fun onAttachedToEngine(binding: FlutterPlugin.FlutterPluginBinding) {

        //name必须和dart端的保持一致
        val channel = MethodChannel(binding.flutterEngine.dartExecutor, "com.test/methodChannel")
        channel.setMethodCallHandler(FlutterNativePlugin(binding.applicationContext))
    }

    companion object {
        fun registerWith(registrar: PluginRegistry.Registrar) {
            val channel = MethodChannel(registrar.messenger(), "com.test/methodChannel")
            channel.setMethodCallHandler(FlutterNativePlugin(registrar.context()))
        }
    }

    override fun onDetachedFromEngine(binding: FlutterPlugin.FlutterPluginBinding) {
    }

    override fun onMethodCall(call: MethodCall, result: MethodChannel.Result) {
        when (call.method) {
            "getUserName" -> result.success('name')
            else -> result.notImplemented()
        }
    }
}
```

## 鸿蒙

### Q:Ability, page的生命周期都是什么

### A: 生命周期

#### Ability:

onCreate → onWindowStateCreate → onForeground → onBackground → onWindowsStateDestory → onDestory

#### page:

onPageShow → onPageHIde → onBackPress

aboutToAppear → aboutToDisAppear

## 设计模式

### Q:什么是单例设计模式, 它有什么优缺点

### A:单例设计模式

单例设计模式的核心是在保证内存中有且只有一个对象, 不同语言间的实现不同, 但原理和效果一致, 以java举例, 通常会将类的构造方法私有化, 同时对外暴漏一个获取对象实例的方法, 在内部判断对象是不是null, 如果是null则初始化, 如果不是则返回该对象, 这是一个基本的单例, 但是当这个单例在多线程场景下调用时, 两条线程同时访问, 判断== null均返回true, 这时就会创建出多个对象, 与单例的思想不符, 所以一般会在判断前加同步锁, 让线程依次执行, 同步锁会阻塞线程, 是一个耗时操作, 为了避免每次访问该对象时都访问同步锁,一般会在同步锁的外层再判断一次对象==null, 这样就不会每次访问都会触发同步锁了, 该对象还会使用volatile关键字进行标识, volatile关键字在这里的作用是禁止指令重排, 当java在创建对象时,会至少执行3个步骤, 分配内存地址, 执行构造方法, 将对象指向内存地址, 此时==null会返回false, 因为操作系统的指令重排机制问题, 不能确保执行步骤, 如果先将对象指向了内存地址, 但并没有执行构造方法, 会导致返回的对象的属性与我们想要的不一致, 所以用volatile关键字标识, 确保执行顺序. 单例模式的优点是节省内存开销, 因为内存中只有一个对象, 缺点是当单例对象持有Context的引用时, Activity被销毁, 因为Context还被单例持有, 无法被垃圾回收机制回收, 会导致内存泄漏.
