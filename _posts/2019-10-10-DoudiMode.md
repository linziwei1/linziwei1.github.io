---
layout:     post
title:      "Windows斗帝模式"
subtitle:   "开启更为强大的设置项选择"
date:       2019-10-10 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - 新奇事物
    - 软件教程
---

### 简介 ###
---
斗帝模式，即"Kongburusi Mode”，或称为“完全控制面板”。是Windows 系统中隐藏的一个简单的文件夹窗口，包含了几乎所有Windows系统的设置，如控制面板的功能、界面个性化、辅助功能选项等方方面面的控制设置，用户只需通过这一个窗口就能实现所有的操控，而不必再去为调整一个小小的系统设置细想半天究竟该在什么地方去打开设置
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/doudimod1.png)

### 开启步骤 ###
---
#### 1、快捷键Win+R打开运行窗口 ####
在运行框中输入 regedit 然后点击【确定】

#### 2、跳转路径 ####
在方框处粘贴HKEY_CLASSES_ROOT\DesktopBackground\Shell回车跳转或一步一步找到此目录。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/doudimod2.png)

#### 3、创建斗帝模式项目 ####
点击【shell】后在右侧窗口鼠标右击选择【新建】选择【项】，将新建项命名为【斗帝模式】。其实名字起啥都可以。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/doudimod3.png)

同样的方法，点击刚刚创建的【斗帝模式】，右击选择【新建】选择【项】，命名为【command】。

#### 4、为【command】进行数值赋值 ####
点击【command】后双击右侧窗口中的【默认】，在数值数据处输入 explorer shell:::{ED7BA470-8E54-465E-825C-99712043E01C} 点击【确定】。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/doudimod4.png)

#### 5、大功告成，桌面调用 ####
在桌面空白处鼠标右击，斗帝模式选项已经成功添加了。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/doudimod5.png)

