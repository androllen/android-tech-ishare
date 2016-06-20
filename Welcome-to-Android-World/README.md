欢迎来到Android世界!  
Android 简介  
在讨论 Eclipse 插件和开发 Android 应用程序之前，我们先看看 Android 的体系结构和一些重要的术语，  
这会对本教程后面的讨论和您自己构建 Android 应用程序有帮助。  
Android 术语  
在 Eclipse 环境中开发 Android 应用程序需要了解 Eclipse 环境和 Android 平台的知识。  
了解以下术语会有助于用 Eclipse 插件开发 Android 应用程序。  
Open   
这是一个由 Google 公司主导的组织，它由许多Handset Alliance公共和私人组织组成。   
Android   
这是 Open Handset Alliance 的主打产品。它是一种针对移动设备的开放源码操作环境。   
模拟器   
模拟另一个系统的软件工具 — 这常常是在个人计算机（IBM®、Mac、Linux®）上运行的一个环境，它模拟另一个环境，比如移动计算设备。   
Linux 
一种开放源码的操作系统内核，许多计算平台都使用这种操作系统，包括服务器、桌面计算机、网络设备和移动计算设备。  
Android 在 Linux 内核上运行。   
Dalvik Virtual Machine   
Dalvik VM 是 Android 产品组合中的一种操作环境，它在运行时解释应用程序代码。Dalvik VM 与 Java VM 相似，但是两者不兼容。  

Android 基础知识和必需的工具  
Android 是一种针对移动平台的开放源码操作系统。到编写本教程时，它是一种纯软件的平台，没有可用的硬件设备。  
Android 平台被称为一个产品组合，因为它是一系列组件的集合，包括：  
•	基于 Linux 内核的操作系统   
•	Java 编程环境   
•	工具集，包括编译器、资源编译器、调试器和模拟器   
•	用来运行应用程序的 Dalvik VM   
简要介绍了 Android 平台的体系结构之后，我们来从市场的角度看看这个平台的一些重要特性。    

Android 为什么很重要？  
自从 Android 和最初的 SDK 发布以来，计算机技术新闻界一直非常关注 Android。Android 之所以重要主要有两个原因。   
Android 是 Google 进军移动市场的主要行动。移动应用程序领域竞争激烈，新的竞争者很难涉足。  
Google 拥有大量资源和强大的品牌实力，有能力涉足任何市场。Google 进军移动市场已经好几年了。  
Android 原来属于另一家公司，Google 通过收购这家公司大大提高了在移动市场上的竞争力。  
Google 的任何行动都会受到关注，而且引入新平台也很引人注目。Android 同时具备这两个因素。  
第二个原因是 Android 的应用程序模型与众不同。Android 应用程序并不是需要大量单击操作的纯粹的菜单式应用程序。  
Android 应用程序中确实有菜单和按钮，但是 Android 在体系结构中引入了一种新颖的设计元素 intent。   
  

intent  
intent 是一种构造，应用程序可以通过它发出请求，这就像是发出求助信号。intent 可能像下面这样：  
"Wanted: An application to help me look up a contact" 或 "Wanted: An application to help me display this image"  
或 "Wanted: An application to perform this geographic-based search"  
应用程序可以按照相似或互补的方式进行注册，表明它们有能力或有兴趣执行各种请求或 intent。比如：  
"Available: Application ready and willing to present contact records in clear, concise manner"  
或 "Available: Application ready and willing to perform a geographic search"  
这些是 IntentFilter 的示例，下面将要讨论。  
  
IntentFilter   
应用程序通过一个称为 IntentFilter 的构造声明它们能够执行某些类型的操作。  
IntentFilter 可以在运行时进行注册，也可以在 AndroidManifest.xml 文件中设置。  
下面的代码片段取自一个对 SMS（文本）消息进行响应的 Android 应用程序：  

清单 1. 对 SMS 进行响应的 Android 应用程序
                    
       <receiver class=".MySMSMailBox" >
            <intent-filter>
    	      <action android:value="android.provider.Telephony.SMS_RECEIVED" />
            </intent-filter>
    	</receiver>

简要介绍 intent 和 IntentFilter 之后，下一节介绍 Android 应用程序的四种主要类型。  

来迎接新的 Android SDK!  
我们刚刚发布了 Android 1.0 SDK! 如果你现在正在用旧版的SDK, 那你可能需要做一些工作升级你的开发环境  
并对你的应用程序做些调整以适应新的 Android 平台.  
请阅读 升级指南 和 API变化一览 来了解更多信息.  
如果你想了解详细的不同, 请阅读API差异分析报告.  
Android 平台 是一个移动设备专用的软件堆, 包括一个操作系统, 中间件以及大量关键应用.   
开发者能建立大量应用程序通过Android SDK平台。应用程序使用Java程序语言编写并且在Dalvik上运转，   
Dalvik是一个运行在Linux内核之上专门供嵌入使用的虚拟机。  
如果你想要知道怎样开发 Android 的应用程序，你找对地方了。 Androidin开发论坛专门提供多种文档来帮助你学习   
Android 和开发基于该平台的移动应用程序。  
现在Android SDK 1.0版本已经正式推出. 它包括源码框架, 实例工程，开发工具，模拟器，当然还包括你所需要的开发Android应用的全部库文件。  
特性  
•	应用程序框架 支持组件的重用与替换   
•	Dalvik 虚拟机 专为移动设备优化   
•	集成的浏览器 基于开源的WebKit 引擎   
•	优化的图形库 包括定制的2D图形库，3D图形库基于OpenGL ES 1.0 （硬件加速可选）   
•	SQLite 用作结构化的数据存储   
•	多媒体支持 包括常见的音频、视频和静态图像格式 （如 MPEG4, H.264, MP3, AAC, AMR, JPG, PNG, GIF）   
•	GSM 电话技术 （依赖于硬件）
•	蓝牙Bluetooth, EDGE, 3G, 和 WiFi （依赖于硬件）  
•	照相机，GPS，指南针，和加速度计（accelerometer） （依赖于硬件）  
•	丰富的开发环境 包括设备模拟器，调试工具，内存及性能分析图表，和Eclipse集成开发环境插件   
Android 架构  
下图显示的是Android操作系统的主要组件。每一部分将会在下面具体描述。  
 
应用程序  
Android会同一系列核心应用程序包一起发布，该应用程序包包括email客户端，SMS短消息程序，日历，  
地图，浏览器，联系人管理程序等。所有的应用程序都是使用JAVA语言编写的。  
应用程序框架  
开发人员也可以完全访问核心应用程序所使用的API框架。该应用程序的架构设计简化了组件的重用；  
任何一个应用程序都可以发布它的功能块并且任何其它的应用程序都可以使用其所发布的功能块（不过得遵循框架的安全性限制）。  
同样，该应用程序重用机制也使用户可以方便的替换程序组件。  
隐藏在每个应用后面的是一系列的服务和系统, 其中包括；   
•	丰富而又可扩展的视图（Views），可以用来构建应用程序， 它包括列表（lists），网格（grids），  
文本框（text boxes），按钮（buttons）， 甚至可嵌入的web浏览器。   
•	内容提供器（Content Providers）使得应用程序可以访问另一个应用程序的数据（如联系人数据库）， 或者共享它们自己的数据   
•	资源管理器（Resource Manager）提供 非代码资源的访问，如本地字符串，图形，和布局文件（ layout files ）。   
•	通知管理器 （Notification Manager） 使得应用程序可以在状态栏中显示自定义的提示信息。   
•	活动管理器（ Activity Manager） 用来管理应用程序生命周期并提供常用的导航回退功能。   
有关更多的细节和怎样从头写一个应用程序，请参考 如何编写一个 Android 应用程序.  
程序库  
Android 包含一些C/C++库，这些库能被Android系统中不同的组件使用。它们通过 Android 应用程序框架为开发者提供服务。以下是一些核心库：  
•	系统 C 库 - 一个从 BSD 继承来的标准 C 系统函数库（ libc ）， 它是专门为基于 embedded linux 的设备定制的。   
•	媒体库 - 基于 PacketVideo OpenCORE；该库支持多种常用的音频、视频格式回放和录制，同时支持静态图像文件。编码格式包括MPEG4, H.264, MP3, AAC, AMR, JPG, PNG 。   
•	Surface Manager - 对显示子系统的管理，并且为多个应用程序提 供了2D和3D图层的无缝融合。   
•	LibWebCore - 一个最新的web浏览器引擎用，支持Android浏览器和一个可嵌入的web视图。   
•	SGL - 底层的2D图形引擎 
•	3D libraries - 基于OpenGL ES 1.0 APIs实现；该库可以使用硬件 3D加速（如果可用）或者使用高度优化的3D软加速。   
•	FreeType -位图（bitmap）和矢量（vector）字体显示。   
•	SQLite - 一个对于所有应用程序可用，功能强劲的轻型关系型数据库引擎。   
Android 运行库
Android 包括了一个核心库，该核心库提供了JAVA编程语言核心库的大多数功能。  
每一个Android应用程序都在它自己的进程中运行，都拥有一个独立的Dalvik虚拟 机实例。Dalvik被设计成一个设备可以同时高效地运行多个虚拟系统。   
Dalvik虚拟机执行（.dex）的Dalvik可执行文件，该格式文件针对小内存使用做了 优化。  
同时虚拟机是基于寄存器的，所有的类都经由JAVA编译器编译，然后通过SDK中 的 "dx" 工具转化成.dex格式由虚拟机执行。  
Dalvik虚拟机依赖于linux内核的一些功能，比如线程机制和底层内存管理机制。  
Linux 内核  
Android 的核心系统服务依赖于 Linux 2.6 内核，如安全性，内存管理，进程管理， 网络协议栈和驱动模型。  
Linux 内核也同时作为硬件和软件栈之间的抽象层。  
Android安装以及Eclipse插件  

文章出处:http://www.cnblogs.com/haix/archive/2007/11/14/959400.html  
SDK安装首先到到http://code.google.com/android/download.html  

下载SDK的压缩包，直接解压到你需要的目录里。里面的Emulator是一个智能手机模拟器。然后是安装Eclipse的开发插件。  

1）在Eclipse的菜单里选择Software Updates > Find and Install...  
2）在随后出现的窗口里选Search for new features to install，然后“下一步”  
3）点New Remote Site  
4）在这里随便给这个远程地址输入一个名字(比如Google Android)，在下面输入网址https://dl-ssl.google.com/android/eclipse/，  
然后点OK，退回到上一级对话框后点“完成”    
5）在随后结果窗口中，选择Android Plugin > Eclipse Integration > Android Development Tools，然后“下一步”  
6）接受license后再“下一步”，然后“完成”  
7）然后点Install All，安装完后重启Eclipse  
8）重新启动Eclipse后，在Window > Preferences... ，选择Android面板，然后后点Browse...把输入SDK的路径就完成了。  

调试配置:  
Eclipse   
1.选择RUN  
2.Open Run Dialog  
3.选择Android Application  
4. New(上面的小白纸).  
看我的文档  


然后你按照api说的配置run,然后就可以运行了，我运行的界面，在Android中的浏览器中搜索博客园的图片,  
 
用 Eclipse 开发 Android 应用程序  
Google Android Development Tools Eclipse 插件入门  
  
Android 应用程序 — 概述  
我们来看看 Android 应用程序的四种主要类型：活动、服务、接收器和 ContentProvider。我们还要看看显示用户界面（UI）元素的视图。  
活动  
活动是最常用的 Android 应用程序形式。活动在一个称为视图 的类的帮助下，为应用程序提供 UI。   
视图类实现各种 UI 元素，比如文本框、标签、按钮和计算平台上常见的其他 UI 元素。  
一个应用程序可以包含一个或多个活动。这些活动通常与应用程序中的屏幕形成一对一关系。  
应用程序通过调用 startActivity() 或 startSubActivity() 方法从一个活动转移到另一个活动。  
如果应用程序只需 “切换” 到新的活动，就应该使用前一个方法。如果需要异步的调用/响应模式，就使用后一个方法。  
在这两种情况下，都需要通过方法的参数传递一个 intent。  
由操作系统负责决定哪个活动最适合满足指定的 intent。  
  
服务和接收器  
与其他多任务计算环境一样，“在后台” 运行着一些应用程序，它们执行各种任务。  
Android 把这种应用程序称为 “服务”。服务是没有 UI 的 Android 应用程序。  
接收器是一个应用程序组件，它接收请求并处理 intent。与服务一样，接收器在一般情况下也没有 UI 元素。  
接收器通常在 AndroidManifest.xml 文件中注册。清单 2 是接收器代码的示例。注意，接收器的类属性是负责实现这个接收器的 Java 类。  

接收器代码  
                    
package com.msi.samplereceiver;

import android.content.Context;
import android.content.Intent;
import android.content.IntentReceiver;

public class myreceiver extends IntentReceiver 
{
	public void onReceiveIntent(Context arg0, Intent arg1) 
	{
		// do something when this method is invoked.
	}
}
  
用 ContentProvider 进行数据管理   
ContentProvider 是 Android 的数据存储抽象机制。我们以移动设备上常见的一种数据为例：地址簿或联系人数据库。  
地址簿包含所有联系人及其电话号码，用户在使用手机时可能需要使用这些数据。ContentProvider 对数据存储的访问方法进行抽象。  
ContentProvider 在许多方面起到数据库服务器的作用。对数据存储中数据的读写操作应该通过适当的 ContentProvider 传递，   
而不是直接访问文件或数据库。可能还有 ContentProvider 的 “客户机” 和 “实现”。  
下一节介绍 Android 视图，这是 Android 在移动设备屏幕上显示 UI 元素的机制。  
  
视图  
Android 活动通过视图显示 UI 元素。视图采用以下布局设计之一：  
LinearVertical   
后续的每个元素都排在前一个元素下面，形成一个单一列。   
LinearHorizontal   
后续的每个元素都排在前一个元素右边，形成一个单一行。   
Relative   
后续的每个元素相对于前一个元素有一定的偏移量。   
Table   
与 HTML 表相似的一系列行和列。每个单元格可以包含一个视图元素。   
选择一种布局（或布局的组合）之后，就可以用各个视图显示 UI。  
视图元素由大家熟悉的 UI 元素组成，包括：  
•	Button   
•	ImageButton   
•	EditText   
•	TextView（与标签相似）   
•	CheckBox   
•	Radio Button   
•	Gallery 和 ImageSwitcher（用来显示多个图像）   
•	List   
•	Grid   
•	DatePicker   
•	TimePicker   
•	Spinner（与组合框相似）   
•	AutoComplete（具有文本自动补全特性的 EditText）   
视图是在一个 XML 文件中定义的。清单 3 给出一个简单的 LinearVertical 布局示例。  

简单的 LinearVertical 布局  
                    
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    >
<TextView  
    android:layout_width="fill_parent" 
    android:layout_height="wrap_content" 
    android:text="Activity 1!"
    />
<TextView  
    android:layout_width="fill_parent" 
    android:layout_height="wrap_content" 
    android:text="Activity 1, second text view!"
    />
<Button
    android:layout_width="wrap_content" 
    android:layout_height="wrap_content" 
    android:text="Switch To Activity 2"
	id="@+id/switchto2"
	/>    
</LinearLayout>

注意，每个元素有一个或多个属于 Android 名称空间的属性。  
下一节讨论如何获取 Android SDK 并在 Eclipse 环境中配置它。  
用 Eclipse 开发 Android 应用程序  
Google Android Development Tools Eclipse 插件入门  
  
构建 SaySomething Android 应用程序  
本节要使用 Android Developer Tools 创建一个基本的 Android 应用程序，它称为 SaySomething。创建这个应用程序之后，将调试和运行它。  
New project 向导  
第一步是创建一个新项目。选择用来创建 Android 项目的向导，如下所示。  

图 2. New project 向导  
 
这个应用程序需要：  
•	Name   
•	Location    
•	Package name   
•	Activity name — 可以认为这是应用程序的主 “表单” 或屏幕   
•	Application name   
看看这个新项目。  

图 3. 新的 Android 项目  
   
这会创建一个默认的应用程序，可以构建和运行它。可以在 Package Explorer 中查看它的组件。  
  
Package Explorer  
Package Explorer（在 Eclipse 的 Java 透视图中）显示 Android 示例应用程序的所有组件，见图 4。  

图 4. Package Explorer  
 
需要注意的组件包括：  
src 文件夹   
包含示例应用程序的包，即 com.msi.ibmtutorial。   
R.java   
Android Developer Tools 自动创建这个文件，它提供访问 Android 应用程序的各种资源所需的常量。后面会详细讨论 R 类与资源之间的关系。   
SaySomething.java   
应用程序的主活动类的实现。   
Referenced libraries   
包含 android.jar，这是 Android SDK 中的 Android 运行时类的 jar 文件。   
res 文件夹   
包含应用程序的资源，包括：  
•	图标   
•	布局文件   
•	字符串   
AndriodManifest.xml   
示例应用程序的部署描述符。   
接下来，详细研究一下源代码。  
  
应用程序的主活动  
这个示例应用程序由一个活动组成，即 SaySomething。正如前面提到的，SaySomething 类是在 SaySomething.java 文件中实现的。  

清单 4. SaySomething.java
                    
package com.msi.ibmtutorial;

import android.app.Activity;
import android.os.Bundle;

public class SaySomething extends Activity 
{
    /** Called when the activity is first created. */
    @Override
    public void onCreate(Bundle icicle) 
   {
        super.onCreate(icicle);
        setContentView(R.layout.main);
    }
}

在这个源代码片段中，要注意几点：  
•	SaySomething 是一个普通的 Java 类，包含包和导入语句。   
•	SaySomething 扩展 android.app 包中的 Android 基类 Activity。   
•	onCreate() 方法是这个活动的入口点，它接受一个 Bundle 类型的参数。Bundle 类本质上是 map 或 hashmap 的包装器。  
在这个参数中传递构造活动所需的元素。本教程不讨论这个参数。   
•	setContentView(..) 负责用 R.layout.main 参数创建主 UI。R.layout.main 是应用程序资源中主布局的标识符。   
下一节讨论示例应用程序的资源。  
  
应用程序的资源  
正如前面提到的，Android 中的资源放在项目的 res 子目录中。资源分为三类：  
Drawables   
这个文件夹包含图形文件，比如图标和位图。   
Layouts   
这个文件夹包含表示应用程序布局和视图的 XML 文件。后面会详细研究这些文件。   
Values   
这个文件夹包含 strings.xml 文件。这是为应用程序实现字符串本地化的主要方法。   
下一节研究 main.xml 文件，了解示例应用程序的 UI 资源。  
  
main.xml
这个示例应用程序包含一个活动和一个视图。应用程序包含一个名为 main.xml 的文件，它代表活动的主 UI 的视觉方面。  
注意，在 main.xml 中没有指定在哪里使用这个布局。这意味着，如果需要的话，可以在多个活动中使用它。清单 5 给出布局文件的内容。  

清单 5. 布局文件
                    
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    >
<TextView  
    android:layout_width="fill_parent" 
    android:layout_height="wrap_content" 
    android:text="Hello World, SaySomething"
    />
</LinearLayout>

这是最简单的布局，其中只有一个垂直的线性布局，这意味着所有元素排成一列。  
这里有一个 TextView 元素，它与其他开发环境中的标签类似。TextView 代表不可编辑的静态文本。  
注意，每个视图元素（比如这个示例中的 LinearLayout 和 TextView）都有属于 Android 名称空间的属性。  
一些属性是所有视图元素都有的，比如 android:layout_width 和 android:layout_height。这些属性可以采用的值是：  
fill_parent   
使视图元素占满可用的空间。也可以认为这就是 “拉伸”。   
wrap_content   
这个值让 Android 把元素一个接一个地排列，不进行拉伸。   
在构建期间，对所有资源进行编译。编译过程的输出之一是 R.java 文件，这个文件向应用程序的其余部分提供资源。下面讨论 R.java 文件。  
  
R.java  
R.java 文件是在构建时自动创建的，所以不要手工修改它，因为所有修改都会丢失。清单 6 给出这个示例应用程序的 R.java 文件。  

清单 6. R.java 文件  
                    
/* AUTO-GENERATED FILE.  DO NOT MODIFY.
 *
 * This class was automatically generated by the
 * aapt tool from the resource data it found.  It
 * should not be modified by hand.
 */

package com.msi.ibmtutorial;

public final class R {
    public static final class attr {
    }
    public static final class drawable {
        public static final int icon=0x7f020000;
    }
    public static final class layout {
        public static final int main=0x7f030000;
    }
    public static final class string {
        public static final int app_name=0x7f040000;
    }
}

R 类包含一些匿名子类，每个子类包含前面描述的各种资源的标识符。注意，这些类都是静态的。  
请注意 R.layout.main 代表的元素。这个标识符代表由 main.xml 定义的布局。  
在活动的 onCreate 方法中使用过这个值：setContentView(R.layout.main);。  
这就是在运行时把特定的活动（在这个示例中是 SayAnything）和特定的布局（主布局）联系在一起的方法。  
  
构建应用程序  
在默认情况下，每次保存文件时，都将对它们进行编译。  

图 5. 错误面板
 
我们在源代码中引入了一个错误，即在 setContent 和 View 之间加了一个空格。  
在保存这个文件时，它被编译并在屏幕底部的 Problems 面板中显示错误。  
在源代码中纠正这个错误之后，应用程序就能够成功编译，并从问题列表中删除错误。  
  
AndroidManifest.xml  
AndroidManifest.xml 文件是 Android 应用程序的部署描述符。这个文件列出应用程序中包含的所有活动、服务、内容提供器和接收器，  
以及应用程序支持的 IntentFilter。下面是这个示例应用程序的完整的 AndroidManifest.xml 文件。  

清单 7. AndroidManifest.xml 文件
                    
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    package="com.msi.ibmtutorial">
    <application android:icon="@drawable/icon">
        <activity class=".SaySomething" android:label="@string/app_name">
            <intent-filter>
                <action android:value="android.intent.action.MAIN" />
                <category android:value="android.intent.category.LAUNCHER" />
            </intent-filter>
        </activity>
    </application>
</manifest>

请注意以下情况：  
•	这里指定了源文件中的包名。这里采用与 Java 源文件和导入语句相似的模式。<manifest> 标记的实际作用是 “导入” 这个包中的类。  
在这个文件中，所有非完全限定的类都属于 package 属性指定的包。   
•	<application> 标记的一个属性引用了应用程序的一个资源。请注意 drawable 标识符前面的 @ 符号。  
这里的意思是，在应用程序资源的 drawable 文件夹中寻找名为 “icon” 的资源。   
•	<activity> 标记包含以下属性和值：  
o	class 属性表示实现这个活动的 Java 类。     
o	android:label 是应用程序的名称。注意，它来自一个字符串资源。string.xml 文件包含应用程序的本地化字符串。   
o	<intent-filter> 表示应用程序中可用的 IntentFilter。这是 Android 应用程序中最常见的 IntentFilter。这个过滤器的实际意思是，它实现 “主” 操作（也就是入口点），而且它位于 OS 的启动器中。这意味着可以在 Android 设备上像启动其他应用程序一样，从应用程序主列表中启动它。   
下一节讨论如何在 Eclipse 中的 Android 模拟器上启动应用程序。  
  
运行应用程序  
应用程序已经成功地编译了，现在该运行这个示例应用程序了。在 Eclipse 中选择 Open Run Dialog 或工具栏上的快捷按钮。  
这会打开一个对话框，可以在这里创建启动配置。选择 Android Application 选项并单击 New 的图标。  
图 6 显示本教程示例所用的值。

图 6. Run 对话框
 
指定配置名称。本教程使用的名称是 Tutorial Configuration。在可用项目列表中选择 ibmtutorial 项目（单击 Browse 可以看到可用项目）。  
在下拉列表中选择启动活动。现在选择 Emulator 选项卡，根据需要指定模拟器设置。可以保持默认设置。有两个设置需要注意，见图 7。  

图 7. Run 对话框，Emulator 选项卡  
 
有几种可供选择的屏幕大小和方向，还有网络选择。如果运行应用程序的移动设备的因特网连接速度不同，网络选择就很重要了。  
在构造应用程序原型时，选择完整网络速度而且没有延迟。开发了主要功能之后，最好在比较真实的网络环境中进行测试，  
看看应用程序的响应速度如何。  
选择 Run 运行示例应用程序。   

图 8. 模拟器
 
应用程序已经在模拟器上运行了，现在看看幕后发生的情况。Dalvik Debug Monitor Service（DDMS）将会帮助检查应用程序的运行情况。  
  
调试应用程序  
要想检查正在运行的应用程序中发生了什么情况，就需要查看正在运行的 Dalvik VM。在 Eclipse 中，选择 Window > Open Perspective > Other。  
在出现的对话框中选择 DDMS。这会在 Eclipse 中打开一个新的透视图，其中有许多有趣的窗口。下面简要介绍一下 DDMS 透视图中提供的资源：  
LogCat 是一个日志文件，它记录 VM 中发生的活动。应用程序可以通过 Log.i(tag,message); 在这个日志文件中添加自己的日志项，  
其中的 tag 和 message 都是 Java 字符串。Log 类属于 android.util.Log 包。  
图 9 显示 LogCat。  

图 9. LogCat   
 
DDMS 中的另一个方便的工具是文件管理器，可以用它访问模拟器的文件系统。图 10 显示在模拟器上部署本教程示例应用程序的位置。  

图 10. 在模拟器上部署的示例应用程序  
 
用户应用程序部署在 /data/app 目录中，而 Android 内置的应用程序部署在 /system/app 目录中。  
在 DDMS 中还可以查看正在运行的进程。  

图 11. 正在运行的进程列表  
 
全面讨论 Android 应用程序的调试超出了本教程的范围，更多信息请参见 参考资料。  

现在的智能手机操作系统已经进入战国时代，老牌的Symbian、Windows Mobile和BREW面临着iPhone和Android等新势力的巨大挑战。
最近有些闲暇时间了，可以研究下新手机操作系统的应用程序开发了。下一代的手机内置功能将不再是决定因素，  
如何让第三方快速开发手机上的应用将是兵家必争的制高点。  
  我是一个Windows Mobile程序员，而且也做了很久，为什么在新的手机操作系统里选择Android？因为Android和Windows Mobile太像了，  
  为什么这么说？  
  1，  都是操作系统与手机硬件分离模式，最有趣的是硬件供应商竟然是一家；  
  2，  可以使用托管代码来进行开发(.NET CF和Java)  
  3，  免费发布的SDK  
  4，  IDE集成式开发环境（Visual Studio和Eclipse）  
  5，  强大的服务器端软件支持（Windows Server、SQL Server、Exchange和Google Online Service）  
  所以说，从技术方向上来说，Windows Mobile和Android是相同技术的不同实现，体现了以软件和在线服务为核心的思想，  
  区别于iPhone和Symbian的以手机为核心的思路。现在还说不好这两种思路谁对谁错。  
  但是，我不选择iPhone还有一个非常重要的原因：我没有Mac电脑，所以无法搭建开发环境。  
  如果将来iPhone落败，这将是一个非常致命的失误。  
  开发环境
 
  好了，先来介绍一下开发环境，我的操作系统是Windows Vista，没有安装Visual Studio开发工具（不是我平时的工作用机）。  
第一步是访问Android主页，通过Google是很容易访问到的。必须承认，Android文档已经比我半年前访问时有很大的提高了，  
可以很容易地找到如何安装开发环境的指南。对于我们这些非Java 开发者来说，这非常有用。  
用代码来改变屏幕（垂直或水平）  
摘自：www.androidin.com

android.view.IWindowManager windowService = android.view.IWindowManager.Stub.asInterface(
android.os.ServiceManager.getService("window"));

try
{
     if (windowService.getOrientation() == 0)    //Orientation vertical
      {
    windowService.setOrientation(1);  //Orientation horizontal
    Log.i("info", "orientation 1 "+windowService.getOrientation());
      }
     else
     {
     Log.i("info", "orientation 0 "+windowService.getOrientation());
     }                        
}
catch (DeadObjectException e)
{
    e.printStackTrace();
}

TOP 
Android程序开发初级教程(二)
摘自：http://blog.csdn.net/k7sem
作者：关文柏

将界面实现用XML编排



你刚刚完成的"Hello, World"例子我们称之为”程序化”的界面编排。意思就是说构建你的应用程序界面是直接使用的源代码。如果你已经完成过很多界面程序，你大概熟悉像此类的方式是多么脆弱：一个对布局小小的修改会对源代码造成很头疼的事情。如果忘掉与View的紧密结合，这个导致代码出错和浪费你的调试时间的界面问题也会很简单。



这就是为什么Android提供了一种可替换的界面构建方式: 基于XML的布局文件。最简单的解释这个概念的方式就是展示一个例子。 我们就用刚才创建的项目来进行演示，达到相同的界面效果。



<?xml version="1.0" encoding="utf-8"?>

<TextView xmlns:android="http://schemas.android.com/apk/res/android"

  android:layout_width="fill_parent"

  android:layout_height="fill_parent"

  android:text="Hello, Android"/>



AndroidXML布局文件的大体的结构很简单。 它是一个标签的树，任何一个标签就是View类的名字。在这个例子中, 它是一个很简单的只有一个元素的树，一个 TextView。 你可以使用任何继承自View类的名字作为标签的名字。包括在你的代码中自定义的View类。这个结构可以很容易的构建界面，它比你在源代码中使用的结构和语法更简单。这个模式的设计灵感来自于Web开发。 就是可以将界面和应用程序逻辑分离的模式。



在这个例子中， 也有些是XML的属性，下面是他们的含义:



属性
含义

xmlns:android
        

这是XML命名空间的声明,它是告诉Android的工具, 你将要涉及到公共的属性已被定义在XML命名空间。在每一个Android的布局文件的最外边的标签必须有这个属性。

android:layout_width
        

这个属性定义了在屏幕上这个View可用的宽度是多少。

android:layout_height
        

这个属性定义了在屏幕上这个View可用的高度是多少。

android:text
        

设置TextView所包含的文本内容，当前设置为”Hello, Android”信息





以上就是一个XML布局文件的样子，但是你需要放在哪里？它要放在你的项目目录的res/ 文件夹下。 “res”是”resources”的缩写，它是存放所有非代码资源的文件夹，包含象图片，本地化字符串和XML布局文件。

这些Eclipse的插件已经给你创建好了，在我们上面的例子中，我们没有使用它。在包浏览器中，展开res目录的layout. 并且编辑 main.xml, 替换掉那个文本内容，然后保存。



现在，在包浏览状态，打开在代码文件夹中名为 R.java的文件， 你将看到下面的内容：



public final class R {

    public static final class attr {

    };

    public static final class drawable {

        public static final int icon=0x7f020000;

    };

    public static final class layout {

        public static final int main=0x7f030000;

    };

    public static final class string {

        public static final int app_name=0x7f040000;

    };

};

  
一个项目的R.java文件是一个定义所有资源的索引文件。 使用这个类就像使用一种速记方式来引用你项目中包含的资源。这个有点特别的强大像对于Eclipse这类IDE的代码编译特性，因为它使你快速的，互动式的定位你正在寻找的特定引用。



到目前需要注意的重要事情是叫做”layout”的内部类和他的成员变量”main”, 插件会通知你添加一个新的XML布局文件，然后从新产生这个R.java文件，比如你添加了新的资源到你的项目，你将会看到R.java也相应的改变了



最后重要的事情是你需要去修改你的HelloAndroid源代码，去使用新的XML布局你的界面。替换掉编码式的界面模式。下面是你的新代码的样子，你可以看到，代码变得更加简单了。



public class HelloAndroid extends Activity {

    /** Called when the activity is first created. */

    @Override

    public void onCreate(Bundle icicle) {

        super.onCreate(icicle);

        setContentView(R.layout.main);

    }

}



当你做这些改变的时候，不要仅仅复制，粘贴到你的代码中，尝试去体验R.java的代码编译特点。你会发现它对你有很大的帮助。



现在完成这些改变以后，你就可以重新运行你的程序，然后你会发现两种不同的界面编排方式会产生同样的效果。



补充：可能与原文有些意思不同，笔者水平有限，请包含，下面是原始链接地址。
Eclipse开发Google Android应用程序教程(一)
摘自：www.knitdream.com

Android 应用程序 — 概述

我们来看看 Android 应用程序的四种主要类型：活动、服务、接收器和 ContentProvider。我们还要看看显示用户界面（UI）元素的视图。

活动

活动是最常用的 Android 应用程序形式。活动在一个称为视图 的类的帮助下，为应用程序提供 UI。视图类实现各种 UI 元素，比如文本框、标签、按钮和计算平台上常见的其他 UI 元素。

一个应用程序可以包含一个或多个活动。这些活动通常与应用程序中的屏幕形成一对一关系。

应用程序通过调用 startActivity() 或 startSubActivity() 方法从一个活动转移到另一个活动。如果应用程序只需 “切换” 到新的活动，就应该使用前一个方法。如果需要异步的调用/响应模式，就使用后一个方法。在这两种情况下，都需要通过方法的参数传递一个 intent。

由操作系统负责决定哪个活动最适合满足指定的 intent。


服务和接收器

与其他多任务计算环境一样，“在后台” 运行着一些应用程序，它们执行各种任务。Android 把这种应用程序称为 “服务”。服务是没有 UI 的 Android 应用程序。

接收器是一个应用程序组件，它接收请求并处理 intent。与服务一样，接收器在一般情况下也没有 UI 元素。接收器通常在 AndroidManifest.xml 文件中注册。清单 2 是接收器代码的示例。注意，接收器的类属性是负责实现这个接收器的 Java 类。


清单 2. 接收器代码

package com.msi.samplereceiver;

import android.content.Context;
import android.content.Intent;
import android.content.IntentReceiver;

public class myreceiver extends IntentReceiver
{
public void onReceiveIntent(Context arg0, Intent arg1)
{
// do something when this method is invoked.
}
}


用 ContentProvider 进行数据管理

ContentProvider 是 Android 的数据存储抽象机制。我们以移动设备上常见的一种数据为例：地址簿或联系人数据库。地址簿包含所有联系人及其电话号码，用户在使用手机时可能需要使用这些数据。ContentProvider 对数据存储的访问方法进行抽象。ContentProvider 在许多方面起到数据库服务器的作用。对数据存储中数据的读写操作应该通过适当的 ContentProvider 传递，而不是直接访问文件或数据库。可能还有 ContentProvider 的 “客户机” 和 “实现”。

下一节介绍 Android 视图，这是 Android 在移动设备屏幕上显示 UI 元素的机制。


视图

Android 活动通过视图显示 UI 元素。视图采用以下布局设计之一：

LinearVertical
后续的每个元素都排在前一个元素下面，形成一个单一列。
LinearHorizontal
后续的每个元素都排在前一个元素右边，形成一个单一行。
Relative
后续的每个元素相对于前一个元素有一定的偏移量。
Table
与 HTML 表相似的一系列行和列。每个单元格可以包含一个视图元素。
选择一种布局（或布局的组合）之后，就可以用各个视图显示 UI。

视图元素由大家熟悉的 UI 元素组成，包括：

Button
ImageButton
EditText
TextView（与标签相似）
CheckBox
Radio Button
Gallery 和 ImageSwitcher（用来显示多个图像）
List
Grid
DatePicker
TimePicker
Spinner（与组合框相似）
AutoComplete（具有文本自动补全特性的 EditText）
视图是在一个 XML 文件中定义的。清单 3 给出一个简单的 LinearVertical 布局示例。


清单 3. 简单的 LinearVertical 布局

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
android:orientation="vertical"
android:layout_width="fill_parent"
android:layout_height="fill_parent"
>
<TextView
android:layout_width="fill_parent"
android:layout_height="wrap_content"
android:text="Activity 1!"
/>
<TextView
android:layout_width="fill_parent"
android:layout_height="wrap_content"
android:text="Activity 1, second text view!"
/>
<Button
android:layout_width="wrap_content"
android:layout_height="wrap_content"
android:text="Switch To Activity 2"
id="@+id/switchto2"
/>
</LinearLayout>


注意，每个元素有一个或多个属于 Android 名称空间的属性。

下一节讨论如何获取 Android SDK 并在 Eclipse 环境中配置它。
Eclipse开发Google Android应用程序教程(二)
摘自：www.knitdream.com

Android Software Developer Kit

我们已经大致了解了 Android 平台，现在讨论如何设置 Eclipse 环境来支持 Android 应用程序开发。本节讨论如何获取 Android SDK 并在 Eclipse 环境中配置它。

获取和安装 Eclipse

如果您还没有安装 Eclipse，那么从 Eclipse Foundation 下载并安装 Eclipse IDE 最新的稳定版。安装包是一个压缩的文件夹。把这个文件夹的内容解压到您计算机上的适当位置。安装程序并不在 Windows® 上创建任何图标或快捷方式。对于本教程，Eclipse 文件夹位于 c:\software\eclipse 目录。

双击 eclipse 安装目录中的 eclipse.exe 启动 Eclipse。这会启动 IDE。软件提示您指定一个 “工作空间” 并建议一个默认位置，比如 c:\documents and settings\username\workspace。选择这个位置或者指定另一个工作空间位置。

启动 Eclipse 之后，单击主屏幕上的 Workbench - Go to the workbench 图标。

现在该获取 Android SDK 了。

获取和安装 Android SDK

有针对 Windows、Mac OS X（只有 Intel® 版）和 Linux（i386）的 SDK 安装版。选择适合您平台的最新的 SDK 版本。注意，到编写本教程时，最新的 Android SDK 版本是 m3-rc37a。

Android SDK 是一个压缩的文件夹。下载这个文件夹并把它的内容解压到您计算机上的适当位置。对于本教程，SDK 安装在 c:\software\google\android_m3-rc37a。显然，如果要在 Mac OS X 和 Linux 上安装 SDK，应该安装在通常安装开发工具的位置。

Eclipse 和 Android SDK 都已经安装好了。现在应该安装 Eclipse 插件。

获取并安装 Eclipse 插件

下面介绍安装 Eclipse 插件 Android Developer Tools 的步骤。注意，Android 网站上也提供了安装说明。

按照以下步骤安装 Android Developer Tools：

   1. 在 Eclipse 中运行 “Find and Install” 特性（在 Help > Software Updates 菜单下面）。
   2. 选择 Search for new features to install 选项。
   3. 选择 New Remote Site。给站点命名，比如 “Android Developer Tools”。
   4. 在对话框中输入以下 URL：https://dl-ssl.google.com/android/eclipse。注意，这个 URL 使用 HTTPS 协议。这是一个安全的下载。

      图 1. New Update Site



   5. 列表中会增加一个新条目并被默认选中。单击 Finish。搜索结果会显示 Android Developer Tools。选择 Developer Tools 并单击 Next。
   6. 阅读并接受许可协议之后，单击 Next。注意，许可协议中对于使用 Google Maps API 有一个特殊的要求。
   7. 检查并接受安装位置，然后单击 Finish。

现在下载并安装这个插件。这个插件没有经过数字签名（到编写本教程时），所以只需单击 Install All，然后重新启动 Eclipse。

配置 Eclipse 插件

重新启动 Eclipse 之后，应该把这个插件连接到 SDK 的安装位置。在 Window 菜单中选择 Preferences。单击左边树视图中的 Android。在右边的面板中，指定 SDK 的安装位置。本教程使用的安装位置是 c:\software\google\android\m3-rc37a（同样，在 Mac OS X 和 Linux 系统上也应该使用适当的位置）。

指定 SDK 安装位置之后，可以配置另外三部分设置。下面简要介绍一下：

    * Build 部分中的选项用来自动地重新构建资源。保持这个选项的设置不变。Build 选项可以改变输出的详细程度。Normal 是默认设置。
    * DDMS — Dalvik Debug Monitor Service 用来监视正在运行的 VM。这些设置指定调试器用来连接 VM 的 TCP/IP 端口号、各个日志记录级别和选项。默认设置应该是合适的。
    * LogCat — 这是在底层 Linux 系统上创建的一个日志文件。可以在这个对话框中选择字体。根据需要调整这个选项。

好了！Eclipse 环境已经设置好了，可以开始创建 Android 应用程序了。
Eclipse开发Google Android应用程序教程(三)
摘自：www.knitdream.com

构建 SaySomething Android 应用程序

本节要使用 Android Developer Tools 创建一个基本的 Android 应用程序，它称为 SaySomething。创建这个应用程序之后，将调试和运行它。New project 向导

第一步是创建一个新项目。选择用来创建 Android 项目的向导，如下所示。

图 2. New project 向导



这个应用程序需要：

Name

Location

Package name

Activity name — 可以认为这是应用程序的主 “表单” 或屏幕

Application name

看看这个新项目。

图 3. 新的 Android 项目



这会创建一个默认的应用程序，可以构建和运行它。可以在 Package Explorer 中查看它的组件。

Package Explorer

Package Explorer（在 Eclipse 的 Java 透视图中）显示 Android 示例应用程序的所有组件，见图 4。

图 4. Package Explorer



需要注意的组件包括：
src 文件夹
包含示例应用程序的包，即 com.msi.ibmtutorial。
R.java
Android Developer Tools 自动创建这个文件，它提供访问 Android 应用程序的各种资源所需的常量。后面会详细讨论 R 类与资源之间的关系。
SaySomething.java
应用程序的主活动类的实现。
Referenced libraries
包含 android.jar，这是 Android SDK 中的 Android 运行时类的 jar 文件。
res 文件夹
包含应用程序的资源，包括：
图标布局文件
字符串
AndriodManifest.xml
示例应用程序的部署描述符。
接下来，详细研究一下源代码。
应用程序的主活动
这个示例应用程序由一个活动组成，即 SaySomething。正如前面提到的，SaySomething 类是在 SaySomething.java 文件中实现的。
清单 4. SaySomething.java
package com.msi.ibmtutorial;

import android.app.Activity;

import android.os.Bundle;

public class SaySomething extends Activity

{

    /** Called when the activity is first created. */

    @Override

    public void onCreate(Bundle icicle)

   {

        super.onCreate(icicle);

        setContentView(R.layout.main);

    }

}


在这个源代码片段中，要注意几点：
SaySomething 是一个普通的 Java 类，包含包和导入语句。

SaySomething 扩展 android.app 包中的 Android 基类 Activity。

onCreate() 方法是这个活动的入口点，它接受一个 Bundle 类型的参数。Bundle 类本质上是 map 或 hashmap 的包装器。在这个参数中传递构造活动所需的元素。本教程不讨论这个参数。

setContentView(..) 负责用 R.layout.main 参数创建主 UI。R.layout.main 是应用程序资源中主布局的标识符。

下一节讨论示例应用程序的资源。

应用程序的资源

正如前面提到的，Android 中的资源放在项目的 res 子目录中。资源分为三类：

Drawables

这个文件夹包含图形文件，比如图标和位图。

Layouts

这个文件夹包含表示应用程序布局和视图的 XML 文件。后面会详细研究这些文件。

Values

这个文件夹包含 strings.xml 文件。这是为应用程序实现字符串本地化的主要方法。

下一节研究 main.xml 文件，了解示例应用程序的 UI 资源。

main.xml

这个示例应用程序包含一个活动和一个视图。应用程序包含一个名为 main.xml 的文件，它代表活动的主 UI 的视觉方面。注意，在 main.xml 中没有指定在哪里使用这个布局。这意味着，如果需要的话，可以在多个活动中使用它。清单 5 给出布局文件的内容。

清单 5. 布局文件

<?xml version="1.0" encoding="utf-8"?>

<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"

    android:orientation="vertical"

    android:layout_width="fill_parent"

    android:layout_height="fill_parent"

    >

<TextView

    android:layout_width="fill_parent"

    android:layout_height="wrap_content"

    android:text="Hello World, SaySomething"

    />

</LinearLayout>

这是最简单的布局，其中只有一个垂直的线性布局，这意味着所有元素排成一列。这里有一个 TextView 元素，它与其他开发环境中的标签类似。TextView 代表不可编辑的静态文本。

注意，每个视图元素（比如这个示例中的 LinearLayout 和 TextView）都有属于 Android 名称空间的属性。一些属性是所有视图元素都有的，比如 android:layout_width 和 android:layout_height。这些属性可以采用的值是：
fill_parent
使视图元素占满可用的空间。也可以认为这就是 “拉伸”。
wrap_content
这个值让 Android 把元素一个接一个地排列，不进行拉伸。
在构建期间，对所有资源进行编译。编译过程的输出之一是 R.java 文件，这个文件向应用程序的其余部分提供资源。下面讨论 R.java 文件。
R.java
R.java 文件是在构建时自动创建的，所以不要手工修改它，因为所有修改都会丢失。清单 6 给出这个示例应用程序的 R.java 文件。
清单 6. R.java 文件
      
/* AUTO-GENERATED FILE. DO NOT MODIFY.

*

* This class was automatically generated by the

* aapt tool from the resource data it found. It

* should not be modified by hand.

*/

package com.msi.ibmtutorial;

public final class R {

    public static final class attr {

    }

    public static final class drawable {

        public static final int icon=0x7f020000;

    }

    public static final class layout {

        public static final int main=0x7f030000;

    }

    public static final class string {

        public static final int app_name=0x7f040000;

    }

}

R 类包含一些匿名子类，每个子类包含前面描述的各种资源的标识符。注意，这些类都是静态的。
请注意 R.layout.main 代表的元素。这个标识符代表由 main.xml 定义的布局。在活动的 onCreate 方法中使用过这个值：setContentView(R.layout.main);。这就是在运行时把特定的活动（在这个示例中是 SayAnything）和特定的布局（主布局）联系在一起的方法。
构建应用程序
在默认情况下，每次保存文件时，都将对它们进行编译。
图 5. 错误面板



我们在源代码中引入了一个错误，即在 setContent 和 View 之间加了一个空格。在保存这个文件时，它被编译并在屏幕底部的 Problems 面板中显示错误。在源代码中纠正这个错误之后，应用程序就能够成功编译，并从问题列表中删除错误。
AndroidManifest.xml
AndroidManifest.xml 文件是 Android 应用程序的部署描述符。这个文件列出应用程序中包含的所有活动、服务、内容提供器和接收器，以及应用程序支持的 IntentFilter。下面是这个示例应用程序的完整的 AndroidManifest.xml 文件。
清单 7. AndroidManifest.xml 文件
<?xml version="1.0" encoding="utf-8"?>

<manifest xmlns:android="http://schemas.android.com/apk/res/android"

    package="com.msi.ibmtutorial">

    <application android:icon="@drawable/icon">

        <activity class=".SaySomething" android:label="@string/app_name">

            <intent-filter>

                <action android:value="android.intent.action.MAIN" />

                <category android:value="android.intent.category.LAUNCHER" />

            </intent-filter>

        </activity>

    </application>

</manifest>
请注意以下情况：
这里指定了源文件中的包名。这里采用与 Java 源文件和导入语句相似的模式。<manifest> 标记的实际作用是 “导入” 这个包中的类。在这个文件中，所有非完全限定的类都属于 package 属性指定的包。
<application> 标记的一个属性引用了应用程序的一个资源。请注意 drawable 标识符前面的 @ 符号。这里的意思是，在应用程序资源的 drawable 文件夹中寻找名为 “icon” 的资源。
<activity> 标记包含以下属性和值：
class 属性表示实现这个活动的 Java 类。
android:label 是应用程序的名称。注意，它来自一个字符串资源。string.xml 文件包含应用程序的本地化字符串。
<intent-filter> 表示应用程序中可用的 IntentFilter。这是 Android 应用程序中最常见的 IntentFilter。这个过滤器的实际意思是，它实现 “主” 操作（也就是入口点），而且它位于 OS 的启动器中。这意味着可以在 Android 设备上像启动其他应用程序一样，从应用程序主列表中启动它。
下一节讨论如何在 Eclipse 中的 Android 模拟器上启动应用程序。
运行应用程序
应用程序已经成功地编译了，现在该运行这个示例应用程序了。在 Eclipse 中选择 Open Run Dialog 或工具栏上的快捷按钮。这会打开一个对话框，可以在这里创建启动配置。选择 Android Application 选项并单击 New 的图标。
图 6 显示本教程示例所用的值。



图 6. Run 对话框

指定配置名称。本教程使用的名称是 Tutorial Configuration。在可用项目列表中选择 ibmtutorial 项目（单击 Browse 可以看到可用项目）。在下拉列表中选择启动活动。现在选择 Emulator 选项卡，根据需要指定模拟器设置。可以保持默认设置。有两个设置需要注意，见图 7。

图 7. Run 对话框，Emulator 选项卡



有几种可供选择的屏幕大小和方向，还有网络选择。如果运行应用程序的移动设备的因特网连接速度不同，网络选择就很重要了。在构造应用程序原型时，选择完整网络速度而且没有延迟。开发了主要功能之后，最好在比较真实的网络环境中进行测试，看看应用程序的响应速度如何。

选择 Run 运行示例应用程序。

图 8. 模拟器



应用程序已经在模拟器上运行了，现在看看幕后发生的情况。Dalvik Debug Monitor Service（DDMS）将会帮助检查应用程序的运行情况。

调试应用程序

要想检查正在运行的应用程序中发生了什么情况，就需要查看正在运行的 Dalvik VM。在 Eclipse 中，选择 Window > Open Perspective > Other。在出现的对话框中选择 DDMS。这会在 Eclipse 中打开一个新的透视图，其中有许多有趣的窗口。下面简要介绍一下 DDMS 透视图中提供的资源：

LogCat 是一个日志文件，它记录 VM 中发生的活动。应用程序可以通过 Log.i(tag,message); 在这个日志文件中添加自己的日志项，其中的 tag 和 message 都是 Java 字符串。Log 类属于 android.util.Log 包。

图 9 显示 LogCat。



图 9. LogCat

DDMS 中的另一个方便的工具是文件管理器，可以用它访问模拟器的文件系统。图 10 显示在模拟器上部署本教程示例应用程序的位置。

图 10. 在模拟器上部署的示例应用程序



用户应用程序部署在 /data/app 目录中，而 Android 内置的应用程序部署在 /system/app 目录中。

在 DDMS 中还可以查看正在运行的进程。

图 11. 正在运行的进程列表
GPhone开发包Android SDK含了很多丰富的类库：

　　android.util 涉及系统底层的辅助类库

　　android.os 提供了系统服务、消息传输、IPC管道

　　android.graphics GPhone图形库，包含了文本显示、输入输出、文字样式

　　android.database 包含底层的API操作数据库(SQLite)

　　android.content 提供了各种数据传输、服务、资源管理

　　android.view 提供基础的用户界面接口框架

　　android.widget 显示各种控件如按钮、列表框、进度条等。

　　android.app 提供高层的程序模型、提供基本的运行环境

　　android.provider 各种定义变量标准

　　android.telephony 提供与拨打电话相关的API交互

　　android.webkit GPhone默认浏览器操作接口
将视频播放器添加新功能<快进，快退，时间显示等>
摘自：www.androidin.com

实现:影片播放进度条,快进、快退,
影片播放进度条显示截图:
 

快进、快退还不够理想！
全屏，影片不能全屏！
其中，单击屏幕，全屏。按“空格”键，还原！
 

影片全屏和转向还没有解决!
package org.hqx.android.surfaceiewvedio;

import java.io.IOException;
import java.sql.Time;

import android.app.Activity;
import android.media.MediaPlayer;
import android.os.Bundle;
import android.os.Handler;
import android.view.KeyEvent;
import android.view.Surface;
import android.view.SurfaceHolder;
import android.view.SurfaceView;
import android.view.View;
import android.view.WindowManager;
import android.view.View.OnClickListener;
import android.widget.Button;
import android.widget.ProgressBar;
import android.widget.TextView;

public class SurfaceViewVedio extends Activity {
        private SurfaceHolder hold = null;
        private SurfaceView mPreview = null;
        private MediaPlayer mp = null ;
        private Surface su = null;
        private ProgressBar progressbar  = null;
        private Button btnplay = null;
        private Button btnstoo = null;
        private TextView text1 = null;
        private TextView text2 = null;
        private Button btnPAUSED = null;
        private Button btnaddgo = null;
        private Button btnaddback = null;
      
        private MediaPlayerState        mediaPlayerState        = MediaPlayerState.STOPPED;
        private enum MediaPlayerState
        {
                STOPPED, PLAYING, PAUSED
        }
      
        private HandlerInvocation        handlerInvocation        = new HandlerInvocation();
        private Handler                                timerHandler                = new Handler();
        private final int                        updateInterval                = 500;
      
        final private String currentFilePath = "/sdcard/android/kongfu.mp4";
   
      
      
        @Override
    public void onCreate(Bundle icicle) {
        super.onCreate(icicle);
        setContentView(R.layout.main);
        mPreview = (SurfaceView)this.findViewById(R.id.surface);
        btnplay = (Button)this.findViewById(R.id.butcnplay);
        btnstoo =(Button)this.findViewById(R.id.butcnstoo);
        btnPAUSED = (Button)this.findViewById(R.id.butcnpause);
        text1 =(TextView)this.findViewById(R.id.textv1);
        text2 =(TextView)this.findViewById(R.id.textv2);
        
        btnaddgo = (Button)this.findViewById(R.id.addgo);
        btnaddback = (Button)this.findViewById(R.id.addback);
        
        progressbar = (ProgressBar)this.findViewById(R.id.progress_horizontal);
        
                // requestWindowFeature(Window.FEATURE_NO_TITLE);
        
        mPreview.setOnClickListener(new OnClickListener(){   
                public void onClick(View arg0) {
                                 hold.setFixedSize(getWindowManager().getDefaultDisplay().getWidth(),
                                                          getWindowManager().getDefaultDisplay().getHeight());
                                             getWindow().setFlags(WindowManager.LayoutParams.FLAG_NO_STATUS_BAR,
                                                                         WindowManager.LayoutParams.FLAG_NO_STATUS_BAR);
                            }
                                });
        
        btnstoo.setOnClickListener(new OnClickListener(){

                        public void onClick(View arg0) {
                                mediaPlayerStop();      
                    }
        });  
        
        btnPAUSED.setOnClickListener(new OnClickListener(){

                        public void onClick(View arg0) {
                                mediaPlayerPause();      
                    }
        });  
      
        btnplay.setOnClickListener(new OnClickListener(){

                        public void onClick(View arg0) {
                                try {
                                                hold = mPreview.getHolder();
                                            su = hold.getSurface();
                                            mediaPlayerPlay();                                                        
                                } catch (IllegalArgumentException e) {
                                        // TODO Auto-generated catch block
                                        e.printStackTrace();
                                }
                    }
        });
        
        btnaddgo.setOnClickListener(new OnClickListener(){

                        public void onClick(View arg0) {
                                
                                addgo();
                        }
               
               
        });
        
        
        btnaddback.setOnClickListener(new OnClickListener(){

                        public void onClick(View arg0) {
                                addback();                                 
                        }
               
               
        });
        
    }

        @Override
        public boolean onKeyUp(int keyCode, KeyEvent event) {
                if(keyCode == KeyEvent.KEYCODE_SPACE ){
                        hold.setFixedSize(480,240);
                        return true;
                }
                return false;
        }
      
      
        private class HandlerInvocation implements Runnable
        {
                public void run()
                {
                        displayProgress();
                        timerHandler.postDelayed(handlerInvocation, updateInterval);
                }

        };
      
        private void displayProgress() {
                Time progress = new Time(mp.getCurrentPosition());
                Time remaining = new Time(mp.getDuration()-mp.getCurrentPosition());
                text1.setText(progress.toString());
                text2.setText("-"+remaining.toString());
               
                int progressValue = 0;
                if(mp.getDuration()>0){
                        progressValue = progressbar.getMax()*mp.getCurrentPosition()/mp.getDuration();
                }
                 progressbar.setProgress(progressValue);
               
        }
      
        private void mediaPlayerPause()
        {
                mp.pause();
                mediaPlayerState = MediaPlayerState.PAUSED;
                timerHandler.removeCallbacks(handlerInvocation);
                displayProgress();
        }
      
        private void addgo()
        {
                if(mediaPlayerState != MediaPlayerState.STOPPED){
                        mp.seekTo(mp.getCurrentPosition()+20);
                        mp.start();
                        timerHandler.postDelayed(handlerInvocation, updateInterval);
                }
                else{
                        timerHandler.removeCallbacks(handlerInvocation);
                        displayProgress();
                }
        }
      
        private void addback()
        {
                if(mediaPlayerState != MediaPlayerState.STOPPED){
                        mp.seekTo(mp.getCurrentPosition()-20);
                        mp.start();
                        timerHandler.postDelayed(handlerInvocation, updateInterval);
                }
                else{
                        timerHandler.removeCallbacks(handlerInvocation);
                        displayProgress();
                }
        }
        private void mediaPlayerStop()
        {
                mp.stop();
                mediaPlayerState = MediaPlayerState.STOPPED;
                timerHandler.removeCallbacks(handlerInvocation);
                displayProgress();
        }
      
        private void mediaPlayerPlay()
        {
                if (mediaPlayerState == MediaPlayerState.STOPPED)
                {
                        mediaPlayerInitialise(currentFilePath);
                        mediaPlayerState = MediaPlayerState.PLAYING;
                        timerHandler.postDelayed(handlerInvocation, updateInterval);
                }
                else{
                mp.seekTo(mp.getCurrentPosition());
                mp.start();
                mediaPlayerState = MediaPlayerState.PLAYING;
                timerHandler.postDelayed(handlerInvocation, updateInterval);
                }      
        }
      
      
        private void mediaPlayerInitialise(String filePath)
        {
                mediaPlayerState = MediaPlayerState.STOPPED;
                mp = new MediaPlayer();
                mp.setOnCompletionListener(new MediaPlayerCompletionListener());
                try
                {   
                        mp.setDisplay(su);
                        mp.setDataSource(filePath);
                        mp.prepare();
                        mp.start();
                        displayProgress();
                }
                catch (IOException e)
                {
                        // TODO: Handle this exception better
                        e.printStackTrace();
                        assert (false);
                }
        }
      
        private class MediaPlayerCompletionListener implements MediaPlayer.OnCompletionListener
        {
                public void onCompletion(MediaPlayer mediaPlayer)
                {
                        mediaPlayerStop();
                }
        }
      
}

引用 报告 回复 TOP 
MusicDroid - Audio Player(音乐点唱机) Part I
摘自：www.androidin.com

介绍:
你可以想像一下在cell phoneh一种流行的方式上去加载音乐.它将借助可移动的存储方介质,如SD card.在第1部分media play教程里,我们将创建一个简单的media player,它将允许用户从SD card里面去选择一首歌曲同时还可以进行播放.

下载此教程的源代码,请点击here
如何创建SD card的镜像在论坛里面有专贴介绍


Layout:
此项目由一个Activity,一个ListActivity组成。因此，对于ListActivity我们需要一个ListView来适用于这个实际的list，同时另一个View将被用于这个list每一项.对于这个例子我们将用一个TextView去显示每一个文件的名字。
首先，这里看到的是我们的ListView(songlist.xml):
<?xml version="1.0" encoding="UTF-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"

androidrientation="vertical"

android:layout_width="fill_parent"

android:layout_height="fill_parent">



<ListView id="@id/android:list"

android:layout_width="fill_parent"

android:layout_height="fill_parent"

android:layout_weight="1"


android:drawSelectorOnTop="false"/>


<TextView id="@id/android:empty"

android:layout_width="fill_parent"

android:layout_height="fill_parent"

android:text="No songs found on SD Card."/>
</LinearLayout>
非常标准的ListView。当ListView里面没有条目时在这个布局里面用这个来表示："@id/android:empty".这个TextView 条目将显示,同时在TextView里每一个这里都要被用于(song_item.xml)：
<?xml version="1.0" encoding="utf-8"?>
<TextView id="@+id/text1"xmlns:android=http://schemas.android.com/apk/res/android

android:layout_width="wrap_content"
android:layout_height="wrap_content"/>
你也许会想，为什么屏幕截图上显示的是一个黑色的ListView，layout上面没有提起任何颜色的设置？很好，这就是在AndroidManifest.xml文件里面定制的”theme（主题）”。在”应用程序”原素你能够定义这样的主题，增加
"android:theme="@android:style/Theme.Dark"".

ListActivity:
我们现在开始工作我们的ListActivity，我们将调用MusicDroid.这里是这个类和onCreate()功能的声明:
public class MusicDroid extends ListActivity {

private static final String MEDIA_PATH = new String("/sdcard/");

private List songs = new ArrayList();

private MediaPlayer mp = new MediaPlayer();

private int currentPosition = 0;

@Override

public void onCreate(Bundle icicle) {

super.onCreate(icicle);

setContentView(R.layout.songlist);

updateSongList();

}
首先我们将设置一个私有成员变量用被用于这个Activity。第一个是MEDIA_PATH,同时我们设置它为”/sdcard”因为这是SD card位置。接下来有一个String类型的list它将包含这每一首歌曲的名字在list里.同时我们当然还需要一个MediaPlayher对象. 我们称为mp.最后一个就是我们向上时,需要确定位置currentPosition,我们将用于存放当前正在播放的这首歌曲的索引.
onCreate()功能是相当基础的,我们设置我们的View让它成为这个songlist view我们在这之上进行创建同时调用这个updateSonglist()功能,这里就是这个功能的内容:
public void updateSongList() {

File home = new File(MEDIA_PATH);

if (home.listFiles(new Mp3Filter()).length > 0) {

for (File file : home.listFiles(new Mp3Filter())) {

songs.add(file.getName());

}

ArrayAdapter<String> songList = new ArrayAdapter<String>(this,

R.layout.song_item, songs);

setListAdapter(songList);

}
}
这里我们创建一个File对象并称为”home”指向”/sdcard”.我们在home.ListFiles()里对这些文件中进行循环并返回.增加每一个文件到我们的List对象(songs)里.一旦我们这个list装满了我们就创建一个ArrayAdapter进入这个songs list同时设置它到我们的ListActivity的ListAdapter(如:setListAdapter(songList);).这样就落户在我们的ListView.
你也许留意到这个对象”Mp3Filter”.这是一个对象它实现FilenameFiter(文件名过滤).这个对象被用于过滤,文件通过它以后返回, 实现了这个accept(File,String)功能, 也就完成了.
这里的这个对象我们能用于过滤,因此listFiles()仅仅返回的是Mp3的文件:
class Mp3Filter implements FilenameFilter {

public boolean accept(File dir, String name) {

return (name.endsWith(".mp3"));

}
}
现在我们应该能够去创建一个在/sdcard路径下所有mp3的list了.因此现在我们需要能够选择一首歌曲并且进行播放.第一件事首先,让我们重载onListItemClick()方法因此当一首歌曲被点击时将通知我们:
@Override
protected void onListItemClick(ListView l, View v, int position, long id) {

currentPosition = position;

playSong(MEDIA_PATH + songs.get(position));
}
相当基础的功能在这里.我们设置currentPosition,它里面包含了这个选中位置的索引这样点击的同时我们通过路径找到此歌曲并进行播放,因此我们去看看在playSong(String)里面到底发生了什么:
private void playSong(String songPath) {

try {



mp.reset();

mp.setDataSource(songPath);

mp.prepare();

mp.start();



// Setup listener so next song starts automatically

mp.setOnCompletionListener(new OnCompletionListener() {



public void onCompletion(MediaPlayer arg0) {


nextSong();

}



});



} catch (IOException e) {

Log.v(getString(R.string.app_name), e.getMessage());

}
}
对于我们这里这个MediaPlayer对象使一些事情真的容易了许多.首先我们调用mp.reset(),这样做将重置MediaPlayer到它的正常的状态.这是必须的如果我们正在放一首歌曲同时又想去改变这个数据源.这个reset()功能将也停止任何正在播放的歌曲.因此如果一首歌曲是播放状态同时我们又要选择另一首歌曲那么它将在启动下一首歌曲之前停止这首正在播放的歌曲.
我们然后通过路径找到这首歌曲(mp.setDataSource(String))同时调用prepare()和start().在这里指向MediaPlayer将启动播放你的歌曲.
接下来的工作就是去装备一个OnCompletionListener (mp.setOnCompletionListener(new OnCompletionListener()启动).在歌曲结束的时候,onCompletion(MediaPlayer) 这个功能将被调用.所有的我们做的这些都是从我们的Activity中调用nextSong()功能.这里是nextSong():
private void nextSong() {

if (++currentPosition >= songs.size()) {

// Last song, just reset currentPosition

currentPosition = 0;

} else {

// Play next song

playSong(MEDIA_PATH + songs.get(currentPosition));

}
}
这里我们检查以确信这不是列表里面的最后一首歌曲,如果是的我们不做任何事情,要不然我们将用playSong(String)功能播放下一首歌曲.

