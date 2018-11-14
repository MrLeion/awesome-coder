
![注意这些目录欧](http://upload-images.jianshu.io/upload_images/2539684-65cc3b43a39094e8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

[xmind源文件下载](http://ox1aqdtfp.bkt.clouddn.com/Android%E6%95%B0%E6%8D%AE%E4%B8%8E%E5%AD%98%E5%82%A8.xmind)


相信部分做 Android 的朋友经常会对内存、内部存储、外部存储这些概念有点含糊不清，也经常对下面这些操作：

- 一键清理
- 清除数据
- 清除缓存

不太清楚从开发角度上代表的真正的意义。今天工作上遇到了需要一些缓存方面的问题，发现对这些概念理解并不是那么清晰，做下小结段友勿喷～～


从英文上去理解

- 内存 memory

  类似于电脑的内存条，是设备进行逻辑和算术预算的重要部件；

- 内部存储 Internal Storage

  如下图所示，手机里需要 root 才能够查看的部分 ：／data/data/包名／...一般用来保存应用的一些配置和登录信息。在 apk 卸载之后包名下的文件会跟着清掉；


![内部存储](http://upload-images.jianshu.io/upload_images/2539684-dcb869bc12fe9695.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



- 外部存储 External Storage

需要关注的常用的私有目录

- ／Android／data／data／caches ：getExternalCacheDir()
- ／Android／data／data／files:getExternalStorageDir()

一般要将缓存的数据放在这两个目录下，在 apk 卸载之后这两个目录中的文件会跟着清掉；

![外部存储](http://upload-images.jianshu.io/upload_images/2539684-aa8d7eeccd49e531.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


这里提供一个文件操作的工具类库 [AndroidUtilCode](https://github.com/Blankj/AndroidUtilCode)

下面解析下三种操作：

一键清理：清除 memory，杀死进程

清除缓存：清除 app 缓存的页面数据

清除数据：清除内部存储和外部存储中 files 和 caches 下的文件。










