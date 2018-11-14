Android中view的绘制和动画效果的制作是常见的两大难点，前段时间正好在优化项目的时候做了一些动画。现在对于它们进行个归纳总结，如果有其他看法的同学欢迎给我留言，或者微博私信我～～

以敝人粗浅的理解，Android中交互是通过手势触摸屏幕中的view而产生的一系列动作，那么在view过程中我们可以理解为在一个数学坐标系上去判断触碰点击的位置和view点关系；动画我们可以理解为让view在坐标系做坐标运算从而产生动画效果。所以，了解坐标系也就成了我们把握view点绘制，动画制作等一系列动作等基础。

下面我们就一起探讨下Android中的哪些坐标系：

在讨论这个问题之前我们需要明确两点：

1. 一般情况下，我们只关心我们应用开发人员可以操纵的区域，下面让我们一起看看android屏幕的大致划分吧:

	-  状态栏
	-  [ActionBar]
	-  应用布局区域

在这样一个前提下，我们应用开发人员可以操纵的区域分为两种情况：

> 有ActionBar
在这种情况下，程序员可操纵区域的范围则是以ActionBar左下角为原点，水平向右为X轴正方向，垂直向下为Y轴正方向。如下图所示：

![](http://upload-images.jianshu.io/upload_images/2539684-e32a77b1848a5283.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

	
> 无ActionBar，那么我们的标题栏也会包含在应用布局中，一般的做法是会用一个公用的布局来作为标题。程序员可操纵区域的范围则是以ActionBar左下角为原点，水平向右为X轴正方向，垂直向下为Y轴正方向。如下图所示：

![](http://upload-images.jianshu.io/upload_images/2539684-217f1e59f198aa07.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



具体原因可以通过查看源码得知，这里就不再赘述啦，感兴趣的朋友可以看下两篇博客：

- [ Android应用setContentView与LayoutInflater加载解析机制源码分析](http://blog.csdn.net/yanbober/article/details/45970721)
-  [Android View 理论基础之坐标系](https://juejin.im/entry/577cedb1a3413100619a7dba)


2. View在屏幕中都是以矩形的形式存在的。


好啦，在这两个前提的基础上，我们一起给坐标分分类吧：

1. View的坐标系

	- 屏幕坐标
	
	以可操纵区域的左上角为原点，水平向右为X轴正方向，垂直向下为Y轴正方向。
	
	- 视图坐标
	
	![](http://upload-images.jianshu.io/upload_images/2539684-07000603ee80334d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
		
	以可操纵区域的左上角为原点，水平向右为X轴正方向，垂直向下为Y轴正方向。在这个时候View被视为一个矩形，通过API可以获得View的坐标：
	
	对应API：

	| View中的方法   | 含义    | 
	| ------------- |-------------| 
	| getTop()     | 	获取View自身顶边到其父布局顶边的距离 |
	| getLeft()     | 	获取View自身左边到其父布局左边的距离|
	| getRight()    | 	获取View自身右边到其父布局左边的距离|
	| getBottom()   | 	获取View自身底边到其父布局顶边的距离|
	
	
	| View中的方法       | 含义          | 
	| ------------- |-------------| 
	| getX()     | 	在当前父View坐标系中对应的坐标X的值 |
	| getY()     | 	在当前父View坐标系中对应的坐标Y的值|
	从Android3.0以后，引入transitionX和transitionY
	
	- X = transitionX + getLeft()
	- Y = transitionY + getTop()
	
	**注：这里的getLeft()和getTop()是不变的，当view在父View中移动是改变的是transitionX和transitionY的值，因此X和Y的值也会跟着改变**
	
2. 触摸点的坐标系


- 绝对坐标
	
	触摸点在屏幕坐标的坐标值；具体如图所示：
	
	![](http://upload-images.jianshu.io/upload_images/2539684-edf396eb49f1d2bb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	
	
	对应API：
	
	| View中的方法   | 含义          | 
	| ------------- |:-------------:| 
	| getRawX()     | 	在屏幕坐标系中对应的坐标X的值 |
	| getRawY()     | 	在屏幕坐标系中对应的坐标Y的值 |
	
	
- 相对坐标
	
	以当前View的左上角为坐标原点建立的坐标系，触摸点在此坐标系中对应的坐标值；具体如图所示：
	
	![](http://upload-images.jianshu.io/upload_images/2539684-239debbef5d5c7cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
	

	对应API：
	
	| View中的方法       | 含义          | 
	| ------------- |:-------------:| 
	| getX()     | 	在当前View坐标系中对应的坐标X的值 |
	| getY()     | 	在当前View坐标系中对应的坐标Y的值|
