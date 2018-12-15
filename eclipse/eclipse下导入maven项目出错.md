Maven 工程错误  
Failure to transfer org.codehaus.plexus:plexus-io:pom:1.0,Failure to transfer org.codehaus.plexus:plexus-archiver:jar:2.0.1  

1.先去掉Maven工程的maven特性，选中工程 鼠标右键-->Maven-->Disable Maven Nature. 此步骤后pom.xml错误消失  

2.为工程增加Maven特性,选中工程 鼠标右键-->Configure-->Convert to Maven Project.  

经过上述步骤，Maven工程就正常了。  
  
还一种情况错误就是maven中要求更高的JDK版本，可在pom.xml中添加一下代码  
  
<build>  
  <plugins>
       <plugin>
             <groupId>org.apache.maven.plugins</groupId>
             <artifactId>maven-compiler-plugin</artifactId>
             <version>3.1</version> 
             <configuration>
                 <source>1.7</source>     //如果是1.8，修改为1.8
                 <target>1.7</target>      //如果是1.8，修改为1.8
            </configuration>
       </plugin>
  </plugins>
</build>
 
