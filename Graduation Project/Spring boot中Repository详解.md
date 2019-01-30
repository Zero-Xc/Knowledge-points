### 不使用mybatis，使用jpa
#### 为什么Repository只有接口，没有实现
- 打开一个Repository接口，发现继承了CrudRepository、JpaSpecificationExecutor接口，CrudRepository中定义了基本  
crud的方法，spring-data-jpa提供了CrudRepository、JpaSpecificationExecutor接口的默认实现，  
实现类为SimpleJpaRepository，package:org.springframework.data.jpa.repository.support。
#### 接下来发现save等一些方法的确是有接口对应，但自定义的方法没有实现类为什么也能运行呢？
- 定义查询方法
存储库代理有两种方法从方法名派生特定于存储区的查询。它可以直接从方法名派生查询，或者使用手动定义的查询。  
可用选项取决于实际存储。但是，必须有一种策略来决定创建什么样的实际查询。让我们来看看可用的选项。   
- 直接从方法名派生查询  
拿上面的作为例子：  
TestEntity findByUserName(String userName);  
该机制将前缀分隔为find…By, read…By, query…By, count…By,get…By去掉然后开始解析其余部分。  
findByUserName去掉前缀则为UserName,该机制开始按照驼峰的命名方式从右往左开始解析，解析为User,Name，Name,  
解析完成后发现name并不是TestEntity中的属性，于是继续解析为UserName，而userName为TestEntity中的属性，  
所以生成了from TestEntity where userName=?的query语句。  
如果解析到最后也没匹配，则会抛出异常在程序启动的时候。  

### 使用mybatis则需要mapper和mapper.xml


