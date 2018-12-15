出错信息如下  
  Description Resource Path Location Type  
  Dynamic Web Module 3.1 requires Java 1.7 or newer. bdp line 1 Maven Java EE Configuration Problem  

  Description Resource Path Location Type  
  One or more constraints have not been satisfied. bdp line 1 Maven Java EE Configuration Problem  


    <build>
      <plugins>
           <plugin>
                 <groupId>org.apache.maven.plugins</groupId>
                 <artifactId>maven-compiler-plugin</artifactId>
                 <version>3.1</version>
                 <configuration>
                     <source>1.8</source>    
                     <target>1.8</target>     
                 </configuration>
           </plugin>
      </plugins>
    </build>
