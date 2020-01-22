---
layout:     post
title:      "JDK&JRE安装教程"
subtitle:   "开启JAVA编程的第一步"
date:       2019-10-24 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - Java
    - Java Web
---

> 要进行Java开发，需要先安装JDK和JRE。  
> 关于两者的区别，《深入理解Java虚拟机：JVM高级特性与最佳实践（第2版）》中是这样解释的：  
> 我们可以把Java程序设计语言、Java虚拟机、Java API 类库这三部分统称为 JDK（Java Development Kit），JDK 是用于支持 Java 程序开发的最小环境。  
> 另外，可以把 Java API 类库中的 Java SE API 子集和 Java 虚拟机这两部分统称为 JRE（Java Runtime Environment），JRE 是支持 Java 程序运行的标准环境。  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall1.png)


### 1、下载JDK ###
JDK 可以到官网下载
http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html
现在Oracle学坏了，必须登录才能下载，安全起见尽量不要在第三方下载，所以方便的话注册一个。

> 注意区分：
> Java SE Development Kit 8u25	//java se开发包  
> Java SE Development Kit 8u25 Demos and Samples Downloads  //java se开发包+示例  
> JavaFX Demos and Samples Downloads  //javaFX开发包和示例  
> 第一个是必须的  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall2.png)


### 2、安装Jdk和Jre ###
打开刚刚下载好的安装文件，选择安装目录，安装过程中会出现两次安装提示 。
第一次是安装 jdk ，第二次是安装 jre 。建议两个都安装在同一个java文件夹中的不同文件夹中。


### 3、配置环境变量 ###
配置环境变量：右击“我的电脑”-->“属性”-->"高级系统设置"-->"环境变量"。

####  (1)JAVA_HOME环境变量 ####
**作用：**
它指向jdk的安装目录，Eclipse/NetBeans/Tomcat等软件就是通过搜索JAVA_HOME变量来找到并使用安装好的jdk。
**配置方法：**
在系统变量里点击新建，变量名填写JAVA_HOME，变量值填写JDK的安装路径。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall3.png)

####  (2)CLASSPATH环境变量 ####
**作用：**
是指定类搜索路径，要使用已经编写好的类，前提当然是能够找到它们了，JVM就是通过CLASSPTH来寻找类的。我们需要把jdk安装目录下的lib子目录中的dt.jar和tools.jar设置到CLASSPATH中，当然，当前目录“.”也必须加入到该变量中。
**配置方法：**
系统变量中新建CLASSPATH变量，变量值为：.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar 
```bash
CLASSPATH：
.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;
```
> 注意不要忘记前面的点和中间的分号。且要在英文输入的状态下的分号和逗号。  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall4.png)

####  (3)path环境变量 ####
**作用：**
指定命令搜索路径，在命令行下面执行命令如javac编译java程序时，它会到PATH变量所指定的路径中查找看是否能找到相应的命令程序。我们需要把jdk安装目录下的bin目录增加到现有的PATH变量中，bin目录中包含经常要用到的可执行文件如javac/java/javadoc等待，设置好PATH变量后，就可以在任何目录下执行javac/java等工具了。
**配置方法：**
在系统变量里找到Path变量，这是系统自带的，不用新建。双击Path，win10系统不需要加分号了，直接点击新建分别添加以下两条路径即可。
```bash
%JAVA_HOME%\bin
%JAVA_HOME%\jre\bin
```
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall5.png)

### 4、测试Java开发环境是否安装成功 ###
快捷键：win+R，输入cmd，回车
分别输入java，javac， java -version，如果显示下图，则说明安装成功。如果显示别的，说明环境变量配置出了问题，需要根据以上步骤重新检查是否哪一步复制粘贴错误。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall6.png)
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall7.png)
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/javainstall8.png)