vue推荐开发环境:  

    Node.js: javascript运行环境(runtime),不同系统直接运行各种编程语言  

    npm: Nodejs下的包管理器。由于国内使用npm会很慢,这里推荐使用淘宝NPM镜像（http://npm.taobao.org/）  
    $ npm install -g cnpm –registry=https://registry.npm.taobao.org  

    webpack: 它主要的用途是通过 CommonJS 的语法把所有浏览器端需要发布的静态资源做相应的准备，比如资源的合并和打包。  

    vue-cli: 用户生成Vue工程模板  

 1.安装node.js  
从node.js官网下载并安装node，安装过程很简单，一路“下一步”就可以了（傻瓜式安装）。

安装完成之后，打开命令行工具，输入 node -v，如下图，如果出现相应的版本号，则说明安装成功。  

 2.npm包管理器，是集成在node中的，所以，直接输入 npm -v就会如下图所示，显示出npm的版本信息.  
 
 3.安装cnpm  

由于有些npm有些资源被屏蔽或者是国外资源的原因，经常会导致用npm安装依赖包的时候失败，所有我还需要npm的国内镜像—cnpm。 

在命令行中输入 npm install -g cnpm –registry=http://registry.npm.taobao.org 然后等待。  
  
出错解决方案  

首先输入以下命令并回车

npm set registry https://registry.npm.taobao.org # 注册模块镜像  
npm set disturl https://npm.taobao.org/dist # node-gyp 编译依赖的 node 源码镜像  
npm cache clean --force # 清空缓存  
然后再运行  
npm install -g cnpm --registry=https://registry.npm.taobao.org  
  
  4.安装vue-cli 脚手架构建工具           
在命令行中运行命令 npm install -g vue-cli ，然后等待安装完成。
