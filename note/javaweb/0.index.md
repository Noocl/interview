> 本笔记来自于《深入理解JavaWeb开发技术 探索基于主流框架的最佳组合》.(谭贞军)

## 1.2 了解使用
### 1.2.1 Java发展历史
JavaSE：Java 2 Platform Standard Edition。Java平台标准版
JavaEE：Java 2 Platform Standard Edition。Java平台企业版
JavaME：Java 2 Platform Micro Edition。Java平台微型版

### 1.2.2 Java特点
面向对象、分布式、可移植、高性能、多线程、平台无关性。

---
## 1.3 Web技术介绍与工作原理
### 1.3.2 Web应用程序的工作原理
1. 浏览器向服务器发送请求
2. 服务器获取浏览器的请求
3. 服务器处理请求。如果请求页面是静态页面，直接返回；如果请求页面是动态页面，将处理后的结果发送给浏览器。
4. 服务器将处理后的结果返回给浏览器显示。

动态网页与静态网页不同，动态网页是指页面内容是动态交互的。

### 1.3.3 常用的Web开发技术
1. 静态Web开发技术
    - HTML技术
    - XML技术：eXtensible Markup Language，可扩展的标记语言
2. 动态Web开发技术
    - ASP技术：Active Server Page，动态网页
    - ASP.NET技术：
    - PHP
    - JSP

---
## 1.4 开发前的准备
### 1.4.2 配置环境变量
1. JAVA_HOME
2. CLSSSPATH：.;%JAVA_HOME%/lib/tools.jar;%JAVA_HOME%/lib/rt.jar;
3. PATH：%JAVA_HOME%/bin;
4. 查看版本：java -versinon

### 1.4.3 JRE和JDK的区别
1. JRE：Java Runtime Environment，Java运行时环境，是运行Java程序的必要条件。
2. JDK：Java SE Development Kit，Java标准版开发包。包括Java编译器，Java运行时环境，常用的Java类库。

---
## 1.5 配置Tomcat服务器
### 1.5.1 Tomcat目录介绍
1. bin：存放启动和关闭Tomcat的命令
2. conf：存放Tomcat的配置
3. lib：存放Tomcat服务器的核心类库，如果需要扩展Tomcat功能，可将第3方类库复制到该路径下。
4. logs：存放Tomcat每次运行后产生的日志。
5. temp：存放Web应用运行过程中生成的临时文件。
6. webapps：用于自动部署Web应用，将Web应用复制到该路径下，Tomcat会将该应用自动部署在容器中。
7. work：存放Web应用程序运行过程中编译生成的class文件，该文件夹可以删除，但每次启动Tomcat时，系统会再次建立该路径。

### 1.5.2 配置Tomcat的服务端口
打开tomcat/conf/server.xml，改port="8080"的值
<Connector port="8080" protocol="HTTP/1.1"
           connectionTimeout="20000"
           redirectPort="8443" />

### 1.5.3 列出Web要路径下的所有页面
打开tomcat/conf/web.xml，找到listings，改false为true。
<init-param>
    <param-name>listings</param-name>
    <param-value>false</param-value>
</init-param>    

### 1.5.4 登录控制台
输入localhost:8080后，页面右上角有3个控制台按钮，需要密码才可以登录。
1. Server Status：用于监控服务器的状态
2. Manager App：可以部署、监控Web应用，最常用。
3. Host Manager：实现站点管理。
可以D:\Dev\tomcat\apache-tomcat-9.0.14\webapps\manager\WEB-INF\web.xml中的如下等配置信息来配置tomcat-users.xml文件
  <security-role>
    <description>
      The role that is required to access the HTML Manager pages
    </description>
    <role-name>manager-gui</role-name>
  </security-role>
打开D:\Dev\tomcat\apache-tomcat-9.0.14\conf\tomcat-users.xml，打到<role><user>标签，改成如下内容
  <role rolename="manager-gui"/>
  <user username="aaaaaa" password="bbbbbb" roles="manager-gui"/>
即可登录。

### 1.5.5 设置虚拟目录
1. 新建目录D:\javaweb
2. 复制\webapps\ROOT\WEB-INFO目录到D:\javaweb
3. 打开\conf\server.xml文件，在<Host>和</Host>之前加入如下代码
<Context path="/javaweb" docBase="D:\javaweb"></Context>
4. 在D:\javaweb目录下创建index.html，输入哈哈。
5. 启动Tomcat，输入localhost:8080/javaweb，显示哈哈。



