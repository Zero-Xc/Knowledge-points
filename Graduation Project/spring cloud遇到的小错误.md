### 注解无法使用
- 检查pom.xml有无错误，若有错误，检查相应jar包名是否正确；若无错误，检查jar包是否正常引入，需删除错误jar包文件，再更新jar包

### @FeignClient无法注入
- @SpringBootApplicatoin是用的@ComponentScan扫描，扫描的是Component，包括@Component, @Controller, @Service, @Repository等，
而@EnableFeignClients扫描的是@FeignClient，所以在指定扫描路径时要分别指定，否则会报异常！找不到对应的bean
