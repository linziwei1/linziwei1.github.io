---
layout:     post
title:      "Sublime Text 3安装与配置、插件"
subtitle:   "安装配置教程与常用插件集合"
date:       2019-10-27 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - 前端
    - 实用软件
---

## 一、Sublime Text 3安装 ##
Sublime Text是一个代码编辑器，也是HTML和CSS先进的文本编辑器。Sublime Text是由程序员Jon Skinner于2008年1月份所开发出来，它最初被设计为一个具有丰富扩展功能的Vim。

Sublime Text具有漂亮的用户界面和强大的功能，例如代码缩略图，Python的插件，代码段等。还可自定义键绑定，菜单和工具栏。Sublime Text 的主要功能包括：拼写检查，书签，完整的 Python API ， Goto 功能，即时项目切换，多选择，多窗口等等。Sublime Text 是一个跨平台的编辑器，同时支持Windows、Linux、Mac OS X等操作系统。

它就相当于文本编辑器中的Chrome，自身没有什么捆绑，你需要什么就自己装什么。

#### 下载 ####
对于一切软件，都应该有去官网下载版本的优良传统。

#### 激活注册 ####
1、hosts文件修改
文件路径(博主是64位系统)：C:\Windows\System32\drivers\etc\hosts
记事本打开追加以下内容：
```bash
127.0.0.1 www.sublimetext.com
127.0.0.1 sublimetext.com
127.0.0.1 sublimehq.com
127.0.0.1 license.sublimehq.com
127.0.0.1 45.55.255.55
127.0.0.1 45.55.41.223
0.0.0.0 license.sublimehq.com
0.0.0.0 45.55.255.55
0.0.0.0 45.55.41.223
```

2、打开软件 -> HELP选项 -> 输入注册码选项 -> 填写以下key
```bash
----- BEGIN LICENSE -----
Member J2TeaM
Single User License
EA7E-1011316
D7DA350E 1B8B0760 972F8B60 F3E64036
B9B4E234 F356F38F 0AD1E3B7 0E9C5FAD
FA0A2ABE 25F65BD8 D51458E5 3923CE80
87428428 79079A01 AA69F319 A1AF29A4
A684C2DC 0B1583D4 19CBD290 217618CD
5653E0A0 BACE3948 BB2EE45E 422D2C87
DD9AF44B 99C49590 D2DBDEE1 75860FD2
8C8BB2AD B2ECE5A4 EFC08AF2 25A9B864
------ END LICENSE ------
```


## 二、关于汉化 ##
编程软件的英文其实就那么来来回回一批单词，能不汉化还是别汉化了，用习惯了还是很必要的。
不然哪天别人找你帮忙解决个问题，菜单都不认识多丢人=。=


## 三、安装插件的前提Package Control ##
Package Control非常重要，因为这关系到后面的st3 安装包的使用。有两种方法：
#### 1、自动安装 ####
按Ctrl+ ` (此符号为tab按键上面的按键) 调出console（注：避免热键冲突）
或者菜单中的“view -> Show Console”
访问https://packagecontrol.io/installation#st3 ，粘贴以下代码到命令行并回车：
```bash
import urllib.request,os,hashlib; h = '6f4c264a24d933ce70df5dedcf1dcaee' + 'ebe013ee18cced0ef93d5f746d80ef60'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```
如果安装成功，菜单“preferences”中就会出现Package Settings 和Package Control 这两个项，

#### 2、手动安装 ####
自动安装失败时，就用手动安装。
到https://packagecontrol.io/installation 官网，右边有一个“Package Control.sublime-package”，点击下载，然后将文件拷贝到 Installed Packages文件夹中。


## 四、安装插件 ##
> 对于Sublime Text 3,它之所以轻巧，是因为它设计就是为了让你按需加载，根据自己的需要，去下载对应的插件，所以才不会像其他的IDE那样笨重。
> 
>安装插件步骤是：“Preferences -> Package Control”(快捷键是：shift+ctrl+p),然后执行“Package Control: Install Package”,接在就是输入你要安装的插件就可以。

以下为一些实用插件：
#### 1、Emmet ####
作用：快速编写HTML，CSS规范代码
示例：html5+tab,div#box+tab
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/emmet.gif)

#### 2、html5 ####
支持html5规范的插件包
注意：与Emmet插件配合使用，效果更好
使用方法：新建html文档>输入html5>敲击Tab键>自动补全html5规范文档

#### 3、jQuery ####
支持JQuery规范的插件包

#### 4、 javascript-Completions ####
支持Javascript、JQuery、Twitter Bootstrap框架、HTML5标签属性提示的插件，是少数支持sublime text 3的后缀提示的插件，HTML5标签提示sublime text 3自带，不过JQuery提示还是很有用处的，也可设置要提示的语言。

#### 5、JSFormat ####
JS代码格式化插件。
使用方法：使用快捷键ctrl+alt+F

#### 6、SublimeLinter ####
作用：一个支持lint语法的插件，可以高亮linter认为有错误的代码行，也支持高亮一些特别的注释，比如“TODO”，这样就可以被快速定位。

#### 7、SublimeCodeIntel ####
作用：代码提示插件，可以帮你补全代码，快速方便书写！大大提升效率！
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/SublimeCodeIntel.gif)

#### 8、BracketHighlighter ####
作用：类似于代码匹配，可以匹配括号，引号等符号内的范围。
使用方法：系统默认为白色高亮，可以使用链接所述方法进行自定义配置

#### 9、Alignment ####
作用：该插件是用来对齐的，选中几行，可一键对齐。
快捷键：默认的是ctrl+alt+a（与qq截图刚好冲突，建议修改）
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/alignment.gif)

#### 10、Ctags ####
作用：函数跳转
使用方法：Alt+点击 函数名称，会跳转到相应的函数

#### 11、DocBlocker ####
作用：注释插件，生成优美的注释。标准的注释，包括函数名、参数、返回值等，并以多行显示，省去手动编写。
使用方法：Preference -> Package Settings -> DocBlockr -> Settings - User，输入如下代码：
```bash
{"jsdocs_extra_tags":["@Author Hybrid","@DateTime {{date}}","@copyright ${1:[copyright]}","@license ${1:[license]}","@version ${1:[version]}"],"jsdocs_function_description":false}
```
效果展示：
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/DocBlocker.gif)

#### 12、SideBarEnhancements ####
作用：增强侧边栏，可用于代码效果的浏览器预览。类似于DW。
使用方法：菜单栏view -> Side Bar -> show side bar
效果如下图：
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/SideBarEnhancements.png)


## 五、删除插件 ##
ctrl + shift + p 或 菜单中的“view -> Show Console”。输入：
```bash
Package Control:Remove Package
```
选择要删除的插件，删除。
