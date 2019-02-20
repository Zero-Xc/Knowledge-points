## 整合步骤
- 首先在POM中添加相应jar包

```
    <dependency> 
        <groupId>org.mybatis.spring.boot</groupId> 
        <artifactId>mybatis-spring-boot-starter</artifactId>
        <version>1.2.0</version>
    </dependency>

    <dependency>
          <groupId>mysql</groupId>
          <artifactId>mysql-connector-java</artifactId>
          <scope>runtime</scope>
    </dependency>

```
- 创建相应的entity和mapper（重点为mapper）
```
  public interface TestMapper {
	@Select("SELECT * FROM activity")
	List<TestEntity> getNewsAll();
  }
```

- 启动类中扫描mapper，跟扫描component类似
```
  @MapperScan("com.mybatis.mapper")
```

- 在application.properties中添加
```
  mybatis.type-aliases-package=com.mybatis.entity
  spring.datasource.driverClassName = com.mysql.jdbc.Driver
  #?serverTimezone=GMT%2B8 表示市区+8
  spring.datasource.url = jdbc:mysql://localhost:3306/stusys?serverTimezone=GMT%2B8
  spring.datasource.username = root
  spring.datasource.password = 199704
  #确定日期格式与时区
  spring.jackson.date-format=yyyy-MM-dd 
  spring.jackson.time-zone=GMT+8 
```
