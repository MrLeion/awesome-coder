Gradle for Android 系列：初识 Gradle 文件


==================================


转自[张拭心的博客]( https://blog.csdn.net/u011240877/article/details/53798052)

读完本文你将了解到：


 *   [setting.gradle](#1-settinggradle)
	*   [主目录下的 buildgradle](#2主目录下的-buildgradle)
        *   [模块下的 buildgradle](#3模块下的-buildgradle)
    *   [备注](#备注)
        *   *   [注意 applicationId 和 package name 其实不是一个东西](#注意-applicationid-和-package-name-其实不是一个东西)
    *   [总结](#总结)

![shixinzhang](https://img-blog.csdn.net/20161222004730773?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTI0MDg3Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

我们用 Android Studio 新创建一个项目时，会自动生成 3 个 Gradle 文件：

![shixinzhang](https://img-blog.csdn.net/20161222004618663?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTI0MDg3Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

接下来介绍这三个文件的作用。

### 1\. setting.gradle

[上篇文章：为什么 Gradle 这么火](http://blog.csdn.net/u011240877/article/details/53572264) 中介绍了，

> 一个 Gradle 构建通常包括三个阶段：初始化，配置，和执行。

setting.gradle 文件在 **初始化过程中**被执行，构建器通过 setting.gradle 文件中的内容了解哪些模块将被 build，下面的内容表明当前项目中除了 app 模块还有另外一个叫做 “shixinlibrary” 的依赖模块：

include ‘:app’, ‘:shixinlibrary’

注意：单模块项目不一定需要有 setting 文件，但一旦有多个模块，必须要有 setting 文件，同时也要写明所有要构建的模块，否则 gradle 不会 build 不包括的模块。

### 2.主目录下的 build.gradle

看 gradle 文件中的注释：

> Top-level build file where you can configuration options common to all sub-projects/modules.

主目录下的 build.gradle 文件是最顶层的构建文件，这里配置所有模块通用的配置信息。

默认的顶层 build.gradle 文件中包括两个代码块 (buildscript 和 allprojects):

![shixinzhang](https://img-blog.csdn.net/20161221225701377?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTI0MDg3Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**buildscript**  
从名字就可以看出来，buildscript 是所有项目的构建脚本配置，主要包括依赖的仓库和依赖的 gradle 版本。

上图中 repositories 代码块将 jcenter 配置为一个仓库，JCenter 是一个很有名的 Maven 仓库。确定了依赖的仓库后，我们就可以在 dependencies 代码块中添加依赖的、在 jcenter 仓库中的包了。

dependencies 代码块用于配置构建过程中的依赖包，注意，这里是用于**构建过程**，因此你不能讲你的应用模块中需要依赖的库添加到这里。

默认情况下唯一被用于构建过程中的依赖包是 Gradle for Android 的插件。我们还可以添加一些其他用于构建的插件，比如 retrolambda, apt, freeline 等等。

**allprojects**  
allprojects 代码块用来声明将被用于所有模块的属性，注意是**所有模块**。常见的就是配置仓库地址（jcenter, 自定义 maven 仓库等），你还可以在 allprojects 中创建 tasks，这些 tasks 最终会运用到所有模块中，

> 官方建议尽量少添加用于所有模块的属性，因为这意味着强耦合，一旦没有构建主项目，你的子模块很有可能因为缺少所有模块的属性导致构建失败。

### 3.模块下的 build.gradle

模块下的 build.gradle 文件只应用于当前模块，你可以覆盖主目录下的 build.gradle 的内容。

以我的练习项目为例介绍：  
![shixinzhang](https://img-blog.csdn.net/20161221231912046?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTI0MDg3Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

上图中主要分三个模块：apply plugin , android, dependencies。

**apply plugin**  
apply plugin 声明了接下来要用到哪些插件的内容，上图表明使用了 androd 插件，这里之所以能用 android 插件，是因为主目录中声明了 Gradle for Android 的依赖，这里才能使用。

因此当我们需要使用其他插件，比如 retrolambda 时，首先需要在主目录 build.gradle 文件中添加依赖，然后在模块 build.gradle 中声明使用 retrolambda 插件。

备注：默认的 android 插件是由 Google 官方维护的，为我们提供了构建、测试、打包 Android 应用的能力。除此之外我们还可以自定义插件。在逐渐加深对 Gradle 的了解后，我们将尝试自己写个 Gradle 插件。

**android**  
在声明了 android 插件后，我们就可以使用 android 插件提供的内容进行构建配置。

android 构建配置中必须要有的是两个版本：

*   compileSdkVersion : 编译应用的 Android API 版本
*   buildToolsVersion : 构建工具版本  
    *   构建工具包括 aapt, zipalign, renderscript 等
    *   用于在打包时生成各种中间产物，可以从 SDK Manager 中下载构建工具

defaultConfig 代码块用于配置应用的默认属性，可以覆盖 AndroidManifest.xml 中的属性，比如：

*   applicationId : 覆盖了 AndroidManifest 中的 package name
*   minSdkVersion : 覆盖了 AndroidManifest 中的属性，配置运行应用的最小 API
*   targetSdkVersion : 一样，用于通知系统当前应用已经被这个版本测试过，和之前的 compileSdkVersion 没有关系
*   versionCode : 一样，应用的版本号
*   versionName : 版本名称

defaultConfig 还可以添加签名，占位符等等，这里只列这些。

buildTypes 用来定义如何构建和打包不同类型的应用，常见的就是测试和生产。具体内容后序介绍。

android 中还可以配置其他信息，比如 签名、渠道等，你可以在 Project Structure 面板中直观的查看，添加，也可以使用代码添加，这些内容我们后续详细介绍：  
![shixinzhang](https://img-blog.csdn.net/20161222003411168?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvdTAxMTI0MDg3Nw==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)

**dependencies**  
上图中可以看到 依赖配置 在 android 代码块的外边，事实上依赖配置是 Gradle 配置的基础功能，也就是说除了 Android，其他类型的项目（比如 JavaEE ）也可以这么用。

我们可以在依赖配置中，添加要使用的库，当然也可以添加本地的 jar 包。具体依赖配置内容我们后续深入介绍。

备注
--

#### 注意： **applicationId 和 package name 其实不是一个东西。**

在使用 Gradle 构建以前，package name 其实有两个作用：

*   在 R 文件中用作报名
*   应用的唯一标示

我们知道，一个安卓手机上相同包名的 app 只能有一个。但是当我们想要同时安装一个应用的不同的版本，比如一种测试一种生产，这时，就需要修改 package name 了，但是资源代码和 R 文件要求使用的包名不能改变，否则你的所有源文件都会随着构建版本而改变。怎么办呢？

Gradle 出现后，Android 工具团队解耦了 package name 的两种不同用法，提出了 applicationId 的概念：

*   定义在 Manifest 文件中的 package，继续用于源代码和 R 文件的标示
*   而 applicationId 则用作设备和 Google Play 的唯一标识

也就是说 applicationId 覆盖了 package name 的一部分职责。

总结
--

这篇文章概览了一个 Android 项目中的 Gradle 文件作用及内容，引申出许多细节，比如 自定义构建、依赖管理、多种类型构建的配置等等。接下来我们将深入学习这些内容。

相关阅读：

[Gradle for Android 系列：为什么 Gradle 这么火](http://blog.csdn.net/u011240877/article/details/53572264)