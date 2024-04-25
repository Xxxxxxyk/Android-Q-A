# Android-Q-A

## 目录

- [last update 2024.04.25](#last-update-20240425)
  - [Java基础](#Java基础)
    - [Q: Java中 == 和 equals的区别是什么? ](#Q-Java中--和-equals的区别是什么-)
    - [Q: 以下代码的输出结果是什么, 为什么? ](#Q-以下代码的输出结果是什么-为什么-)
    - [Q: int和Integer的区别](#Q-int和Integer的区别)
    - [Q: String, StringBuffer, StringBuilder的区别](#Q-String-StringBuffer-StringBuilder的区别)
    - [Q: 什么是堆, 什么是栈 , 有什么区别?](#Q-什么是堆-什么是栈--有什么区别)
    - [Q: 什么是内存泄漏, 内存溢出, 内存抖动](#Q-什么是内存泄漏-内存溢出-内存抖动)
    - [Q: GC的运行原理](#Q-GC的运行原理)
    - [Q: 线程池](#Q-线程池)
    - [Q:线程池的执行流程](#Q线程池的执行流程)
    - [Q: 内部类为什么会持有外部类的引用](#Q-内部类为什么会持有外部类的引用)
    - [Q: Thread的join方法是做什么用的](#Q-Thread的join方法是做什么用的)
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
    - [Q: MVI](#Q-MVI)
    - [Q: AndroidThread是什么](#Q-AndroidThread是什么)
    - [Q: View的绘制流程](#Q-View的绘制流程)
    - [Q: 为什么Android不允许层级嵌套过深, 但是Compose就没问题](#Q-为什么Android不允许层级嵌套过深-但是Compose就没问题)
    - [Q:OKHttp的源码解析](#QOKHttp的源码解析)
    - [Q:LiveData是什么](#QLiveData是什么)
    - [Q:Lifecycle是什么](#QLifecycle是什么)
    - [Q:Handler](#QHandler)
    - [Q:Handler为什么会造成内存泄漏](#QHandler为什么会造成内存泄漏)
    - [Q:为什么Handler不会导致ANR](#Q为什么Handler不会导致ANR)
    - [Q:线程消息机制和线程异步处理](#Q线程消息机制和线程异步处理)
    - [Q:进程间通信](#Q进程间通信)
    - [Q:性能优化内存优化](#Q性能优化内存优化)
    - [Q:网络通信机制，对 Socket 通信、TCP/IP 和 HTTP 有一定理解](#Q网络通信机制对-Socket-通信TCPIP-和-HTTP-有一定理解)
    - [Q:Glide](#QGlide)
    - [Q:一张图片占用的内存空间怎么计算](#Q一张图片占用的内存空间怎么计算)
    - [Q:不使用三方库怎么减小图片占用体积](#Q不使用三方库怎么减小图片占用体积)
    - [Q: Retrofit的源码解析](#Q-Retrofit的源码解析)
  - [Kotlin](#Kotlin)
    - [协程](#协程)
  - [Flutter](#Flutter)
    - [Q: Flutter的生命周期](#Q-Flutter的生命周期)
      - [StatelessWidget](#StatelessWidget)
      - [StatefulWidget](#StatefulWidget)
      - [APP的生命周期](#APP的生命周期)
      - [WidgetsBindingObserver](#WidgetsBindingObserver)
      - [AppLifecycleListener](#AppLifecycleListener)
    - [Q: Flutter与原生怎么通信](#Q-Flutter与原生怎么通信)
    - [Q:Flutter的绘制原理](#QFlutter的绘制原理)
    - [Q:FLutter的手势识别原理](#QFLutter的手势识别原理)
    - [Q: Getx](#Q-Getx)
    - [Q: RiverPod](#Q-RiverPod)
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
    - [Q: 什么是动态代理](#Q-什么是动态代理)
  - [性能调优](#性能调优)
    - [Q: 性能调优工具ProFiler的使用](#Q-性能调优工具ProFiler的使用)
    - [Q: HWUI呈现分析](#Q-HWUI呈现分析)
  - [算法](#算法)
  - [面试做题](#面试做题)
    - [Q: 同时有三个线程, 怎么确保线程依次执行](#Q-同时有三个线程-怎么确保线程依次执行)
    - [Q:同时有三个线程,实现交替执行100次](#Q同时有三个线程实现交替执行100次)

# last update 2024.04.25

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

### Q: 线程池

A: java的线程池是一种多线程的处理形式, 通过把任务添加到线程池队列中执行,  java提供了几种线程池的实现,FixedThreadPool, 固定大小线程, 核心线程数和最大线程数由我们指定, 始终不变, CachedThreadPool, 缓存线程池, 线程池根据需要创建线程,没有任务时回收线程, SingleThreadExecutor, 单线程, 只有一个线程, 保证任务按顺序执行等等 我们也可以自定义线程池的参数, 核心参数是拒绝策略, 当线程池的线程数达到最大线程数时的任务处理方式: 1. 丢弃任务并抛出异常, 2. 丢弃任务, 3. 丢弃队列最前边的任务, 重新提交当前任务, 4. 由提交任务的线程处理该任务,当前线程的任务都执行完毕后执行. 线程池的优点是降低资源消耗, 提高线程可管理性.

### Q:线程池的执行流程

A: 在提交任务后, 首先判断是否存在空闲线程, 如果存在, 则分配, 不存在, 则判断是否已经达到核心线程数, 未达到则创建核心线程, 已达到则判断工作队列是否已满, 如果未满则放入工作队列等待, 如果已满则判断是否已达到最大线程数, 如果未达到则创建非核心线程, 如果已达到则执行拒绝策略.

### Q: 内部类为什么会持有外部类的引用

A: 因为内部类和外部类编译完成后会生成不同的class文件, 内部类的构造函数种会传入外部类的实例, 然后通过this\$0访问外部成员, 不然也没办法调用外部类的方法等等

### Q: Thread的join方法是做什么用的

A: 等待线程执行结束之后再继续执行当前线程.

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

### Q: MVI

A:

### Q: AndroidThread是什么

### Q: View的绘制流程

A: &#x20;

View的绘制流程主要经过了几大步

1. 启动activity

   activity的启动分为两种, 应用内启动和Launcher启动, 当启动一个activity时, 会将请求发送给AMS, AMS会判断目标进程存不存在, 如果不存在则发消息给zygote进程, 从zygote进程fork出目标进程, 进程启动后会调用ActivityThread.main方法, 然后发消息给AMS, 告诉AMS目标进程已启动, 然后AMS调用bindAppcation, 然后调用scheduleTransaction, 启动对应activity.
2. 创建PhoneWindow

   在activity启动后, 会调用attach方法, attach方法初始化了Window, 实际初始化的是Window的子类PhoneWindow, 这个时候PhoneWindow创建完成, 调用activity的onCreate方法
3. 设置布局setContentView, 将xml布局转化为view&#x20;

   在activity启动, 调用完成onCreate方法后, 一般会在onCreate中初始化布局, 调用setContentView, setContentView首先调用的AppCompatActivity的setContentView, 在AppCompatActivity中又调用了getDelegate的setContentView, 而getDelegate实际调用的是AppCompatDelegate.create生成的AppCompatDelegateImpl, 在这里执行了LayoutInflater.from(mContext).inflate(resId, contentParent);  这里通过inflate方法, 运用反射, 将标签名转化成view, 将属性转成AttributeSet, 然后生成view对象
4. 添加布局转化后的view到android.R.id.content中, 这个时候view添加到window中, 开始绘制view本身

   在布局转化为view对象前, AppCompatDelegateImpl中会调用ensureSubDecor方法, 这个方法在第一次调用时, 调用了createSubDecor, 而createSubDecor中又调用了window的setContentView方法, 根据activity的源码可知, getWindow实际是PhoneWindow对象, 而PhoneWindow的setContentView中, 第一次调用时, 因为contentParent是null, 调用installDecor, 然后调用generateDecor方法, 根据features来确定layoutResources, 生成DecorView, 此时有了android.R.id.content, 它的本质是一个FrameLayout, 这时把setContent中的layout布局添加到这个FreamLayout中, 这个时候绘制还没开始, 真正的绘制要在onResume方法走完之后, 在ActivityThread的handleResumeActivity方法里, 执行了activity的onResume之后, 执行了wm.addView方法, 这个wm实际是activity的getWindowmanager方法, 根据activity的源码可知, 实际是WindowManagerImpl的实例,  调用的它的addView, 而它的addView又进而执行了WindowManagerGlobal的addView方法, 在这里创建了ViewRootImpl的实例, 调用了setView方法,  在这里才开始真正的view绘制流程, 调用requestLayout, 判断是不是在主线程, 然后发起绘制请求,然后在performTraversals方法里开始执行onMeasure, onLayout, onDraw
5. 确认view占用空间尺寸, onMeasure

   用来测量view的宽和高, 在performMeasure方法中会调用view的measure方法, 对所有的子元素进行measure, measure过后可以通过getMeasuredWidth和getMeasuredHeight拿到view测量后的宽高
6. 确认摆放位置, onLayout

   用来确定view的四个顶点坐标和实际的view的宽和高, 在performLayout中调用layout方法, 确定布局四个点的位置, 可以通过getWidth和getHeight拿到view最终的宽高
7. 开始绘制, onDraw

   用来绘制view, 在performDraw中调用draw方法, 通过dispatchDraw实现传递过程.&#x20;

### Q: 为什么Android不允许层级嵌套过深, 但是Compose就没问题

A: 因为xml布局在测量过程中可能会发生多次, 嵌套会导致测量时间指数级增长,  Compose强制渲染1次, 就算是嵌套, 也只会是线性增长, 假设布局有2层, 其中父view会对每个子view做二次测量, 那么它的每个子view一共需要被测量两次, 如果到3层, 最内层的view被测量的次数就变成了4次, 以此类推, 而compose只允许测量一次, 不允许重复测量. 此外布局层级嵌套过深还会导致事件分发机制的责任链过长, 导致事件传递变慢.&#x20;

### Q:OKHttp的源码解析

A: OKHttp的源码解析可以先从发起一个请求开始看

```kotlin
//使用建造者模式创建一个OkHttpClient的对象, 设置超时时间, 拦截器等等
var build: OkHttpClient = OkHttpClient.Builder()
            .callTimeout(30, TimeUnit.SECONDS)
            .build()
//使用建造者模式创建一个Request对象
var request: Request = Request.Builder()
            .addHeader("", "")
            .url("")
            .get()
            .build()
//调用异步方法拿到Response
build.newCall(request).enqueue(object : okhttp3.Callback {
       override fun onFailure(call: okhttp3.Call, error: java.io.IOException) {
       }

       override fun onResponse(call: okhttp3.Call, response: okhttp3.Response) {
       }
})
//调用同步方法拿到Response
var response : Response = build.newCall(request).execute()           

```

由上可知几个对象, OkHttpClient, Request, Call, 首先是OkHttpClient, 它的作用是配置参数, 它的内部采用了建造者模式, 方便用户配置参数, 比如超时时间, 拦截器, cookie等等, 其次是Request. Requet它的作用也是配置参数, 只不过它配置的是url, 请求方法, header和body

```java
public final class Request {
  final HttpUrl url;
  final String method;
  final Headers headers;
  final @Nullable RequestBody body;
  final Map<Class<?>, Object> tags;
  ...
  }
```

然后是Call, Call是一个接口, 通过源码可知, newCall的实际返回对象是RealCall.newRealCall,  然后调用同步或者异步方法, 获取Response, 在异步调用的过程中还有一个核心类是AsyncCall, 它是RealCall里的一个内部类, 它的本质是一个Runnable, 被调度器中的线程池执行, 然后还有Dispatcher调度器, 用来调度Call对象, 同时包含线程池与异步请求队列, 用来存放AsyncCall的对象, 然后就是Response, 里边包含了接口的响应数据和Callback回调, 包含了响应成功和失败的两个方法. 以上主要是对请求过程中核心类的作用. 然后是具体的源码流程分析

同步请求:

在newCall之后, 调用它的同步方法, 实际调用时RealCall的同步方法, 同步方法里首先判断是不是已经执行过了, 如果执行过直接抛出异常, 确保只执行一次, 然后开始请求超时计时, 开启请求监听, 然后通过调度器, 把Call加入到runningSyncCalls的队列里, 开始调用getResponseWithInterceptorChain方法, 获取response, 最终执行完毕时, 把call在队列里移除. 这是同步请求的执行流程

异步请求:

在newCall之后, 调用它的异步方法, 实际调用时RealCall的同步方法, 异步方法里首先判断是不是已经执行过了, 如果执行过直接抛出异常, 确保只执行一次, 然后开始请求超时计时, 开启请求监听, 新建一个AsyncCall对象, 通过调度器加入到readyAsyncCalls队列, 然后通过调度器的enqueue里的promoteAndExecute方法发起请求, 这个方法里首先判断是不是有请求正在执行, 如果没有, 加锁保证线程安全, 遍历readyAsyncCalls队列, 判断runningAsyncCalls队列里是不是超过了最大请求数64, 判断同域名的请求是不是超过了5条线程,判断都通过之后, 把请求从readyAsyncCalls中移除, 加入到executableCalls和runningAsyncCalls中,判断运行队列中的请求数量是不是大于0, 标记是否有请求正在执行, 遍历可执行队列, 调用线程池执行AsyncCall的execute方法, 调用getResponseWithInterceptorChain获取response, 通过Callback的onResponse或者onFailure把请求结果或者错误信息传递给调用者, 异步请求结束, 最后调用调度器的finished方法

getResponseWithInterceptorChain方法是怎么拿到response的:

不管是同步请求还是异步请求, 最终调用的都是getResponseWithInterceptorChain方法拿到response的, 这个方法内部首先构建了一个拦截器责任链对象RealInterceptorChain, 然后执行拦截器列表中的每一个拦截器的proceed方法, 返回response

拦截器列表:

拦截器可以根据执行顺序分为7类:&#x20;

1. client.interceptors() 自定义拦截器, 在OkHttpClient构建时通过addInterceptor添加, 可以用于添加添加请求header, 日志拦截器
2. RetryAndFollowUpInterceptor, 这个拦截器主要用于对连接初始化, 以及请求失败的充实, 重定向等连接跟踪工作
3. BridgeInterceptor, 用于将用户构建的请求转换为服务器需要的请求,比如添加content-type, 添加user-agent, 将网络请求返回的响应结果转化为可用的响应, 比如移除Content-Length, 移除Content-Encoding
4. CacheInterceptor, 用于处理缓存的相关逻辑,  在OkHttpClient构建时通过cache创建, 拦截器会结合请求新建一个缓存策略, 用来判断是用网络还是缓存创建response
5. ConnectInterceptor, 用于负责建立连接
6. client.networkInterceptors(), 自定义网络拦截器, 在OkHttpClient构建时通addNetworkInterceptor添加, 它和client.interceptors()的区别是, client.interceptors()一定会执行, 因为它是第一个拦截器, 而网络拦截器不一定会执行, 比如使用缓存的情况下, 或者发生了重定向时, 可能会执行多次.
7. CallServerInterceptor, 网络的IO操作, 把请求头,请求体发送给服务器, 解析服务器返回的response

拦截器通过责任链设计模式, 按顺序执行, 得到response之后, 再从下往上返回回去. 这样做的好处是达到充分解耦, 只需要把请求放到责任链上即可, 无需关心处理细节和请求的传递过程.&#x20;

### Q:LiveData是什么

A: LiveData通常用于在viewModel中通知View层数据变化, 实现数据驱动UI, 使用大致分为4步:&#x20;

> 1.初始化一个livedata对象, 定义好被观察数据的类型
> 2.定义并注册观察者对象, 更改被观察者的值
> 3.通知给观察者
> 4.观察者收到值后进行响应

LiveData的原理可以从定义被观察者对象和更新对象讲解

定义被观察者对象:

观察者模式的构成里一般都有一个接口, livedata的接口是Observer, 它的内部有onChange方法, 在数据发生更改时调用, 通过ObserverWrapper进行了包装, livedata的核心方法是它的observe方法, 在observe中, 首先判断了是不是在主线程和观察者的生命周期是不是onDestroy, 通过生命周期组件与观察者对象新构建一个绑定生命周期的观察者对象LifecycleBoundObserver, 命名wrapper, 这一步主要是为了让观察者对象可以响应activity的生命周期, 在activity处于stop状态时, 不用通知数据变化, 然后检查一下wrapper是否已存在于观察者对象集合中, 如果存在返回在集合中的值, 证明已经注册了观察者, 如果不存在, 将wrapperadd到集合中，并返回null。然后开始判断返回值, 如果不为null, 检查生命周期是否与当前一致,如果不一致抛出异常, 如果是null, 通过addObserver添加到生命周期感知中。

更新对象:

livedata提供两种更新数据操作, setValue和postValue, setValue必须在主线程中调用,同步执行, postValue可以在子线程和主线程中调用, 异步执行, setValue中首先会判断是不是在主线程, 然后给version++, 最后通过dispatchingValue分发数据, 当观察者的version大于或等于livedata的version时, 证明已经接收过当前版本的数据, 不会在发送.postValue中则是通过handler把数据调度到主线程, 然后调用setValue来实现的

### Q:Lifecycle是什么

A: Lifecycle可以让组件具备感知生命周期的能力, 内部通过观察者模式, 将生命周期感知对象和生命周期提供者解耦, 而不用通过回调的形式来通知给需要感知生命周期的对象. 它的内部lifecycle是一个抽象类, 内部有state和event构成, 代表了生命周期的状态和事件, 通过addObserver和removeObserver添加和移除生命周期观察者,Event和state的关系是, event代表着生命周期发生变化的点, state代表着生命周期所处的阶段, 如果我们自己的控件想要感知生命周期, 需要实现LifecycleObserver 的接口, 在生命周期持有者LifecycleOwner对象内部进行添加和移除观察者, 比如activity, fragment都是生命周期的持有者, 它们的内部都有一个方法叫getLifecycle, 它返回一个lifecycleRegistry的对象, 它是lifecycle的具体实现类,将最新的生命周期事件通过handleLifecycleEvent方法提供给观察者对象.handleLifecycleEvent是在生命周期的每个阶段被调用的.

### Q:Handler

A: Handler在大部分情况下, 用来做线程间通讯, 在android内部用来做事件处理, 它的核心类有Handler, Looper, MessageQueue和Message, 它的构成很像电梯, 可以理解为MessageQueue是传送带, Looper是传送带的动力来源, Message则是电梯上的人, Handler则是人上下电梯的过程, 首先通过handler.post/send方法, 把消息放到队列中, 然后Loop通过一个死循环来提供动力, 把Message通过MessageQueue发送到Handler的dispatch中进行处理, 当没有消息时, 则阻塞队列, 等消息队列调用enqueueMessage时通知队列, 解除阻塞, handler与创建线程绑定, 在初始化时得到messagequeue, 所有的消息通过messagequeue发送给handler, 这也就是为什么handler能做线程通讯,  因为handler的发送者的线程不管在哪, 所有的消息都通过messagequeue发送到handler所在的线程, 所以实现了跨线程通讯.

### Q:Handler为什么会造成内存泄漏

A: 原因1: 延迟消息, 当Activity关闭后, 延迟消息还未发出, 主线程的MessageQueue持有消息引用, 而这个消息持有Handler的引用, 而Handler作为匿名内部类又持有了Activity的引用, 主线程不会被回收, 所以这个引用链导致Activity也无法被回收, 导致出现内存泄漏

原因2: 子线程不回收, 子线程通过Handler更新UI, 子线程持有了Activity的引用, 运行中的子线程不会被回收, 所以导致Activity也不会被回收

解决方案: 改写为静态内部类, 在activity onDestory时对handler进行回收,移除所有消息.

### Q:为什么Handler不会导致ANR

A: ANR和Handler的死循环不是一个概念, ANR是任务未在规定时间完成, Handler的死循环是在没事件处理时是阻塞状态. 等待后边有事件时再唤醒

### Q:线程消息机制和线程异步处理

A: 以下几种

1. runOnUiThread 在主线程中处理数据
2. Handler.post, 通过android回调到主线程处理
3. 通过观察者模式, 例如EventBus,LiveData,广播等, 通过事件发送处理
4. RxJava, 通过observerOn, 线程调度到主线程处理
5. 通过AsyncTask 处理

### Q:进程间通信

A: 以下几种

1. 通过Intent, 接收方通过IntentFilter进行接收
2. 通过ContentProvider, 但只能访问特定规则数据
3. 通过广播, 一个进程发送一个广播, 在另一个进程注册并接收
4. 通过AIDL, 定义跨进程通信接口
5. 通过Binder

### Q:性能优化内存优化

A:   1. 通过ProFiler或者leakcanary等工具进行内存泄漏优化

1. 避免单例对象持有context的引用
2. IO流关闭
3. bitmap回收, 图片尺寸, 质量压缩
4. 使用弱引用等等

### Q:网络通信机制，对 Socket 通信、TCP/IP 和 HTTP 有一定理解

A: Socket是TCP/IP网络的API, 它是对TCP/IP协议的封装, 通过Socket, 可以进行网络数据通信, TCP/IP是一种网络通信协议, IP属于网络层, TCP属于传输层, TCP使用三次握手来创建连接, 使用四次挥手释放连接,  第一次握手, 建立连接, 客户端发送请求报文, 等待服务器确认, 服务器收到并确认报文之后, 发送给客户端, 客户端收到服务器返回的报文后, 三次握手结束, 建立连接成功, 当数据发送结束后, 需要断开连接, 此时采用四次挥手, 第一次, 客户端告诉服务器,没有数据发送了, 第二次服务器收到客户端的数据后, 向客户端返回ACK报文, 同意关闭请求, 第三次向服务端向客户端发送FIN报文, 请求关闭连接, 第四次客户端收到FIN报文,向主机发送ACK报文, 服务器收到后, 关闭连接, 客户端没有在收到回复后,证明服务端已关闭, 此时关闭客户端. 三次握手可以防止服务器收到失效请求后一直等待客户端请求, 造成死锁, 四次挥手则可以保证双方都可以正常释放和断开连接.HTTP的基础也是基于TCP/IP, 它由请求方法, 请求头, 请求体, 响应码, 响应体构成.Https则是通过SSL数据加密的

### Q:Glide

A: Glide主要分为三个部分, 首先是with阶段, 绑定页面生命周期,管理请求和生命周期事件, 然后是load阶段, 给每个请求配置单独的参数,比如宽高, 缓存等, 最后是into阶段, 启动请求, 加载数据, 对数据进行转码, 并进行缓存, 展示图片, 它的最主要的是缓存策略, 可以分为三块,活跃内存缓存, 普通内存缓存, 资源缓存, 磁盘转换的图片和数据缓存, 缓存在磁盘上的文件, 在取缓存的过程中, 检查到哪一层有缓存就直接返回图片, 如果都没有缓存就取网络/文件/资源里加载,

### Q:一张图片占用的内存空间怎么计算

A: 长度 \* 宽度 \* 每个像素占用空间 像素占用空间根据不同模式占用不同, ARGB8888占用4个字节, RGB565占用两个字节, ARGB4444和ALPHA8占用1个字节

### Q:不使用三方库怎么减小图片占用体积

A: 1. 设置Bitmap.Option.isJustDecodeBounds为true, 只读取图片的宽高, 而不加载图片, 根据尺寸做等比压缩. 2. 设置图片采样率为ARGB565, 减小占用内存 3. 如果在列表里的话, 滑动过程中暂停加载, 滑动结束再加载

### Q: Retrofit的源码解析

## Kotlin

### 协程

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

### Q:Flutter的绘制原理

A: Flutter的渲染主要通过三棵树来实现, 即Widget树, Element树和RenderObject树组成, Widget树是Flutter中用描述UI界面的一种数据结构, 它由一系列的Widget节点构成, Widget节点是不可变的, 它的配置信息一旦创建就不会发生变化,  这就使得Widget树可以在不同的时间节点上被重复使用. 每个Widget节点都有一个build方法, 它返回一个Element节点, 用于构建Element树. Element树是Widget树的实例, 用来表示Widget树在运行时的一种数据结构, 它由Element节点组成, 每个Element节点包含了一个Widget节点和与它对应的状态信息, Element节点是可变的, 当Widget节点需要更新时, Flutter会在Element树上进行对应操作, 比如添加删除等, 来反映出Widget树的变化, 然后是RenderObject树, RenderObject树是用来描述UI布局和绘制的一种数据结构, 每个RenderObject节点包含了一个用于描述UI界面和绘制的RenderObject对象, 这些对象根据Widget树和Element树信息进行布局和绘制, 最终在屏幕上显示.RenderObject树是可变的, 当Element节点需要更新时, Flutter会在RenderObject树上进行操作. 以反映出UI界面的变化

### Q:FLutter的手势识别原理

A: 手势识别原理可以分为三个方面, 底层指针事件, 手势识别, 指针事件处理流程, 底层指针事件, 当触摸在屏幕时, 产生PointerEvent来包装这个事件, 形成事件流, Flutter的手势识别本质上是监听这个事件流, 内部通过RawGestureDetector 判断和跟踪手势来做出响应的反应. 手势识别, GestureRecognizer是手势识别的基类, 他定义了手势识别的基础方法和流程,Flutter提供一些常用的手势识别器, 他们都是继承GestureRecognizer来实现的, 当手势被识别器识别后, GestureRecongnizer会触发对应手势的回调, 如果它的子树上存在多个识别同一手势的识别器的话, 它会选取其中的一个来响应.指针事件处理流程, 产生PointerEvent事件后, 首先是命中测试, 将PointerDownEvent传给GestureBinding, GestureBinding 是Flutter的手势系统入口, 负责管理整个手势识别体系, GestureBinding沿着渲染树, 从叶节点向根节点遍历, 对每个节点进行命中测试, 测试通过表示该组件需要处理点击事件, 然后加入到HitTestResult列表中. 然后是事件分发, 命中测试完毕后, GestureBinding会遍历HitTestResult列表, 调用每一个对象的事件处理方法handleEvent来处理事件, 后续产生的事件直到抬起后也会按照HitTestResult列表进行分发, 直到分发完毕后, 清空HitTestResult列表

### Q: Getx

A:

### Q: RiverPod

A:

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

### Q: 什么是动态代理

A:

## 性能调优

### Q: 性能调优工具ProFiler的使用

A: 通过ProFiler的CPU Profiler可以查看哪个线程消耗的时间最多, 是否有不必要的线程或长时间运行的线程。再进行代码层面的分析优化, Memory Profiler可以监控内存的使用情况, 查找内存泄漏,查看内存分配来找出哪些对象占用了大量内存。Network Profiler可以分析网络请求的传输速度, 请求时间等.

### Q: HWUI呈现分析

A: HWUI呈现分析可以查看页面绘制性能,它是由绿色, 黄色, 红色的柱状图组成的,绿色：表示帧的渲染在16毫秒内完成，这是60帧每秒的标准。黄色：表示帧的渲染超过了16毫秒，但仍在可接受的范围内。红色：表示帧的渲染时间过长，可能会导致界面卡顿。可以通过查看柱状图分析布局, 比如嵌套层级过深, bitmap使用优化, 减少布局更新等等

## 算法

## 面试做题

### Q: 同时有三个线程, 怎么确保线程依次执行

A1:

```kotlin
//使用handler,每个线程执行完毕后再开始下个线程
        val handler = Handler(Looper.getMainLooper(), Handler.Callback {
            binding.tvText.setText(it.obj.toString());
            when (it.what) {
                1 -> {
                    thread1.start()
                }

                2 -> {
                    thread2.start()
                }
            }
            return@Callback true
        })

        val thread = Thread {
            val message = Message()
            message.obj = "123580"
            message.what = 1
            handler.sendMessage(message)
        }.start()

        thread1 = Thread {
            val message = Message()
            message.obj = "246810"
            message.what = 2
            handler.sendMessageDelayed(message, 3000)
        }

        thread2 = Thread {
            val message = Message()
            message.obj = "我变成英文了哈"
            message.what = 3
            handler.sendMessageDelayed(message, 3000)
        }

```

A2:

```kotlin
//使用Volatile, 保证变量的更改对所有线程可见, 一个变量控制
        @Volatile
        var x: Int = 0
        
        var thread = Thread {
            binding.tvText.setText("13579");
        }

        thread1 = Thread {
            while (x != 1) {

            }
            runOnUiThread {
                binding.tvText.setText("246810")
            }
        }
        thread2 = Thread {
            while (x != 2) {

            }
            runOnUiThread {
                binding.tvText.setText("我变成英文了哈");
            }
        }

        thread.start()
        thread1.start()
        thread2.start()

        Handler().postDelayed(Runnable { x = 1 }, 3000)
        Handler().postDelayed(Runnable { x = 2 }, 6000)

```

A3:

```kotlin
//使用锁
fun printString(text: String) {
    print(text)
}

fun main() {
    val c0 = CountDownLatch(0)
    val c1 = CountDownLatch(1)
    val c2 = CountDownLatch(1)
    Thread {
        c0.await()
        for (x in 0..10) {
            printString("A")
        }
        c1.countDown()
    }.start()

    Thread {
        c1.await()
        for (x in 0..10) {
            printString("B")
        }
        c2.countDown()
    }.start()

    Thread {
        c2.await()
        for (x in 0..10) {
            printString("C")
        }
    }.start()

}

```

### Q:同时有三个线程,实现交替执行100次

A1:

```kotlin
var times: Int = 100

@Volatile
var count: Int = 1


fun main() {
    var obj: Object = Object()

    Thread {
        synchronized(obj) {
            while (count <= times) {
                while (count % 3 != 1) {
                    obj.wait()
                }
                print("A")
                count++
                obj.notifyAll()
            }
        }
    }.start()

    Thread {
        synchronized(obj) {
            while (count <= times) {
                while (count % 3 != 2) {
                    obj.wait()
                }
                print("B")
                count++
                obj.notifyAll()
            }
        }
    }.start()

    Thread {
        synchronized(obj) {
            while (count <= times) {
                while (count % 3 != 0) {
                    obj.wait()
                }
                print("C")
                count++
                obj.notifyAll()
            }
        }
    }.start()

}
```

A2:

```kotlin
fun main() {
    var s1: Semaphore = Semaphore(1)
    var s2: Semaphore = Semaphore(0)
    var s3: Semaphore = Semaphore(0)

    Thread {
        for (x in 0..100) {
            s1.acquire()
            print("A")
            times--
            s2.release()
        }
    }.start()
    Thread {
        for (x in 0..100) {
            s2.acquire()
            print("B")
            times--
            s3.release()
        }
    }.start()
    Thread {
        for (x in 0..100) {
            s3.acquire()
            print("C")
            times--
            s1.release()
        }
    }.start()
}
```

A3:

```kotlin
```
