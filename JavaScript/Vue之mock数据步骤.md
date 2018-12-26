基于vue-cli 2.9。此版本下构建webpack项目中去除了dev-server.js和dev-client.js两个文件，  
所以通过其插件的api（devServer.before）来接口数据。  
操作如下：  
根目录下新建mock文件夹，文件夹下新建testList.json,并存入一些json串  
在build文件夹下的webpack.dev.config.js中加入以下代码：  
  
      const express = require('express')     //获取数据
      const app = express() 
      const router = express.Router()
      const testListData = require('../mock/testList.json') 
      app.use('/api', router)  
      
      devServer: {               //该方法已存在！
      before(app) {              //设置接口，需添加的代码
      app.get('/api/testList', (req, res, next) => {
        res.json(testListData)
       })
      },
      
      通过http://localhost:8080/api/testList 即可访问
