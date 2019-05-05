---
layout:     post
title:      "Github Pages+jekyll博客全记"
subtitle:   "不坑不是病，坑起来真要命"
date:       2019-1-2 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - Github
    - jekyll
    - Blog
    - MarkDown
    - Git
    - 图床
    - 云服务
    - ruby
---
## 建站 ##
> 这两天重新搭建了Github Pages上的博客，换用了jekyll，比之前的hexo差不多，主要就说下环境搭建。

> 还有那些让人欲哭无泪的BUG们=。=

> 话不多说，下面就进入正题。

## 系统环境搭建 ##
首先安装jekyll，这是GitHub官方推荐的静态网页工具。它类似于WordPress，但只是一个生成静态网页的工具，不需要数据库支持。同时可以配合第三方服务,例如Disqus。
### 首先安装ruby ###
> [ 安装git ](http://git-scm.com/download/)

> [ 安装ruby和devkit工具 ](https://rubyinstaller.org/downloads/)  

安装时勾选添加到PATH，以便添加环境变量。
>这里有个贼坑的地方，安装路径一定不能在二级目录，只能直接在盘符下一级目录安装，否则就会出现一堆百度和谷歌解决不了的问题，别问我怎么知道的=。=

![](http://ww1.sinaimg.cn/large/7c08400ely1g2kwkvvhd8j20dz0atq3i.jpg)
安装完成后继续安装msys2，直接选finish就可以进入安装界面。
![](http://ww1.sinaimg.cn/large/7c08400ely1g2kwkvtmw0j20dz0at752.jpg)
然后选择第三项（输入3），等待安装提示success后关闭即可。
![](http://ww1.sinaimg.cn/large/7c08400ely1g2kwkvsxv3j20qr07l745.jpg)

### 安装RubyGems ###
ruby 是一种语言，是某些软件包代码的执行环境。而gem是管理这些基于ruby程序的程序。

> [ 安装RubyGems ](https://rubygems.org/pages/download)
> 
> Windows中下载ZIP格式比较方便，下载后解压到任意路径。

执行以下指令安装
```bash
$ cd {unzip-path} // unzip-path表示解压的路径
$ ruby setup.rb
```

### 安装jekyll ###
cmd中输入指令安装
```bash
$ gem install jekyll
$ gem install "jekyll-paginate" 
```

### 验证安装完成 ###
在cmd中输入：
```bash
$ jekyll -v
```
成功输出版本号说明安装成功。


## 开启本地实时预览 ##
切换到仓库所在目录，在cmd中输入:
```bash
$ jekyll serve
```

![](http://ww1.sinaimg.cn/mw690/7c08400ely1g2kxc3onxwj20fo0a63zh.jpg)
访问http://127.0.0.1:4000/即可看到效果。

>有时会遇到jekyll serve启动报错如下。这是因为jekyll默认使用4000端口，而4000是FoxitProtect（福昕阅读器的一个服务）的默认端口。最简单的办法就是指定端口，例如：

```bash
Incremental build: disabled. Enable with --incremental
      Generating...
jekyll 3.7.3 | Error:  Permission denied @ rb_sysopen - C:/Users/username/NTUSER.DAT
```

```bash
$ jekyll serve -P 5555
```

然后该写文章写文章，该自定义功能代码就自定义。。。。。。

## push到GitHub ##
本地博客做好，接下来就是上线了。跟普通项目流程基本一致。
首先新建一个项目，然后clone下来，把本地所有文件放进去先。（不是clone下来的或者从别的代码代管clone下来的都不行）

### 本地添加SSH ###
#### 1、首先需要检查你电脑是否已经有 SSH key  ####
运行 git Bash 客户端，输入如下代码：
```bash
$ cd ~/.ssh
$ ls
```
这两个命令就是检查是否已经存在 id_rsa.pub 或 id_dsa.pub 文件，如果文件已经存在，那么你可以跳过步骤2，直接进入步骤3。

#### 2、创建一个 SSH key ####
```bash
$ ssh-keygen -t rsa -C "your_email@example.com"
```
代码参数含义：  
-t 指定密钥类型，默认是 rsa ，可以省略。  
-C 设置注释文字，比如邮箱。
-f 指定密钥文件存储文件名。  

以上代码省略了 -f 参数，因此，运行上面那条命令后会让你输入一个文件名，用于保存刚才生成的 SSH key 代码，如：
```bash
Generating public/private rsa key pair.
# Enter file in which to save the key (/c/Users/you/.ssh/id_rsa): [Press enter]
```
当然，你也可以不输入文件名，使用默认文件名（推荐），那么就会生成 id_rsa 和 id_rsa.pub 两个秘钥文件。

接着又会提示你输入两次密码（该密码是你push文件的时候要输入的密码，而不是github管理者的密码），

当然，你也可以不输入密码，直接按回车（两次回车，一次输入，一次确认）。那么push的时候就不需要输入密码，直接提交到github上了。

#### 3、添加你的 SSH key 到 github上面去 ####
a、根据生成的文件地址找到对应的id_rsa.pub文件，用notepad++等工具打开将秘钥进行复制。

b、登录你的github账号，从右上角的设置（ Account Settings ）进入，然后点击菜单栏的 SSH key 进入页面添加 SSH key。

c、点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中，记得 SSH key 代码的前后不要留有空格或者回车。当然，上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名。默认的会使用你的邮件名称。
[![iYuNxe.png](https://s1.ax1x.com/2018/10/09/iYuNxe.png)](https://imgchr.com/i/iYuNxe)

#### 4、测试一下该SSH key ####
在git Bash 中输入以下代码
```bash
$ ssh -T git@github.com
```
当你输入以上代码时，会有一段警告代码，如：
```bash
The authenticity of host 'github.com (207.97.227.239)' can't be established.
# RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
# Are you sure you want to continue connecting (yes/no)?
```
这是正常的，你输入 yes 回车既可。如果你创建 SSH key 的时候设置了密码，接下来就会提示你输入密码，如：
```bash
Enter passphrase for key '/c/Users/Administrator/.ssh/id_rsa':
```
当然如果你密码输错了，会再要求你输入。当然前面你两次回车的话这里就不用管了。

注意：输入密码时如果输错一个字就会不正确，使用删除键是无法更正的。

密码正确后你会看到下面这段话，如：
```bash
Hi username! You've successfully authenticated, but GitHub does not
# provide shell access.
```
如果用户名是正确的,你已经成功设置SSH密钥。如果你看到 “access denied” ，者表示拒绝访问，那么你就需要使用 https 去访问，而不是 SSH 。

### 上传开始 ###
---
> 在博客目录右键git bash，输入以下代码：

```bash
git config --global user.email "你的GitHub邮箱"
git config --global user.name "你的GitHub用户名"
```
下面就可以正式发布了！
```bash
git add .
git commit -m "提交信息"
git push
```
没有报错的话，上传完毕就可以用"你的用户名.github.io"作为地址浏览了。

## 要一个更好记的域名？ ##
如果你觉得上面的域名不大好记，那可以去腾讯云或万网注册一个新的域名，然后添加解析到github.io空间上就可以了。  
PS：GitHub Pages有一个好处就是免于备案了，当然坏处就是空间和速度牺牲了一些，不过对于个人用户来说也足够了。

## 关于图片存储 ##
由于服务器速度和空间限制，我们最好的做法是把图片托管在网络图床上，可以推荐的有[七牛云](https://www.qiniu.com/)（但是这货需要你上传手持身份证照片才能给你10G，所以我放弃了）、[路过图床](https://imgchr.com/)（免注册，我现在正在用的）。
更新：最好的做法其实是新浪微博图床，这个可以自行搜索Chrome插件，非常好用，新浪微博的服务器绝对既快又稳定。
