
![](http://upload-images.jianshu.io/upload_images/2539684-b7085d0a8f8487a4.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


首先必须得承认如果通过反编译直接窃取别人的劳动成果是有那么点不道德！所以我们一定一定一定要学好反编译，这样我们就可以尽情地窃取别人的劳动成果，并且防止我们自己的技术不被反编译啦(开个玩笑啦，别当真)～～

好吧，下面单纯从技术的角度一起谈谈我们的android安全攻防大战吧：

![](http://upload-images.jianshu.io/upload_images/2539684-58f9f0249bb6df74.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如上图，迎面向我们走来的是本文的两大重要环节攻与防，也就是我们所说的反编译和混淆加固啦；反编译(攻)一般分为两种情况：

- 1.资源反编译，针对喜欢高仿但是不会P图的广大程序员屌丝们；
- 2.源代码反编译，可以看看别人的代码和实现手段；

混淆加固(防)也分为两种手法：

- 1.混淆，这种情况比较麻烦，引入第三方还要避免混淆别人的代码，并且混淆后的代码还是可以看得出大致使用的技术和逻辑，所以不推荐使用；
- 2.加固，360加固全部自动化打包，但是现在应用商店似乎对加固软件进行了限制，比如之前工作上传百度应用市场的时候居然提示我们要用百度加固～～，baidu，坑爹！

### 赛前准备 

工欲善其事，必先利其器。选择一个好的工具可以使我们的工作:

- [dex2jar](https://sourceforge.net/projects/dex2jar/files/?source=navbar)

- [JD-GUI](http://jd.benow.ca/)

- [apktool](https://ibotpeaches.github.io/Apktool/install/)

- [iTerm命令行工具](https://www.iterm2.com/)

- [360加固工具](http://jiagu.360.cn/qcmshtml/details.html#helper)

- [Apk编辑器](http://android.myapp.com/myapp/detail.htm?apkName=com.gmail.heagoo.apkeditor.pro) 



> 问题一：apktool安装配置，作为mac盲的我展示下零基础怎么配置以及遇到的一些问题吧：

- 1.右键保存链接为 apktool 所有格式文本[wrapper script](https://raw.githubusercontent.com/iBotPeaches/Apktool/master/scripts/osx/apktool)
- 2.apktool.jar 下载地址打开可以看到历史版本列表，可以选择最新版本的，此教程使用的版本为：2.2.3 下载成功重命名为apktool.jar.

- 3.将 apktool.jar 和 apktool 拷贝到 /usr/local/bin（需要 root 权限）

> sudo cp apktool apktool.jar /usr/local/bin [此目录是 mac 中管理员可执行命令]

- 4.修改这两个文件的权限: sudo chmod + x file名

- 5.现在就可以在终端运行 apktool 命令了

> 验证安装 apktool 是否安装成功的时候发现错误：
Error: Invalid or corrupt jarfile /usr/local/bin/apktool.jar

![](http://upload-images.jianshu.io/upload_images/2539684-1ca922efdbc2dad7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

Google了一下，检测jar包是否正常的命令：

> java -jar jar包名

报出同样的错误，删除原本 /usr/local/bin/ 目录下的文件，重新配置，获得成功：

![](http://upload-images.jianshu.io/upload_images/2539684-d82bc617b744483c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


> 问题二：dex2jar 需要授权：

切换到 dex2jar 目录下，执行命令：chmod a+x *.sh

注：否则直接执行会提示:

d2j-dex2jar.sh: line 36: ./d2j_invoke.sh: Permission denied



###反编译

为了能够更好地串联整个过程也本着尊重版权的原则，我们写了一个简易的demo：
 
 ![](http://upload-images.jianshu.io/upload_images/2539684-20b45148983d10c7.gif?imageMogr2/auto-orient/strip)
 
 好的，下面就围绕这个demo进行展开吧～～
 
 出于文件整理的考虑，我们将apk文件和授权完成的dex2jar放入同一目录下：
 
 ![](http://upload-images.jianshu.io/upload_images/2539684-989b8bd7199b3ada.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 
####源代码反编译

思路：我们知道 android 的源代码是以 .dex 文件的形式存在的，也就是说我们要查看源码，我们需要将.dex -> java 代码；但是目前还没有找到比较好的直接转换工具，所以我们套用原有套路:.dex -> .jar->java源码；

说干就干，执行命令：

> sh dex2jar-2.0/d2j-dex2jar.sh app-release.apk

通过dex2jar我们获得以下文件：

![](http://upload-images.jianshu.io/upload_images/2539684-069d38e3715e4a15.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

右击app-release-dex2jar.jar文件选择用JD-GUI打开查看源码即可，让我们来看看我们的成果吧：
![](http://upload-images.jianshu.io/upload_images/2539684-0e2f86aeaeb07a43.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

做到这里大家不知道有没有好奇，没毛病啊～～图片什么的都有啦，源代码也有啦，打开 .xml 文件一看，目瞪口呆：

![](http://upload-images.jianshu.io/upload_images/2539684-38dadf20b73c4f5f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

所以咋们都资源反编译也就应运而生啦～～

####资源反编译

正如上面提到的，资源反编译针对的主要是 xml 资源文件，我们使用的工具也就是 apktool ,切换到上图目录下废话不多说来行命令压压惊：

> apktool d app-release.apk


xml完美呈现：

![](http://upload-images.jianshu.io/upload_images/2539684-c8c9950826fb6f4a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这个时候我们可以打开smali文件夹改些文本什么的，重新拿个证书打个包，就是一个添加了我们 tag 的 app 啦～～

切换目录到demo下，执行命令

> apktool b app-release

兴冲冲装到自己手机上，结果发现安装不了，原来是没有证书，没有条件就去创造下条件从AS中生成一个自己的证书，然后用该证书给咋们的app打个包就OK啦。

执行命令：

 >  jarsigner -verbose -keystore android.keystore -signedjar app-release-1.apk app-release.apk android.keystore
 
 效果如下：
 
 ![](http://upload-images.jianshu.io/upload_images/2539684-02abcb9375674028.gif?imageMogr2/auto-orient/strip)
 


### 加固

好啦，我们成功破解所有套路之后，我们来看看如何反套路吧，目前市面上对代码进行混淆或者加固。本文选择运用加固技术对我们的app进行保护。如果需要加固助手的同学可以360官网下载到加固助手，另外它还需要注册账号，个人配置密钥证书和下载渠道，参考帮助手册进行操作即可。

![](http://upload-images.jianshu.io/upload_images/2539684-717f4f0484a01130.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果你看到这个界面那么咋们就可以开始加固打我们的渠道包啦，暂时我们只添加了腾讯应用宝、百度手机助手和360市场打包成功后我们可以获取每个渠道的app。

下面我们还是用上面的方法对我们的渠道包进行反编译，我们会发现很安全因为整个逻辑根本就看不清楚啦～～

![](http://upload-images.jianshu.io/upload_images/2539684-eea3b77b9f17dec2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

好啦，Android 攻防战到此结束，如果有朋友有更好玩的欢迎微博或者简书私信我偶～～


参考文章：

- [Android安全-反编译-郭霖](http://blog.csdn.net/guolin_blog/article/details/49738023)

- [Android安全-混淆技术-郭霖](http://blog.csdn.net/guolin_blog/article/details/50451259)

- [反编译Mac实操参考](http://www.jianshu.com/p/b3bb4da64dc7)
