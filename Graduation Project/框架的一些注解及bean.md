### domain包下：  
- @Id 标注用于声明一个实体类的属性映射为数据库的主键列。   
该属性通常置于属性声明语句之前，可与声明语句同行，也可写在单独行上,@Id标注也可置于属性的getter方法之前。  
- @GeneratedValue 用于标注主键的生成策略，通过strategy 属性指定。默认情况下，  
自动选择一个最适合底层数据库的主键生成策略：SqlServer对应identity，MySQL 对应 auto increment。  
- @Column注解来标识实体类中属性与数据表中字段的对应关系。有十个属性，其中常用的一些：  
nullable属性表示该字段是否可以为null值，默认为true。  
- @Transient的作用是指定该属性或字段不是永久的。它用于注释实体类，映射超类或可嵌入类的属性或字段。  
### repository包下：
- @Transactional 可以作用于接口、接口方法、类以及类方法上。当作用于类上时，该类的所有 public  
方法将都具有该类型的事务属性，同时，我们也可以在方法级别使用该标注来覆盖类级别的定义。  
- @query()查询  
### controller包下：
- @ComponentScan(basePackages={"com.xx.xx"}) 该注解表示需要扫描的组件，必须。
- @RestController 注解相当于@ResponseBody ＋ @Controller合在一起的作用。  
如果只是使用@RestController注解Controller，则Controller中的方法无法返回jsp页面，  
或者html，配置的视图解析器InternalResourceViewResolver不起作用，返回的内容就是Return 里的内容。
- @component 用于注解一个控制器，和@service,@controller效果都一样
- @bean 出现与@component之后，用于引用第三方组件？
- @GetMapping是一个组合注解，是@RequestMapping(method = RequestMethod.GET)的缩写。该注解将HTTP Get 映射到 特定的处理方法上。
同理@PostMapping、@PutMapping、@DeleteMapping、@PatchMapping类推
- @RequestMapping 在Spring MVC 中使用 这个注解来映射请求，也就是通过它来指定控制器可以处理哪些URL请求
- @RequestParam主要用于将请求参数区域的数据映射到控制层方法的参数上，主要参数：value、required、defaultValue
- @PathVariable 可以将@RequestMapping注解中用{}表示的变量部分的值截取下来（即去除反斜杠）
- @Autowired 该注解可以对类成员变量、方法及构造函数进行标注，完成自动装配的工作。按照类型（byType）装配依赖对象
- @Resource 可以对类成员变量、方法及构造函数进行标注，完成自动装配的工作,默认按照ByName自动注入,找不到name才按类型装配
### domain.result包下：
- ExceptionMsg 类，全名Exception Message（异常消息），用枚举类定义一个状态码用作异常处理。
