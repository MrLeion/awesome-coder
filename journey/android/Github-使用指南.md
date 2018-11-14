![](http://upload-images.jianshu.io/upload_images/2539684-1a53495ad76841c8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###Github和Git的区别

写这篇文章的目的一来是总结下自己对于 Github 这个社区的使用经验总结；另一方面希望可以帮助到那些刚刚接触到编程的筒子们，希望你们能够在编程的道路上找到属于自己的乐趣！
首先需要更正的一个常识：Github 和 Git 不是一个玩意儿；在实际工作中，我们的代码可能会被存储在当前的项目工程目录下、本地仓库(电脑某个固定的文件下)、远程服务器上。Github 可以理解为我们储存代码的服务器，当然它远非服务器这么简单啦，Git 就是协助我们在上个目录下提交代码的一款工具，就和 SVN 是一个道理；
Github 作为全球最大的基友交流群，有着很多的公司驻扎在其中：

- [Google 爸爸](https://github.com/google)
- [Facebook](https://github.com/facebook)
- [Square](https://github.com/square)
- [Alibaba](https://github.com/alibaba)
- 。。。。。。

在这里你还可以认识各界大神，比如 Android 界的大神：

- [Jake Wharton](https://github.com/JakeWharton)
- [Triena](https://github.com/Trinea)
- [代码家](https://github.com/daimajia)
- 。。。。。。

作为一个程序员，GitHub 是我们提升个人影响力的很好的一种方式，所以你还在犹豫什么，赶紧注册一个号一起投入到编程的行业中来吧：[传送门](http://www.github.com/)

另外，宣传下[我个人的账号](https://github.com/MrLeion)欢迎大家一起来交流技术～～

###基本概念

![](http://upload-images.jianshu.io/upload_images/2539684-fe196467bcf62c75.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

当你注册完账号，进入 Your Profile 界面时，你就会看到上图的界面，当然如果你是第一次进入可能还没有什么项目。

这里我们要对Github上一些操作有一个概念性的理解(英语不好的筒子们不用担心)：

- Repository
   仓库的意思，即你的项目，你想在 GitHub 上开源一个项目，那就必须要新建一个 Repository。
   
- Issue
  别人发现你的项目中有bug，或者哪些地方做的不够好，他就可以给你提个 Issue 。
  
- Star
	就是给项目点赞。
	
- Fork
 
  你开源了一个项目，别人想在你这个项目的基础上做些改进，然后应用到自己的项目中，这个时候他就可以 Fork 你的项目，这个时候他的 GitHub 主页上就多了一个项目，只不过这个项目是基于你的项目基础。


- Pull Request(PR)

发起请求，这个其实是基于 Fork 的，还是上面那个例子，如果别人在你基础上做了改进，后来觉得改进的很不错，应该要把这些改进让更多的人收益，于是就想把自己的改进合并到原有项目里，这个时候他就可以发起一个 Pull Request（简称PR） ，原有项目创建人就可以收到这个请求，这个时候他会仔细review你的代码，并且测试觉得OK了，就会接受你的PR，这个时候你做的改进原有项目就会拥有了。


- Watch

这个也好理解就是观察，如果你 Watch 了某个项目，那么以后只要这个项目有任何更新，你都会第一时间收到关于这个项目的通知提醒。


- Gist

如果你只是单纯的想分享一些代码片段，那这个时候 Gist 就派上用场了！


好吧，下面就一起开启 Github 浪漫之旅吧～～



###第一次使用需要的配置

工具安装：[Git 传送门](https://sourceforge.net/projects/git-osx-installer/)

第一次使用嘛，肯定要告诉人 Github 你的身份啦，有必要配置你的用户名和密码加上你的  SSH 密钥；

```
$ git config --global user.name "用户名"
$ git config --global user.email "电子邮箱"

```


在使用 Github 的过程中，我讲大部分操作归结为两大类，即从 Github 上 clone 项目；或者将我们自己的项目分享到 Github 上和志同道合的人士进行交流，下面来看看具体是如何操作的吧～～

###Project To GitHub


- case 1：空的代码库
```
# 在当前目录新建一个Git代码库
$ git init

# 新建一个目录，将其初始化为Git代码库
$ git init [project-name]
```
- case 2：已存在代码库
# 切换到项目目录下
$ git init

# 添加到本地暂存区
$ git add . 

# 提交到本地暂存
$ git  commit -m "hello world"


# 添加到远程仓库，将本地仓库与远程仓库简历链接
$ git remote add origin [github 仓库地址]

# 更新
$ git pull origin master --allow-unrelated-histories

# 提交
$ git push origin master

** 注： ** 按步骤操作偶~~




###Project From Github

```
下载一个项目和它的整个代码历史
$ git clone [url]

```

### 常用命令

![图片来源于阮一峰博客](http://upload-images.jianshu.io/upload_images/2539684-82b89315231e2286.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如上图所示，我们需要清楚了解下面几个概念：

- Workspace：工作区
- Index ：暂存区
- Repository：本地仓库
- Remote：远程仓库

我们的项目工程在从本地提交中央远程仓库的过程中，



1. 工作区->暂存区

```
# 添加指定文件到暂存区
$ git add [file1] [file2] ...

# 添加指定目录到暂存区，包括子目录
$ git add [dir]

# 添加当前目录的所有文件到暂存区
$ git add .

# 添加每个变化前，都会要求确认
# 对于同一个文件的多处变化，可以实现分次提交
$ git add -p

# 删除工作区文件，并且将这次删除放入暂存区
$ git rm [file1] [file2] ...

# 停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]

# 改名文件，并且将这个改名放入暂存区
$ git mv [file-original] [file-renamed]
```

2. 暂存区->本地仓库

```
# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

# 提交时显示所有diff信息
$ git commit -v

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]

# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ...
```



3. 本地仓库->远程仓库

```

# 删除远程tag
$ git push origin :refs/tags/[tagName]

# 查看tag信息
$ git show [tag]

# 提交指定tag
$ git push [remote] [tag]

# 提交所有tag
$ git push [remote] --tags

# 新建一个分支，指向某个tag
$ git checkout -b [branch] [tag]
```



###分支管理

```
# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]

# 提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a

# 提交时显示所有diff信息
$ git commit -v

# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]

# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ...
五、分支

# 列出所有本地分支
$ git branch

# 列出所有远程分支
$ git branch -r

# 列出所有本地分支和远程分支
$ git branch -a

# 新建一个分支，但依然停留在当前分支
$ git branch [branch-name]

# 新建一个分支，并切换到该分支
$ git checkout -b [branch]

# 新建一个分支，指向指定commit
$ git branch [branch] [commit]

# 新建一个分支，与指定的远程分支建立追踪关系
$ git branch --track [branch] [remote-branch]

# 切换到指定分支，并更新工作区
$ git checkout [branch-name]

# 切换到上一个分支
$ git checkout -

# 建立追踪关系，在现有分支与指定的远程分支之间
$ git branch --set-upstream [branch] [remote-branch]

# 合并指定分支到当前分支
$ git merge [branch]

# 选择一个commit，合并进当前分支
$ git cherry-pick [commit]

# 删除分支
$ git branch -d [branch-name]

# 删除远程分支
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]
```


###通过 Github 提升自己

上面的操作让我们将github这个「网盘」的功能发挥到了淋漓尽致；但是如果需要真正通过Github提升自己的能力，就要回归到根本。作为有名的「基友交友社区」，我们可以看到通过别人的代码拓广自己解决问题的思路，而且可以通过自己的积累发现问题并完善别人的代码！
这里我们就经常要 Fork 下别人的代码，然后给别人(项目主程开发)提交 PR (Pull Request)。给大家推荐一份电子书，作者 Phodal 可以说是 TDD 的死忠，大家有兴趣可以去看看他的文章也算体验下大神的日常生活吧： [GitHub 漫游指南](http://github.phodal.com)


- TDD
- CI
- 重构
- 自动部署


最后给大家推荐几款用着还不错的 Github 插件和网站吧(PS:网上有很多很好的，大家搜索关键词就好了，有不错的记得推荐给我欧～～)：

-  [Github Ranking](http://git-awards.com/)
-  [Githuber](https://githuber.cn/)
-  [Github 开放接口](https://developer.github.com/)

最后如果希望搭建个人网站但是苦于没有钱买服务器的筒子们可以使用 Github Pages ,个人就是用 Hexo 在上面建了个自己的站，还可以。

推荐文章：

[常用 Git 命令清单 —— 阮一峰](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

[GitHub 漫游指南](http://github.phodal.com)

[如何通过github提升自己](https://www.phodal.com/blog/use-github-grow-self/)
