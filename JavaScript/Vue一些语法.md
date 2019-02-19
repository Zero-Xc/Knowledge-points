## 结构目录
- index.html 单页面文件，spa所指的单页面
- main.js 程序入口文件，加载组件，挂载到单页面上
- App.vue 主组件，带vue后缀就是组件
- view 页面组件,可在script中通过import导入一些公共组件并重命名，通过组件名在页面中调用
- component 一些公共组件比如head或foot；效果点击组件
- util 公共方法组件
- store 状态管理及api
```
<router-view/>   <!--显示路由位置，嵌套路由，关联index.js-->
```
## 一些语法
- /根目录  ./当前目录 ../父级目录
- router  index.js 路由组件，其中含嵌套路由
- render: h => h(App),vue2写法，渲染一个视图，然后提供给el挂载，表示 Vue 实例选项对象的
render 方法作为一个函数，接受传入的参数 h 函数，返回 h(App) 的函数调用结果
- template 模板方法，只能有一个根元素，可写一个总的<div>
- Submenu 一种树形导航结构
- Breadcrumb 面包屑导航
- modal 模态框是覆盖在父窗体上的子窗体。通常，目的是显示来自一个单独的源的内容，
  可以在不离开父窗体的情况下有一些互动。子窗体可提供信息、交互等。
- export default 用于对外输出本模块（一个文件可以理解为一个模块）变量的默认接口
- mounted 对于前端来说，钩子函数就是指再所有函数执行前，我先执行了的函数，即 钩住 我感兴趣的函数，只要它执行，我就先执行。
- href= 'javascript：void(0)' 这个的含义是，让超链接去执行一个js函数,而不是去跳转到一个地址
- activated()：在vue对象存活的情况下，进入当前存在activated()函数的页面时，一进入页面就触发；可用于初始化页面数据等
- ‘==’与‘===’区别：不同类型间比较，==比较“转化成同一类型后的值”看“值”是否相等，===如果类型不同，其结果就是不等，若
  同类型比较，则两者结果相同
- html中使用驼峰命名的名称都要转换为短横分割命名，比如组件名或props名
  
## 一些指令
- v-cloak，解决初始化慢导致页面闪动的问题，与display:none连用
- v-once，表示组件只渲染一次
- v-if、v-else、v-else-if，根据表达式渲染或销毁元素
- v-show，改变display属性
- v-for，遍历数组或枚举一个对象
- v-on:click，监听一个点击事件，简写 @click
- v-model，用于在表单类上双向绑定数据，绑定一个静态字符串或者布尔值
- v-bind，可动态的更新DOM元素，即通过method或computed或钩子函数，简写 ：
- slot，子组件内备用内容，作用域是子组件，父组件模板中子组件内所有内容会替换子组件的slot内容
- this.$router.push()，methods里的点击跳转事件

## 代码解释
```
<script>
  var app=new Vue({  构造函数，根实例
    el：'#app'，      指定一个已存在的DOM元素，挂载Vue实例
    data:{           data用来声明需要双向绑定的数据（建议是应用内会用到的所有数据）
      message:''     文本插值{{ message }}会将双向绑定的数据实时显示
    }，              {{ }}中可以使用javascript进行简单计算、三元运算，但不支持语句(var num='1')和流控制
    created：function(){ el挂载前调用，只能初始化一些数据
    },
    activated():{      vue对象存活，一进入页面就触发，用于初始化数据
    },
    mounted:function(){ el挂载后调用，一般是一些业务逻辑
    },
    beforeDestroy:function(){ 实例销毁之前调用，解绑一些监听事件
    },
    methods:{
    this.message='111'   methods和钩子函数中的this都指向当前实例
    }
  })
```

## 项目中一些问题
- 导入组件不仅需要在script里import，还需在default export里的component里输出，格式为aBB,页面中调用```<a-BB>```
- div尽量不要使用绝对位置！调整窗口就会错位，解决办法：使用自适应布局，和单位em来进行相对定位。

## 关于导入vue组件快速开发:
```
首先安装element-ui依赖包
cd进入项目目录
  npm i element-ui -S
在main.js中导入
  import ElementUI from 'element-ui'
  import 'element-ui/lib/theme-chalk/index.css'
  Vue.use(ElementUI)
  
安装axios
cd进入项目目录
  npm install axios
  
在main.js中导入
  import axios from 'axios'
  Vue.prototype.$http = axios

在组件中使用methods中
  goLogin:function(){
            this.$http.get('/api/feign-consumer3')
            .then(res=>{
                //console.log(res)
                alert(res)
            }).catch(error=>{
                console.log(error)
            })
        }

axios跨域请求
  在config.js中加入
     proxyTable: {
      '/api': {
        target: 'http://localhost:9001',//设置你调用的接口域名和端口号 别忘了加http
        changeOrigin: true,
        pathRewrite: {
          '^/api': ''//这里理解成用‘/api’代替target里面的地址，后面组件中我们掉接口时直接用api代替  
                     //比如我要调用'http://40.00.100.100:3002 /user/add'，直接写‘/api/user/add’即可
        }
      }
    },
```
