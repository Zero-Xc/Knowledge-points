Maven 工程错误  
Failure to transfer org.codehaus.plexus:plexus-io:pom:1.0,Failure to transfer org.codehaus.plexus:plexus-archiver:jar:2.0.1  

1.先去掉Maven工程的maven特性，选中工程 鼠标右键-->Maven-->Disable Maven Nature. 此步骤后pom.xml错误消失  

2.为工程增加Maven特性,选中工程 鼠标右键-->Configure-->Convert to Maven Project.  

经过上述步骤，Maven工程就正常了。
