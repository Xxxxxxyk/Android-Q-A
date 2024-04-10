# Android-Q-A

## 目录

- [last update 2024.04.10](#last-update-20240410)
  - [Java基础](#Java基础)
    - [Q: Java中 == 和 equals的区别是什么? ](#Q-Java中--和-equals的区别是什么-)
    - [Q: 以下代码的输出结果是什么, 为什么? ](#Q-以下代码的输出结果是什么-为什么-)
    - [Q: int和Integer的区别](#Q-int和Integer的区别)
    - [Q: String, StringBuffer, StringBuilder的区别](#Q-String-StringBuffer-StringBuilder的区别)
    - [Q: 什么是堆, 什么是栈 , 有什么区别?](#Q-什么是堆-什么是栈--有什么区别)
    - [Q: 什么是内存泄漏, 内存溢出, 内存抖动](#Q-什么是内存泄漏-内存溢出-内存抖动)
    - [Q: GC的运行原理](#Q-GC的运行原理)
  - [Android](#Android)
    - [Q: Activity, Fragment的生命周期都是什么?](#Q-Activity-Fragment的生命周期都是什么)
      - [在正常情况下:](#在正常情况下)
      - [进入后台后:](#进入后台后)
      - [由后台再进入前台:](#由后台再进入前台)
      - [低内存情况下页面被回收](#低内存情况下页面被回收)
      - [受启动模式影响:](#受启动模式影响)
      - [Fragment的生命周期:](#Fragment的生命周期)
      - [onAttach和onDetach:](#onAttach和onDetach)
      - [onCreateView和onDestroyView](#onCreateView和onDestroyView)
      - [onActivityCreated(已过时)](#onActivityCreated已过时)
    - [Q:Activity的启动模式](#QActivity的启动模式)
      - [standard](#standard)
      - [singleTop](#singleTop)
      - [singleTask](#singleTask)
      - [singleInstance](#singleInstance)
      - [singleInstancePerTask](#singleInstancePerTask)
    - [Q: JetPack全家桶都是什么, 都有什么作用](#Q-JetPack全家桶都是什么-都有什么作用)
    - [Q: 讲解一下Android的事件分发机制](#Q-讲解一下Android的事件分发机制)
    - [Q: MotionEvent是什么, 它和GestureDetector有什么区别?](#Q-MotionEvent是什么-它和GestureDetector有什么区别)
    - [Q: 事件冲突的解决方案:](#Q-事件冲突的解决方案)
    - [Q: android的存储机制](#Q-android的存储机制)
    - [Q: Service的生命周期和启动模式](#Q-Service的生命周期和启动模式)
    - [Q: Android系统结构的原理和各版本的特性及适配](#Q-Android系统结构的原理和各版本的特性及适配)
    - [Q: MVC MVP MVVM的区别](#Q-MVC-MVP-MVVM的区别)
  - [Flutter](#Flutter)
    - [Q: Flutter的生命周期](#Q-Flutter的生命周期)
      - [StatelessWidget](#StatelessWidget)
      - [StatefulWidget](#StatefulWidget)
      - [APP的生命周期](#APP的生命周期)
      - [WidgetsBindingObserver](#WidgetsBindingObserver)
      - [AppLifecycleListener](#AppLifecycleListener)
    - [Q: Flutter与原生怎么通信](#Q-Flutter与原生怎么通信)
  - [鸿蒙](#鸿蒙)
    - [Q:Ability, page的生命周期都是什么](#QAbility-page的生命周期都是什么)
      - [Ability:](#Ability)
      - [page:](#page)
  - [设计模式](#设计模式)
    - [Q:什么是单例设计模式, 它有什么优缺点](#Q什么是单例设计模式-它有什么优缺点)
    - [Q:什么是工厂模式](#Q什么是工厂模式)
    - [Q: 什么是建造者模式](#Q-什么是建造者模式)
    - [Q: 什么是观察者模式](#Q-什么是观察者模式)
    - [Q: 什么是责任链设计模式](#Q-什么是责任链设计模式)
  - [性能调优](#性能调优)
    - [Q: 性能调优工具ProFiler的使用](#Q-性能调优工具ProFiler的使用)
    - [Q: HWUI呈现分析](#Q-HWUI呈现分析)
  - [算法](#算法)

Android的面试题整理

# last update 2024.04.10

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

A: 会输出true, true, false, false&#x20;

因为Integer内部的IntegerCache

缓存了-128 - 127之间的数进行重用, 内存指向同一个位置, 所以返回的是true, 而128不在缓存池内, ==对比的两个对象的地址值, 所以是false, equals对比的是Integer内部的equals方法, 所以返回的是true

### Q: int和Integer的区别

A: Integer是int的包装类, JDK1.5引入了自动拆箱/装箱的概念, 两者可以相互转化, 不同的是Integer的默认是是null, int的默认值是0, int和Integer比较时, Integer会自动拆箱为int进行比较

### Q: String, StringBuffer, StringBuilder的区别

A: String是字符串常量, 拼接时是不同的两个空间, StringBuffer和StringBuilder是字符串变量, 拼接时直接append在字符串的后边, StringBuff是线程安全的, 执行效率低, StringBuilder是线程不安全的, 执行效率高.

### Q: 什么是堆, 什么是栈 , 有什么区别?

A: 堆栈:

栈: 一种后进先出的数据结构, 用于存储变量和方法调用的上下文, 在android中是由编译器自动管理的, 通常不需要操作栈内存.  它的特点是速度快, 由操作系统管理, 当函数或者方法执行完毕之后, 栈帧会自动弹出, 释放内存. 栈上数据在函数调用期内存在, 函数返回数据后即被销毁. 每个线程有自己的栈, 栈的大小是有限的, 如果局部变量过多或递归较深, 会导致栈溢出 Stack Overflow

堆: 一种用于动态内存分配的内存区域, 可以在程序运行时手动申请和释放内存, 堆内存通过垃圾回收机制来回收不再使用的对象. 它的特点是大小不固定, 可以根据需要动态的分配和释放. 并且需要手动管理, 在调用时通过new来申请内存, 在不需要的时候调用release释放, 或者依靠垃圾回收机制回收. 当对象在堆上被分配之后, 它的生命周期不会因为函数的调用而立刻结束, 只有当垃圾回收机制确认没有引用指向该对象时, 才会回收其占用的内存.

### Q: 什么是内存泄漏, 内存溢出, 内存抖动

A: 内存泄漏是指因为对象创建后没有被销毁, 或者还有引用未被销毁, 导致垃圾回收机制无法进行回收, 即为内存泄漏, 内存泄漏到一定程度后, 会导致可用内存越来越少, 此时再创建对象则会内存溢出OutOfMemoryError, 内存抖动是指内存不稳定, 频繁分配和回收, 导致内存不稳定, 表现现象是频繁GC, 内存抖动会产生大量的内存碎片,  不连续的内存碎片很多情况下是无法被分配的, 从而导致OOM.

### Q: GC的运行原理

A: GC采用分代收集算法, 将Java堆内存分为新生代 老年代 针对不同存活周期, 不同大小的对象采取不同的垃圾回收策略, 新生代包括Eden区和两个Survivor区, 新创建的对象首先在Eden区分配内存, 当Eden区空间不足时, 会触发Minor GC, 存活的对象进入Survivor区域, 将对象的年龄增加, 对象在Survivor区域内每熬过一次Minor GC, 年龄就加1, 到一定年龄后会被移动到老年代, Minor GC是发生在新生代的GC, Major GC或Full GC是发生在老年代的GC, 老年代通常采用标记 - 清除 - 整理算法, 首先标记所有存活的对象, 然后清理未被标记的对象, 此方法产生内存碎片, 然后通过整理, 移动对象消除内存碎片,.

## Android

### Q: Activity, Fragment的生命周期都是什么?

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

A:Activity的启动模式分为5种

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

A1 → A2 → A3 → A2 → A3   栈1: A3 → A2   栈2: A3 → A1&#x20;

### Q: JetPack全家桶都是什么, 都有什么作用

A: JetPack包括 :

架构, 基础, 行为和UI, 旨让开发者更轻松的编写优质应用, 摆脱样板代码, 简化复杂任务, 把精力更好的放在业务逻辑中.

其中架构包括: viewModel数据模型, Room数据库, Lifecycles生命周期管理, Livedata数据通知更改, Paging加载数据源, WorkManager后台管理, Navigation导航

基础包括: KTX Kotlin, AppCompat, Benchmark代码检查, Multidex分包, Security安全性, Auto, TV和Test单元测试

行为包括: CameraX相机管理, DownloadManager下载器, Media媒体, Notifications通知, Permission权限, Sharing共享, Slices切片器

UI包括: Fragment, Animation动画, Layout布局, Emoji表情, Palette调色板&#x20;

### Q: 讲解一下Android的事件分发机制

A: 事件分发机制

android的事件分发机制是一个标准的责任链模式的实现, 它的核心主要有三个方法: dispatchTouchEvent, onInterceptTouchEvent onTouchEvent 事件从触摸屏幕的一刻开始, 生成一个MotionEvent事件, 这个事件从Activity传递到Window再传递到ViewGroup再传递到VIew, 这三个方法主要的作用是 dispatchTouchEvent决定了事件下一级要传递给谁, onInterceptTouchEvent决定了要不要处理事件, viewGroup特有,onTouchEvent决定了事件的响应, 事件分发过程中, 由顶层的activity开始分发, 然后逐级传递给目标viewgroup, 直到找到处理该事件的view为止, 在分发过程中, 如果某个viewgroup拦截了事件, 事件就不会再向下传递给子view, 而是由viewgroup自己处理或分发给父view,  当事件到达目标view时, 会调用view的onTouchEvent方法来处理事件, 如果事件处理, 则分发结束, 如果事件不处理, 则向上返回, 由父view处理.

### Q: MotionEvent是什么, 它和GestureDetector有什么区别?

A: MotionEvent和GestureDetector:&#x20;

MotionEvent是android用来描述触摸事件的类, 它包含用户点击的位置, 点击的时间, 点击的操作(按下, 抬起, 拖动等).

GestureDetector是android用来描述手势的类, 它提供了便携的手势识别的功能, 比如单击, 双击

### Q: 事件冲突的解决方案:

A: 解决方案:

通常分为滑动方向一致的冲突和滑动方向不一致的冲突, 滑动方向不一致的冲突, 通过判断滑动方向, 来决定哪个view进行拦截, 滑动方向一致的冲突, 可以通过内部拦截或外部拦截的处理方式, 内部拦截, 事件交给子view处理, 重写子view的dispatchTouchEvent方法或者onTouchEvent方法, 结合父view的requestDisallowTouchEvent方法, 需要处理就消费事件, 不需要就交给父view 外部拦截:重写父布局的onInterceptTouchEvent方法,根据条件判断什么时候拦截

### Q: android的存储机制

A: android的存储机制主要涉及到6种,每种的存储机制有特定的用途和优势

1. 内部存储, 系统存储空间,应用安装后会自动在此区域创建一个私有存储区域, 内部数据是私有的, 只有应用本身可以访问, 其他应用无法直接访问, 主要用于存储配置类文件或敏感数据
2. 外部存储, 系统内置存储或外部存储卡空间, 用途存储文件, 照片, 视频等等数据, android10之后推出了分区存储的逻辑,可以很好的管理外部存储中的文件, 确保应用的隐私和数据安全
3. 文件存储, File对象, 通过IO写入到磁盘中持久化保存的数据, 适合存储照片, 视频, 大文档等等数据
4. 数据库存储, Sqlite移动端轻量关系型数据库, 通常用来存储一些网络请求下来, 需要持久化的数据, 或者用户的配置等等, 通过sql读取
5. SP存储, 轻量级键值对存储, 用于存储一些配置文件
6. 网络存储, 通过接口访问,将数据存储到网络.或者用于不同设备间的数据共享.

### Q: Service的生命周期和启动模式

A: Service有两种启动模式, 不同的启动模式生命周期不同

bindService启动模式下, onCreate → onBind → onUnBind → onDestory

startService启动模式下, onCreate → onStartConmmond → onDestory

两种启动模式的区别是: startService的形式在开启后, 服务与调用者断开联系, 不会因为调用者的创建和销毁导致服务销毁, bindService的启动模式下, 服务的生命周期会随着调用者的生命周期开启和结束, 两种服务的通信方式(数据交互形式)也不同, startService只能通过会回调, 或者事件通知形式交互, bindService通过ServiceConnect交互. 在重复创建时, startService的服务会重复回调onStartConmmond, bindService的服务如果onUnBind返回true, 则会回调onReBind, 如果是super则不会

### Q: Android系统结构的原理和各版本的特性及适配

A: Android系统结构原理主要基于其分层的架构设计，这一设计使得Android系统既具有高度的灵活性，又能满足各种设备和应用的需求。Android系统结构的主要组成部分及其原理：
应用层：这是Android系统最上层的层次，主要负责与用户进行交互。应用层包含了大量的应用程序，如电话、短信、浏览器等，这些应用都是用Java开发的。
应用框架层：为开发人员提供了开发应用程序所需的API。这一层包含了诸如Activity Manager（活动管理器）、Location Manager（位置管理器）、Package Manager（包管理器）、Notification Manager（通知管理器）、Resource Manager（资源管理器）、Telephony Manager（电话管理器）、Window Manager（窗口管理器）、Content Provider（内容提供者）以及View System（视图系统）等组件。这些API使得开发人员能够更方便地访问系统服务和资源，从而开发出各种功能强大的应用。
系统运行库层(Framework)：这一层包含了两个部分：C/C++程序库和Android运行时。C/C++程序库提供了一系列的底层功能，如媒体框架、Surface Manager（负责多个应用程序显示与存取操作间的互动）等。Android运行时则包括核心库和Dalvik虚拟机（或ART运行时，取决于Android版本）。核心库提供了Java语言API中的大多数功能，同时也包含了Android的一些核心API。
硬件抽象层：这一层为上层提供了统一的硬件接口，使得应用程序能够访问到底层的硬件设备，而无需关心具体的硬件实现。
Linux内核层：Android系统基于Linux内核，负责如设备驱动、进程管理、内存管理等核心系统服务。Linux内核层为Android系统提供了稳定的底层支持，使得整个系统能够高效、稳定地运行。
总的来说，Android系统的结构原理是通过分层的架构设计，将复杂的系统功能分解为不同的层次，每个层次都有其特定的职责和功能。这种设计使得Android系统既具有高度的可扩展性和灵活性，又能保证系统的稳定性和安全性。同时，通过提供丰富的API和底层服务，Android系统为开发人员提供了强大的支持，方便开发出各种功能的应用。

android各版本的特性和适配, 比较典型的几个版本是 android6.0 引入了运行时权限的概念, 在进行一些危险操作时, 需要动态向用户申请授权, 比如拨打电话, 发送短信, 读取写入存储.

android10.0 分区存储,简单概括就是应用可访问的存储区域被限制, 应用访问写入APP私有目录, 无需任何权限, 应用访问共享存储区域,比如相册, 需要使用特殊的API进行访问, 比MediaStore, 应用访问其他目录, 则需要申请单独的权限.

android12 进一步完善分区存储, 访问外置存储需要MANAGE\_EXTERNAL\_STORAGE权限

android13 将读取写入外部存储权限拆分, 拆分为读取照片, 读取视频,读取音频三个权限, API小于33的应用只需要申请读取写入外部存储权限, 而API33则需要单独申请3类.

### Q: MVC MVP MVVM的区别

A: MVC model view和 controller , controller持有view和model, view也持有model, view和controller全都写在activity中, 导致controller过大, 维护复杂, 难以管理

MVP model view和presenter, view抽出和用户交互的接口, 逻辑写在presenter, presenter持有view和model, 将数据更新通过接口反应给view, 这种模式会导致需要大量的接口和抽象类

MVVM model view和viewmodel, viewmodel中与view双向绑定, 通过databinding, 在数据变化时驱动UI更新. &#x20;

## Flutter

### Q: Flutter的生命周期

A: Flutter的生命周期

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

A: 通信方式

MethodChannel

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

A: 生命周期

#### Ability:

onCreate → onWindowStateCreate → onForeground → onBackground → onWindowsStateDestory → onDestory

#### page:

onPageShow → onPageHIde → onBackPress

aboutToAppear → aboutToDisAppear

## 设计模式

### Q:什么是单例设计模式, 它有什么优缺点

A:单例设计模式

单例设计模式的核心是在保证内存中有且只有一个对象, 不同语言间的实现不同, 但原理和效果一致, 以java举例, 通常会将类的构造方法私有化, 同时对外暴漏一个获取对象实例的方法, 在内部判断对象是不是null, 如果是null则初始化, 如果不是则返回该对象, 这是一个基本的单例, 但是当这个单例在多线程场景下调用时, 两条线程同时访问, 判断== null均返回true, 这时就会创建出多个对象, 与单例的思想不符, 所以一般会在判断前加同步锁, 让线程依次执行, 同步锁会阻塞线程, 是一个耗时操作, 为了避免每次访问该对象时都访问同步锁,一般会在同步锁的外层再判断一次对象==null, 这样就不会每次访问都会触发同步锁了, 该对象还会使用volatile关键字进行标识, volatile关键字在这里的作用是禁止指令重排, 当java在创建对象时,会至少执行3个步骤, 分配内存地址, 执行构造方法, 将对象指向内存地址, 此时==null会返回false, 因为操作系统的指令重排机制问题, 不能确保执行步骤, 如果先将对象指向了内存地址, 但并没有执行构造方法, 会导致返回的对象的属性与我们想要的不一致, 所以用volatile关键字标识, 确保执行顺序. 单例模式的优点是节省内存开销, 因为内存中只有一个对象, 缺点是当单例对象持有Context的引用时, Activity被销毁, 因为Context还被单例持有, 无法被垃圾回收机制回收, 会导致内存泄漏.

### Q:什么是工厂模式

A: 工厂设计模式

工厂设计模式的核心是通过工厂方法创建多种对象, 而不需要关心内部逻辑, 工厂中不再通过new创建对象, 而是通过工厂方法, 比如创建一个运算符的类, 内部有一个计算的抽象方法, 它接收两个值, 返回一个int对象, 创建四个类加减乘除继承该类, 在方法中返回运算结果, 创建一个运算符工厂, 根据用户输入的内容创建不同的运算符类, 而它的返回值都是运算符这个对象, 因为加减乘除都实现了运算符的接口, 然后调用类的计算方法, 则返回计算结果, 它的优点是解耦, 隐藏内部实现逻辑, 扩展时不需要关心其他对象, 只需要额外新建子类, 处理不同的业务逻辑

### Q: 什么是建造者模式

A: 建造者模式

建造者模式的核心是灵活的创建复杂一个对象, 比如说我盖一个房子, 房子有门有窗有玻璃, 这个时候可以创建一个HouseBuilder的类, 用于创建一个房子, 然后调用它的buildWindow方法, 让这个房子有4个窗子,尺寸等等, 最后调用一个build方法, 创建一个House的对象, 使用建造者模式可以很好的把复杂对象的创建过程分离, 并且在不同场景下创建出不同的对象, 灵活的添加和删减其中的构建过程.&#x20;

### Q: 什么是观察者模式

A: 观察者设计模式

观察者模式的核心是当一个对象发生变化时可以立即通知给它的观察者, 它是一种通知模式, 比如AppleStore的自动更新, 当APP发生更新行为时, 商店就会通知到我APP已经更新, APP就是被观察者, 而我就是观察者, 当被观察者发生变化时, 它会通知所有关注它数据变化的观察者, 通过这种形式可以让数据之间保持一个比较松散的耦合关系, 被观察者只需要关心自身变化, 不需要关注谁观察了它, 而观察者只需要在值变化时做出处理, 而不需要关心时谁发了通知. 这种模式的好处是充分解耦, 但是会存在一个被观察者存在多个观察者对象, 导致出现bug时调试复杂, 事件滥用的情况.

### Q: 什么是责任链设计模式

A: 责任链设计模式

责任链设计模式很像击鼓传花的游戏, 它的核心是将事件一层一层传递下去, 每个节点都需要参与决策或者处理事件, 直到某一个节点消耗了这个事件, 它的优点是降低耦合度, 可以灵活的删除和增加链上的对象, 但是如果链过长时, 会影响性能,  因为每一个节点都需要逻辑判断, 所以android上要求避免布局嵌套过深.&#x20;

## 性能调优

### Q: 性能调优工具ProFiler的使用

A: 通过ProFiler的CPU Profiler可以查看哪个线程消耗的时间最多, 是否有不必要的线程或长时间运行的线程。再进行代码层面的分析优化, Memory Profiler可以监控内存的使用情况, 查找内存泄漏,查看内存分配来找出哪些对象占用了大量内存。Network Profiler可以分析网络请求的传输速度, 请求时间等.

### Q: HWUI呈现分析

A: HWUI呈现分析可以查看页面绘制性能,它是由绿色, 黄色, 红色的柱状图组成的,绿色：表示帧的渲染在16毫秒内完成，这是60帧每秒的标准。黄色：表示帧的渲染超过了16毫秒，但仍在可接受的范围内。红色：表示帧的渲染时间过长，可能会导致界面卡顿。可以通过查看柱状图分析布局, 比如嵌套层级过深, bitmap使用优化, 减少布局更新等等

## 算法
