## scss语法
### vue中安装scss模块
```
npm install --save-dev sass-loader
npm install --save-dev node-sass
```
```
<style lang="scss" scoped>
$bg:#FFFFFF; //表示背景色变量
.main{
 width:200px;
 .body{      //可直接通过类型选择器使用
    width:100px;
 }
}
</style>
```
