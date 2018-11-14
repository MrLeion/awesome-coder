##基础设置
1 `cmd+alt+s`进入设置界面，输入 encoding 设置默认字符集为`UTF-8`(千万别忘了，否则就坑队友啦～～)

![](http://upload-images.jianshu.io/upload_images/2539684-514e6cacf8c39c60.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2 设置主题，窗口大小，动画效果

-  修改主题

-  修改全局窗口字体，字号

-  窗口动画

![](http://upload-images.jianshu.io/upload_images/2539684-2fcbc20f84f7311e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



3.修改menu或者toolBar

> 这里我是添加了创建class,fragment,activity的ToolBar

![](http://upload-images.jianshu.io/upload_images/2539684-809a509e6fe71671.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.释放空包折叠

![](http://upload-images.jianshu.io/upload_images/2539684-939640c737612f4e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5.打开工程设置

- 禁用自动打开上次关闭工程 ,禁用退出提示

- 打开新项目提示方式

![](http://upload-images.jianshu.io/upload_images/2539684-8f1be1792c239e38.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


6.禁用自动检查更新

- 取消as自动更新

- 消sdk自动更新


![](http://upload-images.jianshu.io/upload_images/2539684-92951e0fbde14538.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


7.配置快捷键

- 自定义快捷键

- 根据内容搜索快捷键

- 根据按键搜索快捷键

- 删除快捷键 

![](http://upload-images.jianshu.io/upload_images/2539684-24cea3286d2cb2d0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

快捷键查询：

[Android Studio常用快捷键汇总（mac的小伙伴们看过来)](https://segmentfault.com/a/1190000006898515)

[Mac官方快捷键](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)


8.编辑器

- 鼠标悬停显示文档

- 格式化&导包提示


![](http://upload-images.jianshu.io/upload_images/2539684-b9fc23f8f4edd632.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


9.显示行号，显示方法分隔线

- 显示行号

- 显示方法分隔符

![](http://upload-images.jianshu.io/upload_images/2539684-cd4f14a56e197394.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


10.代码折叠

- 取消方法自动折叠


![](http://upload-images.jianshu.io/upload_images/2539684-e5b5dcc075b38c11.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

11.代码智能提示

- 敲什么都提示

- 提示时间设置

![](http://upload-images.jianshu.io/upload_images/2539684-e99af54a18a1c35d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 敲什么字符会提示，All(大小写全部符合)，None（不管大小写，符合就提示),(First letter)（第一个字符符合就OK，其他随意）。我这种脑残没记性的当然选择None。时间设置根据自己电脑性能.


12.自动导包

![](http://upload-images.jianshu.io/upload_images/2539684-98014f12c91999aa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Optimize imports on the fly：优化导包，格式化代码时会删掉多余的导包。Add unambiguous imports on the fly：敲代码时，敲简单类名就帮你把包导了。

##代码风格设置

1.创建个人代码样式配置

> 估计是为了保护默认的代码样式配置，让用户把配置搞坏了也能一键还原，IDEA不允许修改默认的配置，需要用户创建配置才能进行修改。选择基于哪个主题的，然后Save As一份即可。

![](http://upload-images.jianshu.io/upload_images/2539684-4d5add49c9260456.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2．修改代码字体

> 强烈建议用Consolas字体，好看！！！

![](http://upload-images.jianshu.io/upload_images/2539684-28b9ea6b4fd5694f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


3.修改控制台字体

> 要改的话，得先把1那个地方的勾取消掉,默认android Logcat 每个级别的颜色都是一样的.建议修改

![](http://upload-images.jianshu.io/upload_images/2539684-2e474c54614ad404.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.Logcat字体

> 要改的话，得先把1那个地方的勾取消掉,默认android Logcat 每个级别的颜色都是一样的.建议修改

![](http://upload-images.jianshu.io/upload_images/2539684-a90e4a09afda7e95.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


5.修改注释位置

> 禁用“语句堆一行”

![](http://upload-images.jianshu.io/upload_images/2539684-173633b90bcb16dc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> Comment at frist column：启用的话，注释符号就会在行首，否则就按照缩进来注释。
> Control statement in one line：格式化代码的时候，会把些很短的语句合并成一行。这样影响代码可读性.


6.对齐变量名

![](http://upload-images.jianshu.io/upload_images/2539684-e2ad1c34f2760f3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


7.修改变量前后缀

> 静态成员是s，普通成员是m，转换成成员变量的时候自动加上m,生成setter,getter的时候会忽视m,很好很强大.

![](http://upload-images.jianshu.io/upload_images/2539684-5022955f3baa1dca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

8.取消Android Lint 检查

> 一定程度加快速度吧,不过打开Android Lint会有一些android相关提示

![](http://upload-images.jianshu.io/upload_images/2539684-e9d1ab236e832dac.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

9.新建文件模板

` /**      
* author: ${USER}     
 * created on: ${DATE} ${TIME}      
* description:    
  */
`
![](http://upload-images.jianshu.io/upload_images/2539684-d0ba47f594116806.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

10.修改新建文件文件头

> 每次建新类,会加上这样的头信息
![](http://upload-images.jianshu.io/upload_images/2539684-1f2f761440d59c90.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 上图就是通用的文件头，框住的地方是你系统的用户名，想个性化的话，可以改这里，至于哪里引用这个文件头的呢，就在隔壁
![](http://upload-images.jianshu.io/upload_images/2539684-8edfcf37355b600e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




11.自己定义Live Templates

> 模板定义,方便开发,减少重复代码

![](http://upload-images.jianshu.io/upload_images/2539684-e74b1bfe801ef3cd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##工具篇


1.添加管理插件

![](http://upload-images.jianshu.io/upload_images/2539684-4eaa71f4178d2463.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

1)	从远程仓库获取插件
2)	从本地仓库获取插件



2.Svn添加移除项目

![](http://upload-images.jianshu.io/upload_images/2539684-9130aeb1e1306796.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.配置Svn安装路径

a)可以自己是自己下载的Subversion SVN的svn.exe

b)可以是Visual SVN里面的svn.exe

c)可以是TortoiseSVN里面的svn.exe

![](http://upload-images.jianshu.io/upload_images/2539684-67b351500260d808.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.配置git安装路径

![](http://upload-images.jianshu.io/upload_images/2539684-7851f25865c018d1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

5.配置Gradle安装路径,离线模式,本地Gradle仓库

![](http://upload-images.jianshu.io/upload_images/2539684-aae44ab67245f49b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


6.配置maven仓库路径

![](http://upload-images.jianshu.io/upload_images/2539684-c1e1714b9e46ac01.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

7.项目自动编译

![](http://upload-images.jianshu.io/upload_images/2539684-e2b7b6039b6c84aa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

8.Gradle Task超时时间

![](http://upload-images.jianshu.io/upload_images/2539684-6f0e3831185b5cd6.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

9.优化-取消同步

![](http://upload-images.jianshu.io/upload_images/2539684-c1c21adb98301b1e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


##AndroidStudio奇淫异巧


- 上面的这些设置我已经帮各位设置好，放在这个目录下啦，各位只要`import settings`,下载地址：[setting.jar](https://github.com/MrLeion/MacTools/blob/master/AndroidStudio/settings.jar)

- mac多行编辑
 
> ctrl+G

> shift+</> 选中单个字母

> shift+command+</> 选中整行

> shift+alt+</> 选中单个单词
 

- mac插件集合

	- ButterKnife
	
	- GsonFormat

	- Selector
	
	
- 资源下载站
 
 [Google中国开发官网](https://developer.android.google.cn/index.html)
 
 [Android Studio中文社区]( http://tools.android-studio.org/index.php)
 	
 [Android Studio问答社区](http://ask.android-studio.org/?/explore/)

 [Android Studio开发者工具下载](http://www.androiddevtools.cn/)


 	

- 参考资料

[Androidstudio快速入门](http://stormzhang.com/devtools/2015/06/17/android-studio-all/)

[Android studio官方权威指南](https://developer.android.google.cn/studio/index.html)
