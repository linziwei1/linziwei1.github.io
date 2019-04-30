---
layout:     post
title:      "Github Pages+Hexo博客全记"
subtitle:   "论挖坑与填坑心得"
date:       2018-10-1 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - Github
    - Hexo
    - Blog
    - MarkDown
    - Git
    - 图床
    - 云服务
---
## 建站 ##
> 这两天尝试搭建了Github Pages上的博客，用的Hexo，最直观的感觉跟WordPress比起来就是这个玩意儿太繁琐了。WordPress与之相比简直就是傻瓜一键式360度无值守操作。

> 不过同时这个带来的乐趣也是WordPress所不能比拟的，我这次又选用了一个教程不多的Theme来建站，其实现在内心里是后悔的。。。基本看了整个文件目录和官方文档，写这篇文章也是万一以后我要是域名出现了什么变动，好避过这些当年见过的坑。
>
> 话不多说，下面就进入正题。

## 系统环境配置 ##
要使用Hexo，首先需要在你的系统中支持Nodejs以及Git。
> [ 安装Node.js ](https://nodejs.org/download/)  
> 参考地址：
> [ Node.js ](http://www.w3cschool.cc/nodejs/nodejs-install-setup.html)  
> [ 安装git ](http://git-scm.com/download/)

下面安装Hexo  
```bash
	$ cd d:/hexo
	$ npm install hexo-cli -g
	$ hexo init blog
	$ cd blog
	$ npm install
	$ hexo g # 或者hexo generate
	$ hexo s # 或者hexo server，可以在http://localhost:4000/ 查看
```

除此之外还有一个hexo deploy (hexo d) 用来部署博客到远端（比如github, heroku等平台），这个后面会讲到。

现在我们打开[ http://localhost:4000/ ]( http://localhost:4000/ )已经可以看到一篇内置的blog了。

[![iYVuJe.jpg](https://s1.ax1x.com/2018/10/09/iYVuJe.jpg)](https://imgchr.com/i/iYVuJe)

## Hexo主题安装 ##
这里我选择了一个比较小众但很layout很好看的一个主题，与大名鼎鼎的Next相比教程确实少多了。

### 安装主题 ###
```bash
	$ hexo clean
	$ git clone https://github.com/huweihuang/hexo-theme-huweihuang themes/lin
```
### 启用主题 ###
修改Hexo目录下的_config.yml配置文件中的theme属性，将其设置为lin

### 更新主题 ###
```bash
	$ cd themes/lin
	$ git pull
	$ hexo g # 生成
	$ hexo s # 启动本地web服务器
```
现在打开[http://localhost:4000/](http://localhost:4000/) ，会看到我们已经应用了一个新的主题。

## 主题个性化 ##
主题的整体框架比较完备，无需进行多余的代码编写（以我的前端基础，也编写不出更好看的来= =）  
### 站点信息设置 ###
打开根目录下面的_config.yml进行编辑，可以修改站点信息、社交等，这里就不再详述，都是英文，可以根据对应项目进行设置，这里就挑几个重要设置项加以说明。  
值得注意的是这里的每一个设置项后都需要加一个空格，否则部署的时候会报错！！！
> 1.首先就是url: 设置为你的域名，在设置好之后需要创建一个CNAME的文件，没有后缀没有后缀没有后缀！里面的内容需要设置为你的域名，仅仅是域名，不需要加HTTP和www。  
> 
> 2.Writing设置的post_asset_folder默认值为false，这里我们可以把它设置为true。设置之后当我们每创建一个post的时候，就会在同目录下自动生成一个同名文件夹，这样的话我们就可以通过相对路径调用这个文件夹中的图片等资源。
> 
> 3.deploy的设置，这决定了你能否成功将网站同步至GitHub  
  	type: git  
  	repository: 这里填的是你GitHub的项目地址，在GitHub中可以直接复制到。  
  	branch: master  
>底部信息修改：blog\themes\lin\layout\_partial\footer.ejs

PS：这个theme中的Categories不可用，所以大家可以自行将导航栏中的这一项修改为别的链接，我的设置为了腾讯的公益404。  
这样设置完之后，不出什么意外的话我们就可以在本地预览成果了。  
那么关于主题的介绍就先告一段落了。

## 文章Post写作 ##
与WordPress应用了大量php和html作为后台和页面不同，Hexo中运用了大量的md页面，这也就导致了写文章时也需要用到md编辑器，这里我提供了一款很好用的Windows10平台可用的MarkdownPad 2（附激活码）。大家可点击下方链接下载：
[![iYeBV0.png](https://s1.ax1x.com/2018/10/09/iYeBV0.png)](https://imgchr.com/i/iYeBV0)
> 链接：[点此下载](https://pan.baidu.com/s/1qitNltRUgpHNpOZ1gtDjUA)
提取码：tnu6

关于markdown的语法介绍，我会在另一篇文章中详细说明。

## 本地blog上传至GitHub ##
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
> 前提条件：前面的_config.yml中配置好了deploy的地址
> 在博客目录右键git bash，输入以下代码：

```bash
	git config --global user.email "你的GitHub邮箱"
	git config --global user.name "你的GitHub用户名"
```
下面就可以正式发布了！
```bash
	hexo g #生成新的静态文件
	hexo  d #发布到GitHub
```
没有报错的话，就可以用"你的用户名.github.io"作为地址浏览了。

## 要一个更好记的域名？ ##
如果你觉得上面的域名不大好记，那可以去腾讯云或万网注册一个新的域名，然后添加解析到github.io空间上就可以了。  
PS：GitHub Pages有一个好处就是免于备案了，当然坏处就是空间和速度牺牲了一些，不过对于个人用户来说也足够了。

## 关于图片存储 ##
由于服务器速度和空间限制，我们最好的做法是把图片托管在网络图床上，可以推荐的有[七牛云](https://www.qiniu.com/)（但是这货需要你上传手持身份证照片才能给你10G，所以我放弃了）、[路过图床](https://imgchr.com/)（免注册，我现在正在用的）。

这样就差不多了，有别的再说吧！欢迎与我讨论更多细节！