****

简书的 MarkDown 编辑器居然不支持音视频解析～～

[相声：郭德纲、于谦《我要穿越》](http://ofc6yl8uw.bkt.clouddn.com/%E9%83%AD%E5%BE%B7%E7%BA%B2%20%E4%BA%8E%E8%B0%A6%20%E6%88%91%E8%A6%81%E7%A9%BF%E8%B6%8A.mp3)

****

 ![](http://upload-images.jianshu.io/upload_images/2539684-73a19d2abeb550e2.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


喜欢上「简书」与生俱来简约的风格，不用考虑任何排版，只要了解一些基本的语法就可以写出简洁的文章，妈妈再也不用担心我写作排版难看了。选择 Markdown 这几点值得拥有：

- 专注于内容创造
- 可以导出为 html、pdf


###工具推荐

因为本人使用的是Mac电脑，所以推荐的工具只能局限于这一平台的啦，Windows上工具多多大家去百度下就可以了；

-  MacDown：[传送门](https://macdown.uranusjr.com/)

-  sublime Text 3 安装插件，并安装插件：[传送门](https://www.sublimetext.com/3)

废话不多说，自行 Google 或者尝试着用下，包君满意～～

###语法

####标题

在 Markdown 中，你只需要在文本前面加上 # 即可，同理、你还可以增加二级标题、三级标题、四级标题、五级标题和六级标题，总共六级，只需要增加 # 即可，标题字号相应降低:


----
代码：

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题
```
----
效果：
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
##### 五级标题
###### 六级标题


----


#### 分割线

在 Markdown 中，你只需要使用连续的四个 * 就可以了

----
代码：

```
****

```

----
效果：

****



----



#### 列表

在 Markdown 中，列表分为有序和无序两种：

##### 无序列表

在 Markdown 中，你只需要在文字前面加上 - 就可以了。

----
代码：

```
- 无序
- 无序
- 无序
```
----
效果：

- 无序
- 无序
- 无序

---

##### 有序列表

在 Markdown 中，你只需要在文字前面加上 1. 2. 3. 就可以了。


----
代码：

```
1. 有序
2. 有序
3. 有序
```
----
效果：

1. 有序
2. 有序
3. 有序

---


####多媒体超链接

#### 链接

----
代码：

 ```
 [百度](http://www.baidu.com)
 ```

----
效果：

[百度](http://www.baidu.com)

----




##### 图片


----
代码：


```
 ![图片描述](http://upload-images.jianshu.io/upload_images/2539684-73a19d2abeb550e2.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```


----
效果：

 ![图片描述](http://upload-images.jianshu.io/upload_images/2539684-73a19d2abeb550e2.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

----

#### 音频


----
代码：

```
<audio src="http://ofc6yl8uw.bkt.clouddn.com/%E9%83%AD%E5%BE%B7%E7%BA%B2%20%E4%BA%8E%E8%B0%A6%20%E6%88%91%E8%A6%81%E7%A9%BF%E8%B6%8A.mp3" controls="controls">
</audio>
 
```

----
效果：

<audio src="http://ofc6yl8uw.bkt.clouddn.com/%E9%83%AD%E5%BE%B7%E7%BA%B2%20%E4%BA%8E%E8%B0%A6%20%E6%88%91%E8%A6%81%E7%A9%BF%E8%B6%8A.mp3" controls="controls">
</audio>

----


#### 视频

----
代码：

```
 <iframe height=498 width=510 src="" frameborder=0 allowfullscreen></iframe>
```

----
效果：

 <iframe height=498 width=510 src="" frameborder=0 allowfullscreen></iframe>

----


#### 引用

我们写作的时候经常需要引用他人的文字，这个时候引用这个格式就很有必要了，在 Markdown 中，你只需要在你希望引用的文字前面加上 > 就好了：

----
代码：

```
> 失意莫灰心，得意莫忘形

```

----
效果：

>  失意莫灰心，得意莫忘形

----


#### 代码引用

----
代码：

```

	```
	
  @Override
    protected void initViews() {
        initListener();
    }
    
    ```

```

----
效果：




	```
	  @Override
	    protected void initViews() {
	        initListener();
	    }
 
        ```

----




#### 表格

----
代码：

```
dog | bird | cat
----|------|----
foo | foo  | foo
bar | bar  | bar
baz | baz  | baz

```

----
效果：


dog | bird | cat
----|------|----
foo | foo  | foo
bar | bar  | bar
baz | baz  | baz


----

考虑到大部分读者对于代码语法这个东西基本无感，这里给大家介绍一个在线的练习网站，希望可以帮助大家更快的了解 Markdown：

[在线练习网站](https://github.com/gjtorikian/markdowntutorial.com)

学习了简单的使用后相信大家在以后的使用中还会有需要查证的地方：

  [Markdown中文参考](http://wowubuntu.com/markdown/#list)


###多媒体资源处理

5G 时代都快到来了，相信大家在使用 Markdown 书写过程中一定会有给自己的文章配图或者偶尔附加几个音视频等需求吧。这里给出自己作为IT男的一些玩法吧，如果大家有更好玩的欢迎给我私信欧～～

首先图片资源搜集问题相信大家应该都有自己的套路(百度谷歌随便搞搞，当然如果是专业点的图片还需要去到图片网站上找的，后期会给大家分享这方面的技巧)。平常的时候我喜欢听听相声什么的，然后通过自己的文章分享出来。一般喜欢去 youtube 上去找一些视频资源，然后借助在线的转换工具，这里给大家推荐一款吧，类似的可以去 Google 上找找：

[youtube-mp3](https://www.youtubeto.com/zh/)

这个网站会将在线的 youtube 视频链接直接转成 mp3 并且下载到本地来视频也是一样的，好啦有了获取自己想要的多媒体资源的能力，那么下面我们就一起看看怎么去管理好自己的资源吧。


通过上一节的 Markdown 语法的学习相信大家对它已经不陌生了吧，可以看到我们在向 Markdown 文档中添加自己需要的这些多媒体资料的时候需要一系列的超链接，如果这些资源我们不能很好的管理的话，那么很有可能在咋们文章上传之后那些超链所对应的资源会被删除。所以为了避免这样的问题，咋们需要自己的一款多媒体资源的服务器来寄存咋们的资源。
干编程的同志们应该听过这两个网站：

-  [七牛云服务器](https://www.qiniu.com)
-  [Github](https://github.com/)

这两款产品可以作为我们多媒体资源的存储服务器，并且获取对应的超链接这样就完美解决这个问题啦～～（ PS：随着我们持续不断地使用相信可能会收一点点费用，但是我相信对于长期打算写作锻炼自己的我应该是不打紧的，毕竟半年多了我没有被收一毛钱！）


###中文写作规范

既然选择用文字记录下自己思绪的点滴，那么就让我们打造出最完美的格式，让别人在获取分享的同时更能理解我们对于细节的追求和打磨(PS:实际上就是扯扯淡，也就是让自己的文章看起来没有那么辣眼睛而已),归纳一下总结为以下几点：
1. 中、英、数字、链接之间要有空格；
2. 不要有重复标点符号；
3. 专有名词需要规范大小写；


详情请点击： [中文排版规范](https://github.com/sparanoid/chinese-copywriting-guidelines)
