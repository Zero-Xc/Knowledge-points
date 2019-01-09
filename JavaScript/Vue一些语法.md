## 结构目录
- index.html 单页面文件，spa所指的单页面
- main.js 程序入口文件，加载组件，挂载到单页面上
- App.vue 主组件，带vue后缀就是组件
- view 页面组件
- component 一些公共组件比如head或foot；效果点击组件
- util 公共方法组件
- store 状态管理及api
```
<router-view/>   <!--显示路由位置，嵌套路由，关联index.js-->
```
- router  index.js 路由组件，其中含嵌套路由
- render: h => h(App),vue2写法，渲染一个视图，然后提供给el挂载，表示 Vue 实例选项对象的
render 方法作为一个函数，接受传入的参数 h 函数，返回 h(App) 的函数调用结果
- template 模板方法
- Submenu 一种树形导航结构
- Breadcrumb 面包屑导航
- modal 模态框是覆盖在父窗体上的子窗体。通常，目的是显示来自一个单独的源的内容，
  可以在不离开父窗体的情况下有一些互动。子窗体可提供信息、交互等。
- export default 用于对外输出本模块（一个文件可以理解为一个模块）变量的默认接口
- mounted 对于前端来说，钩子函数就是指再所有函数执行前，我先执行了的函数，即 钩住 我感兴趣的函数，只要它执行，我就先执行。

## 关于导入vue组件快速开发:
```
首先安装element-ui依赖包
cd进入项目目录
  npm i element-ui -S
在main.js中导入
  import ElementUI from 'element-ui'
  import 'element-ui/lib/theme-chalk/index.css'
  Vue.use(ElementUI)
```
