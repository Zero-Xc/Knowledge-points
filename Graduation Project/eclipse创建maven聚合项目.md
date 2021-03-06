## pom.xml项目结构
```
<groupId></groupId>  组织标识
<artifactId></artifactId>  项目名称
<version></version>  当前版本号
<packaging></packaging> 打包格式
<name></name>  项目名称  

<parent>    指明需要继承的另一个maven项目
   <relativePath/>   当两个项目的目录结构不是父子关系，用来描述父项目位置
</parent> 

<properties></properties>  属性设置，包括jdk版本号等

<modules></modules>  聚合项目，在编译被聚合项目的同时会将聚合项目一起编译

<dependencies></dependencies> 编写项目依赖，会导入实际jar包

<dependencyManagement></dependencyManagement> 若dependencies 里的 dependency 自己没有声明 version 元素，
那么maven 就会到 depenManagement 里去找有没有该jar包的artifactId 和 groupId，若存在，则继承它，
若没有则报错。如果dependency声明一个version，dependencies 中的 dependency 也声明了version，
则 dependencyManagement 中的声明无效

<dependencies>和<dependencyManagement>区别
所有声明在dependencies 里的依赖都会自动引入，并默认被所有的子项目继承
dependencies 即使在子项目中不写该依赖项，那么子项目仍然会从父项目中继承该依赖项（全部继承）
dependencyManagement 只是声明依赖的版本号，该依赖不会引入，因此子项目需要显示声明所需要引入的依赖，若不声明则不引入
子项目声明了依赖且未声明版本号和scope，则会继承父项目的版本号和scope，否则覆盖


<build>  全局配置
   <plugins>   使用指定插件
   <repositories> 配置maven项目远程仓库
   <pluginRepositories> 插件的远程仓库
</build> 
```

## 首先创建一个maven项目
- 点击file，点击new，点击maven project，输入Group Id：项目的包路径，Artifact Id：项目名称
- 注意Packaging：以何种方式打包，父项目需选pom，子maven项目是jar或war
- 右键项目名点击 new，选择 maven module，键入module name：子项目名称，一直到finsh即可
- 建立完目录结构，子项目中jdk都要改至与父项目一致。

## POM项目使用模板,版本号需要注意问题
```
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<groupId>com.demo</groupId>
	<artifactId>demo</artifactId>
	<version>0.0.1-SNAPSHOT</version>
	<name>demo</name>
	<description>Demo project for Spring Cloud demo</description>
	
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.1.2.RELEASE</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>

	<properties>
		<java.version>1.8</java.version>
		<spring-cloud.version>Greenwich.RC2</spring-cloud.version>
	</properties>

	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>   <!-- 全栈web开发模块 -->
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
		</dependency>
      <dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.cloud</groupId>
				<artifactId>spring-cloud-dependencies</artifactId>
				<version>${spring-cloud.version}</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>
	
	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

	<repositories>
		<repository>
			<id>spring-milestones</id>
			<name>Spring Milestones</name>
			<url>https://repo.spring.io/milestone</url>
		</repository>
	</repositories>


</project>

```
