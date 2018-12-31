一、Spring Boot 推荐目录结构  

（1）代码层的结构  

　　根目录：com.springboot  

　　　　1.工程启动类(ApplicationServer.java)置于com.springboot.build包下  

　　　　2.实体类(domain)置于com.springboot.domain  

　　　　3.数据访问层(Dao)置于com.springboot.repository  

　　　　4.数据服务层(Service)置于com,springboot.service,数据服务的实现类(serviceImpl)置于com.springboot.service.impl  

　　　　5.前端控制器(Controller)置于com.springboot.controller或者com.springboot.web

　　　　6.工具类(utils)置于com.springboot.utils  

　　　　7.常量接口类(constant)置于com.springboot.constant  

　　　　8.配置信息类(config)置于com.springboot.config  

　　　　9.数据传输类(vo)置于com.springboot.vo  

（2）资源文件的结构  

　　根目录:src/main/resources  

　　　　1.配置文件(.properties/.json等)置于config文件夹下  
         两种配置文件选其一使用application.properties和application.yml：一种基于Unicode容易阅读，容易和脚本语言交互的，
         用来表达资料序列的编程语言。

　　　　2.国际化(i18n))置于i18n文件夹下  

　　　　3.spring.xml置于META-INF/spring文件夹下  

　　　　4.页面以及js/css/image等置于static文件夹下的各自文件下  
