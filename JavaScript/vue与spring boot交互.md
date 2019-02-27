## 问题1：引入Eureka模块后，后端返回数据为XML
- controller前添加注解 @RequestMapping(produces = MediaType.APPLICATION_JSON_UTF8_VALUE)
## 问题2：axios发送post请求格式
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
## 问题3：controller接受POST请求参数
- 形参前加注解  @RequestBody，需注意形参类型最好是bean，若为字符串可能会返回xml？？

## 问题4：firebox浏览器查看发送的请求
- 页面空白处右键，选择 查看元素，控制器可以看到输出日志（程序中使用console.log("") ），网络中可以看到请求的参数和返回的参数
