### 问题1：后端返回数据为XML
- 可能原因1：引入了eureka，导致返回格式xml优先级高级json  
controller前添加注解 @RequestMapping(produces = MediaType.APPLICATION_JSON_UTF8_VALUE)
- 可能原因2：mapper中entity与数据库属性映射错误，需要属性名与数据库名一致；若为属性，则需要在属性前加@Param  
  
### 问题2：axios发送post请求格式参数为data；发送get格式参数为params
```
export function login(name, psd) {
  return request({        //把数据传送给后台，后台进行验证返回token
    url: '/login',  //携带参数，转到mock/index.js再转到mock/user.js  +username
    method: 'post',
    data: {
      username:name,
      password:psd,
    }
  })
}
```

### 问题3：firebox浏览器查看发送的请求
- 页面空白处右键，选择 查看元素，控制器可以看到输出日志（程序中使用console.log("") ），网络中可以看到请求的参数和返回的参数

### 问题4：controller接受参数的注解
- @RequestParam  接受URL中的参数，即获取get参数
- @RequestBody   接受请求体中参数，即获取post参数
- @PathVariable  动态参数，将形参绑定到@RequestMapping中URL的占位符

### RESTful API
```
  -/order/1 HTTP GET ：得到 id = 1 的 order 
	- /order/1 HTTP DELETE：删除 id = 1的 order 
	- /order/1 HTTP PUT：更新id = 1的 order 
	- /order HTTP POST：新增 order
```
