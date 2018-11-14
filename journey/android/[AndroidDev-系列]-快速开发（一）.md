因为受到github上江清清的[FastDev4Android](https://github.com/jiangqqlmj/FastDev4Android)项目的启发,正巧又要负责公司新项目的启动，所以准备写个类似的库，争取做到write once,run AnyWhere(哈哈，开玩笑，方便以后快速开发啦～～)


随着`Android`项目业务量的迅速增长，原本的项目结构已经远远不能满足我们的需求来。因为直线上涨的代码量让我们花在编译项目上的时间由原来的一分钟左右到现在的五分钟甚至更长的时间。虽然谷歌官方提出`instant run`的解决方案，但是由于种种问题，还是没能很好的解决这个问题。

> 题外话：这里在网上看到有一种比较好玩的方案，通过编写`gradle`来计算每个`task`的执行时间，从而对整个项目的编译时间进行优化。有兴趣的朋友可以试下～～

[Gradle插件编写](http://blog.csdn.net/sbsujjbcy/article/details/50782830)

好吧，回到我们的主题：由于组件化采取的是在开发过程中将每一个业务模块都作为一个`application`，并伴随着一个壳工程，这样就大大缩减了我们开发时的编译时间；当项目上线的时候，只要将这些`application`变成第三方`Lib`，然后让壳工程依赖于这些`Libs`，进行打包，这样就完美的结局了编译时间上的问题。由于之前已经有大神总结了比较好的实践过程，这里就不赘述啦，直接看大神的文章吧～～

[Android组件化开发实践](http://www.jianshu.com/p/186fa07fc48a)


相信朋友们一定听过插件化这个概念，这里可以通过下面这篇文章稍稍科普下：

[Android 组件化和插件化开发](https://juejin.im/entry/577bae93d342d30057970e05)


下面来介绍下接下来我们要完成的项目的结构吧：


![](http://upload-images.jianshu.io/upload_images/2539684-9181f495f635ebdc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


通过图中我们可以看到，对我们来说比较重要的突破点就是：

- 路由工程


- BaseLibrary

其中，路由工程我们可以直接引用下[ActivityRouter](https://github.com/mzule/ActivityRouter)这个工程；

接下来，就是根据我们的业务需要去完成最重要的baseLibrary啦～～
从图中我们可以看到，我们需要在接下来的日子里面完成：

- 网络请求的封装

- 图片加载的封装

- 加密库的封装

- UI的封装

.......

不知道这里你是不是和我有着一样的疑问：github上有那么多现成的第三方框架，例如Square全家桶，facebook等(PS:移动端技术更新太过频繁啦，向大家推荐一个站可以看看最近出来哪些比较稳定的技术吧[Android 流行框架查速表](http://www.ctolib.com/cheatsheets-Android-ch.html))，为什么还要封装自己的框架呢？

实际上我们的封装也是建立在这些第三方库的基础上的，只是随着业务量的不断扩大，我们可能会切换项目所引用的第三方库，这个时候我们只需要更改自己的封装类就可以啦，是不是很方便。其实我也是借鉴stormzhang的观点的啦，有兴趣深入了解这样做的原因可以看看这篇文章，[如何正确使用开源项目？](http://stormzhang.com/android/2016/05/08/how-to-choose-open-source-project/)

好啦，接下来就让我们一起开启Android快速开发之旅吧，一起加油吧～～

待会儿，在没开始之前，咋们还是要确立注意点规范，还有就是工具啦，工欲善其事，必先利其器嘛～～

* [安卓开发规范](https://github.com/Blankj/AndroidStandardDevelop#2-as%E8%A7%84%E8%8C%83)
* TODO:android开发工具篇
