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
<dependencies></dependencies> 编写项目依赖
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
