---
layout:     post
title:      "INTELLIJ IDEA安装插件与常用应用"
subtitle:   "Web项目、快捷键、Maven、Git、SSM、SpringBoot"
date:       2019-10-28 12:00:00
author:     "Lin Joey"
header-img: "img/post.jpg"
tags:
    - Java
    - 实用软件
    - IDE
---

## 一、INTELLIJ IDEA安装 ##
下载地址：https://www.jetbrains.com/idea/download/#section=windows  
#### 关于破解 ####
版本变动太快，直接Google百度去搜吧，有能力的直接入正也是极好的。  

#### 启动配置 ####
一路accept -> Darcula风格 -> Next: Default plugins -> Start using IntelliJ IDEA  

## 二、修改配置文件位置与项目界面配置 ##
> 一旦开始使用IDEA之后，就需要做很多的配置相关工作，使得IDEA越来越符合你的个人习惯，让你使用起来得心应手。而这些配置信息，都保存在C盘。而默认放在C盘是不好的习惯，一旦重装系统之后，所有的配置信息都丢失了，又要全部重头来过。所以需要修改配置文件的位置。  

以安装目录为E:\software\IntelliJ IDEA 2017.2为例。  
1、找到E:\software\IntelliJ IDEA 2017.2\bin\idea.properties，打开文件，修改如下两个位置。  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea1.png)  
2、再次启动后，就可以发现配置信息都保存在E:\software\IntelliJ IDEA 2017.2\.IntelljIIdea下了。   
3、**显示工具栏和工具按钮**：菜单->View->勾选 Toolbar和Tool Buttons  
4、**设置项目结构**：工具栏找到Project Structure -> Project，可进行JDK版本的设置。  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea2.png)  

## 三、增加Jar包 ##
>有时用到了第三方的类，同时又没有添加jar包，运行就会有异常抛出。  

1、下载Jar，复制在lib目录下(lib目录需要自己在项目根目录下手动创建)  
2、右键lib目录->Add as Library... ，弹出个对话框，点击ok  

## 四、安装插件 ##
**插件安装方法**：Settings -> Plugins，如下图所示：  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea3.png)  

以下为一些实用插件：  
#### 1、Background Image Plus ####
**作用**：更换背景  
**使用方法**：View -> Set Background Image  

#### 2、Mybatis Log Plugin ####
**作用**：直接将Mybatis执行的sql脚本显示出来，无需处理，可以直接复制出来执行  
**使用方法**：Tools -- >  Mybatis Log Plugin  打开其日志框，注意其转换的SQL不是输出到IDE的控制台  

#### 3、Grep Console ####
**作用**：由于Intellij idea不支持显示ascii颜色，grep-console插件能很好的解决这个问题， 可以设置不同级别log的字体颜色和背景色  
**使用方法**：Settings -> Other Settings  

#### 4、CodeGlance ####
**作用**：代码编辑区缩略图插件，可以快速定位代码，使用起来比拖动滚动条方便多了  

#### 5、GenerateAllSetter ####
**作用**：  
> 通过alt+enter对变量类生成对类的所有setter方法的调用  
> 当两个对象具有相同的字段时生成一个转换器  
> 当returnType为List Set Map时生成默认值  
> 在所有getter方法上生成对assertThat的调用  

#### 6、RestfulToolkit ####
**作用**：  
> 1.根据 URL 直接跳转到对应的方法定义 ( or Ctrl Alt N );  
> 2.提供了一个 Services tree 的显示窗口;  
> 3.一个简单的 http 请求工具;  
> 4.在请求方法上添加了有用功能: 复制生成 URL;,复制方法参数...  
> 5.其他功能: java 类上添加 Convert to JSON 功能，格式化 json 数据 ( Windows: Ctrl + Enter; Mac: Command + Enter )  

**使用方法**：安装后，右侧会有RestServices侧边栏，点击打开  
全局快捷搜索快捷键：Ctrl + \   

#### 7、Maven Helper ####
**作用**：分析依赖冲突插件，可用界面操作来方便显示maven的依赖树  
**使用方法**：打开项目中的pom文件，在底部会显示一个“Dependency Analyzer”，点击此按钮，切换到此工具栏。可执行如下操作：  
> Conflicts（查看冲突）  
> All Dependencies as List（列表形式查看所有依赖）  
> All Dependencies as Tree（树形式查看所有依赖）  
> 搜索功能  

#### 8、Json Parser ####
**作用**：用于验证和格式化JSON字符串的轻量级插件  

#### 9、aiXcode ####
**作用**：推荐使用！！！真正的提高编码效率！AI智能编程插件。aiXcoder主要两个功能：代码自动补全和相似代码智能推荐。  

#### 10、Alibaba Java Coding Guidelines ####
**作用**：阿里巴巴代码规范检查插件  
**使用方法**：在你需要检查的代码上面，点击右键，选择编码规约扫描  

#### 11、Material Theme UI ####
**作用**：更换主题，增加美观度。  
**使用方法**：安装后重启IDEA自动进入设置（貌似2019版本开始才会自动进入设置）  

## 五、常用快捷键 ##
#### 1、查找类 ####
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea8.png)  
#### 2、编辑类 ####
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea9.png)  
#### 3、编码常用 ####
> 直接输入psv就会看到一个psvm的提示，此时点击tab键一个main方法就写好了  
> 在方法体内键入for会有一个fori的提示，选中然后tab键，就会自动创建一个for循环  
> sout就是System.out.println();  


## 六、创建项目 ##
### 1、创建J2EE项目 ###
create new project -> Java ->JBoss -> Next -> Next -> 设置项目路径  

### 2、创建WEB PROJECT ###
以项目HelloServlet为例：  
（1）**新建项目**：菜单->File->New->Project->勾上 Web Application(3.1)->OK  
（2）**新建目录**：右键WEB-INF->New->Directory 新建两个目录：classes和lib目录  
（3）**新建HelloServlet**：选中src目录，然后右键鼠标->New->Servlet->输入HelloServlet  
（4）**导入jar包**：下载Jar，复制在WEB-INF的lib目录下。project structure -> Libraries -> 加号 -> 选中Java -> 指定项目路径\WEB-INF\lib\servlet-api.jar -> OK  
（5）**指定输出目录**：project structure -> 设置 project complier output 为项目路径\WEB-IN\classes  
（6）**配置Tomcat**：如下图红框那里下拉 -> Edit Configurations -> +号 -> Tomcat Servet -> Local -> name -> Configure.. -> Tomcat Home设为所在路径 -> Deployment -> 加号 -> Artifact... -> 自动生成 j2ee.war ->OK -> 运行 -> 当出现j2ee.war deployed successfully的时候，就表示部署成功了  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea5.png)  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea6.png)  
（7）输入地址http://localhost:8080/ ，查看效果   
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea7.png)  

### 3、导入ECLIPSE DYNAMIC WEB PROJECT动态WEB项目 ###
项目目录以e:\project\j2ee为例  
（1）Import Project -> 选择项目目录e:\project\j2ee -> Create project from existing sources ->下一步 -> 导入项目  
（2）创建Artifacts：菜单-> File -> Project Structure -> Artifacts -> 加号 -> Web Application Exploded -> from Module -> j2ee -> ok -> ok  
（3）配置Tomcat，启动。  

## 七、Maven ##
### 1、介绍 ###
Maven （专家）是专门用于构建和管理Java相关项目的工具。  

###  2、用处 ###
（1）使用Maven管理的Java 项目都有着相同的项目结构  
> 1. 有一个pom.xml 用于维护当前项目都用了哪些jar包  
> 2. 所有的java代码都放在 src/main/java 下面  
> 3. 所有的测试代码都放在src/test/java 下面  

（2）统一维护jar包  
maven风格的项目，首先把所有的jar包都放在"仓库“ 里，然后哪个项目需要用到这个jar包，只需要在pom.xml 里给出jar包的名称和版本号就行了。 这样jar包就实现了共享。  

### 3、Maven的下载与配置 ###
（1）**官方最新版下载地址**：http://maven.apache.org/download.cgi  
（2）**环境变量配置**：环境变量-系统变量-Path-添加maven安装目录\bin   
（3）**检验版本**：命令行输入mvn -v。  

### 4、仓库 ###
所谓的仓库就是用于存放项目需要的jar包的。maven采用一个仓库，多个项目的方式，让多个项目共享一个仓库里的相同jar包。  
（0）**配置文件的位置**：apache-maven-3.5.0\conf\settings.xml  
（1）**仓库默认位置**：配置文件第52行指定了仓库的位置是${user.home}/.m2/repository。
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea10.png)  
（2）**修改仓库位置**：在配置文件第55行写入  
```bash
<localRepository>E:\Software\maven\repository</localRepository>
```
（3）**修改jar包下载服务器**：maven官方提供的服务器速度慢，改为阿里云。配置文件修改位置是160-165行：   
```bash
<mirror>
            <id>alimaven</id>
            <mirrorOf>central</mirrorOf>
            <name>aliyun maven</name>
            <url>http://maven.aliyun.com/nexus/content/repositories/central/</url>
</mirror>
```

### 5、IDEA配置 ###
完成了MAVEN准备工作之后，进行IDEA settings：File->Other Settings->Default Settings.. ->Build, Execute, Deployment->Build Tools->Maven。  
修改 Maven home directory为E:\Software\maven，修改User settings file为E:\Software\maven\conf\settings.xml。  
如此这般，IDEA中的maven就准备好了，并且是使用本地库。  

### 6、IDEA新建Maven J2SE Project ###
（1）**新建Maven项目**：Create new project -> 左边选择Maven -> Create from archetype -> org.apache.maven.archetypes:maven-archetype-quickstart -> Next  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea11.png)  
（2）设置GroupId（如com.linjava）和ArtifactId（如j2se）  
（3）配置maven 目录 -> 确认创建项目 -> 此时，Maven项目创建了，IDEA还会做一些初始化的工作，那么需要点击右下角的 Import Changes -> Maven Import之后，就会得到一个经典的Maven项目，并且有一个附送的App.java类。  

### 7、Maven增加Jar包 ###
http://mvnrepository.com/  可以直接下载jar，也可以复制maven代码。  
（0）网上下载jar包安装到仓库中 ：  
（1）**以hutool为例**：记录下网站的依赖代码。安装命令如下  
```bash
<!-- https://mvnrepository.com/artifact/cn.hutool/hutool-all -->
网站依赖代码示例：
<dependency>
    <groupId>cn.hutool</groupId>
    <artifactId>hutool-all</artifactId>
    <version>4.3.1</version>
</dependency>
安装命令：
mvn install:install-file -Dfile=jar包的位置(参数一) -DgroupId=groupId(参数二) -DartifactId=artifactId(参数三) -Dversion=version(参数四) -Dpackaging=jar
```
（2）**更新仓库**：显示“Buid Success”安装成功。安装成功后在IDEA的Settings -> Build,Execution,Deployment -> Build Tools -> Maven -> Repositories -> 选中本地仓库，Update -> OK。  
（3）**修改pom.xml**，24-28行附近添加maven代码。或者也可以直接Alt + Insert搜索本地的jar包选择添加依赖。  
```java
<dependency>
    <groupId>cn.hutool</groupId>
    <artifactId>hutool-all</artifactId>
    <version>4.3.1</version>
</dependency>
```
（4）**Maven import**：在修改了pom.xml之后，IDEA上会弹出Maven projects need to be imported，点击Import Changes  
（5）再次执行。  

### 8、IDEA新建Maven J2EE Web Project ###
（1）**新建Maven项目**：Create new project -> 左边选择Maven -> Create from archetype -> 选中 org.apache.maven.archetypes:maven-archetype-webapp -> Next  
（2）设置GroupId（如com.linjava）和ArtifactId（如j2ee）  
（3）配置maven 目录 -> 确认创建项目 -> 每次新建Maven项目，或者pom.xml有改动，都会有这个提示，这次点击Enable Auto-Import，自动导入，省掉麻烦  
（4）**新建java源代码目录**：maven web项目默认是没有java源代码目录的，所以需要手动创建。右键main目录-> New->Directory->输入java->右键java->Mark Directory as-> Sources Root  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea12.png)  
（5）右键java->New->Servlet->HelloServlet（如果New里没有Servlet，需要在j2ee.iml里对应位置添加如下代码，之后关闭项目重新打开）  
```bash
	<sourceRoots>
		<root url="file://$MODULE_DIR$/src/main/resources" />
		<root url="file://$MODULE_DIR$/src/main/java" />
	</sourceRoots>
```
（6）修改web.xml,添加/hello映射。  
```xml
<web-app>
  <display-name>Archetype Created Web Application</display-name>
    <servlet>
        <servlet-name>HelloServlet</servlet-name>
        <servlet-class>HelloServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>HelloServlet</servlet-name>
        <url-pattern>/hello</url-pattern>
    </servlet-mapping>
</web-app>
```
（7）**修改pom.xml**：添加servletjar包依赖。  
（8）配置Tomcat，启动。访问localhost：8080查看效果。  

### 9、IDEAMAVEN - 父子-聚合项目 ###
（1）**父子-聚合项目**： 所谓的父子项目，即有一个父项目，有多个子项目。这些子项目，在业务逻辑上，都归纳在这个父项目下，并且一般来说，都会有重复的jar包共享。  
（2）**新建父项目**：Create new project -> 左边选择Maven -> Create from archetype -> org.apache.maven.archetypes:maven-archetype-quickstart -> Next -> 填信息名字（ArtifactId为parentMavenProject） -> Finish  
（3）**修改pom.xml**：idea 自动生成的 pom.xml 有一大堆东西，很多都用不着。  
```bash
	1、<packaging>jar</packaging>修改为<packaging>pom</packaging>
	2、增加 hutool jar 和 junit 包的依赖，用于后来子项目里观察对其的调用。
	<dependencies>
    <dependency>
      <groupId>junit</groupId>
      <artifactId>junit</artifactId>
      <version>4.11</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>cn.hutool</groupId>
      <artifactId>hutool-all</artifactId>
      <version>4.3.1</version>
    </dependency>
  </dependencies>
```
（4）**创建子项目**：子项目其实是maven module。右键点击 parentMavenProject->New->Module。左边选择Maven -> Create from archetype -> org.apache.maven.archetypes:maven-archetype-quickstart -> Next -> 填信息名字（AitifactId为childMavenProject） -> Finish。  
（5）**TestHutool**：在 childMavenProject 下新建 TestHutool类，并运行。输出“2012-12-12 12:12:12”。可以发现，是可以使用 hutool jar 里的类的。 这说明子项目，能够使用 父项目中的 jar 包了。  
```java
	package childMavenProject;
	import java.util.Date;
	import cn.hutool.core.date.DateUtil;
	public class TestHutool {
 	   public static void main(String[] args) {
	        String dateStr = "2012-12-12 12:12:12";
 	       Date date = DateUtil.parse(dateStr);
    	    System.out.println(date);
  	  }
	}
```
（6）分别查看父子项目的pom.xml  
> 观察子项目的 pom.xml ，可以发现它多了个 parent, 这个就是对父项目的依赖。  
> 再打开父项目的 pom.xml ,可以发现它多了一个模块modules, 就表示对子项目的关联。  

（7）**项目结构**：如果有多个 childMavenProject，他们都是位于 parentMavenProject下面的。这就方便管理了。  

### 10、 IDEA 创建的 MAVEN项目手动添加resources目录 ###
（1）菜单 -> File -> Project Structure -> Modules -> Sources -> 右键点击 main -> New Folder -> resources.  
（2）**标记为资源目录**：右键 resources -> Resources.  


## 八、Git ##
### 1、简介 ###
比如一个项目，两个人同时参与开发，那么就把这个项目放在一个**公共的地方**，需要的时候都可以去获取，有什么改动，都可以进行提交。  
为了做到这一点，就需要一个版本控制系统，Git就是这样一个免费、开源的分布式版本控制系统，用于敏捷高效地处理任何或小或大的项目。  
一般选用Github作为代码托管平台。  

### 2、安装Git ###
一路默认，需要注意的是设置环境变量时选择Git from the command line and also from 3rd-party software，这样在dos命令下可以方便使用git.exe 命令。之后一路默认。  
安装完毕后，cmd输入git，查看是否安装成功。  

### 3、IDEA配置Git ###
（1）**为IDEA指定git路径**：默认情况下，IDEA是不自带git运行程序的，所以需要通过
菜单->settings->Version Control->Git->Path to Git executable: 设置为安装git中所安装的git.exe  
（2）**设置github账号**：菜单->settings->Version Control->GitHub->Create API Token  
（3）设置好了之后，IDEA的git准备工作就做好了  

### 4、IDEA pull项目 ###
（1）**checkout新建分支**：菜单->VCS->Checkout from Version Control->GitHub  
（2）**输入项目参数**：Git Repositor URL：项目链接；Parent Directory：路径；Directory Name：项目名称。然后点击 Clone。  
（3）如此就拿到了Git上的项目  

### 5、IDEA本地项目创建在Github上 ###
（1）**在github创建一个仓库**：New repository创建仓库New repository。输入仓库名称helloworld。创建成功得到地址：https://github.com/linziwei1/helloworld   
（2）**在本地创建一个项目**：本地创建一个项目helloworld，并且新建一个Java类，输出hello world！  
（3）**建立本地仓库**：菜单->VCS->import into Version Control->Create Git Repository->E:\JavaProject\helloworld  
（4）**把项目加入到本地仓库**：右键项目->Git->Add  
（5）**提交项目**：右键项目->Git->Commit Directory之后弹出如图所示的窗口，在Commit Message 输入 test， 然后点击 Commit And Push  
![](https://linjoey-image.oss-cn-beijing.aliyuncs.com/idea13.png)  
（6）**Push Commit**：这里会询问你要提交的哪里去，点击Define remote,并输入name：helloworld。url：https://github.com/linziwei1/helloworld 。继续点push。  
（7）再次刷新github地址，就可以看到上传成功了。   

### 6、GIT - 提交和更新 ###
（1）**提交改动**：在代码变更之后，使用快捷键CTRL+K,就会弹出提交的界面，点击Commit and Push即可。  
（2）**更新**：点击快捷键Ctrl+T，就会弹出更新的界面，点击OK即可。  

## 九、IDEA与SSM项目 ##
### 1、IDEA导入SSM项目 ###
例如有一个现成的SSM项目，目录在E:\JavaProject\ssmtest  
（1）**导入项目**：File->New->Project from existing sources 输入  
```bash
E:\JavaProject\ssmtest\pom.xml
```
注：这里一定要指定pom.xml文件，而非目录。后续的就一直点Next就行了  
（2）**启动Tomcat**  
（3）**测试**：访问http://localhost:8080/ssm/listCategory  
注：为了在访问路径里使用ssm,必须把Tomcat配置界面的Deployment的Application context/设置为ssm，否则只能用http://localhost:8080/listCategory 路径访问了  

### 2、调试 ###
（1）在Tomcat的Deploy对应的 Artifacts这里，需要选择war exploded, 不要选择第一个war。因为选war的话，每次修改了jsp都要重新打包成war才能看到效果，不便于观察jsp修改后的效果  
（2）在Tomcat的Server 下面两个 On ： 都设置为 Update classes and resources.其作用是把类和资源文件修改同步更新掉。  
On 'Update' action 是手动更新，或者点击快捷键CTRL+10更新。  
On frame deactivation 是当idea失去焦点，比如打开浏览器的时候自动更新。  
所以都勾上就好了  
（3）**使用Debug模式运行**：运行Tomcat的时候，采用debug模式，这样 勾上 Update classes and resources 这一步导致的类自动更新就会引起Tomcat的reload，那么就不需要重新启动Tomcat也能看到效果了，便于修改代码和观察效果。  

### 3、IDEA 无法正确识别@AUTOWIRED ###
（1）IDEA有时候无法正确地识别 @Autowired ，并发出不应该的报错  
（2）**解决方法**：把这个报错级别，设置为Warning就好了。  
File->Settings->Editor->Inspections->Spring->Spring Core->Code->Autowiring for Bean Class-> 从Error 修改为Warning 就好了。  

## 十、IDEA与SpringBoot ##
### 1、IDEA创建SpringBoot项目 ###
（1）**创建项目**：菜单 -> New -> Project -> Spring Initializr 然后点 Next。输入Group和Artifact，之后Next。  
（2）**选择Web 模块**：左边选择 Web, 右边只勾选 Web 即可，然后点击Next。指定项目路径之后项目就创建成功了。  
（3）项目创建好之后，就自带一个SpringbootApplication, 其被@SpringBootApplication 所标记，表示这个是一个Springboot 应用。  

### 2、IDEA导入SpringBoot项目 ###
（1）**导入项目**：菜单->File->New->Project From Existing Sources->选中项目文件地址->指定pom.xml文件->点击OK，然后后面就一路 Next 就行了  
（2）因为是 maven 项目，所以在本地库没有 springboot 相关 jar 的前提下， idea 就会去进行下载。一旦下载完成，就会展现为maven 风格的项目结构。  
（3）运行启动类 Application，然后访问地址:http://127.0.0.1:8080/  
注：不同的springboot项目的启动类是不一样的，不见得都是访问这个地址。  