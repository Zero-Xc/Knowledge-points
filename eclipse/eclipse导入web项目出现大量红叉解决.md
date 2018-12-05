  点击eclipse菜单栏window（窗口）-preferences（偏好,优先权）-java-installed JREs。接着可以add本地的一些jre运行环境。

  接着点击java-compiler（编译），修改编译器版本与导入的本地jdk版本一致，至此eclipse的jdk版本修改完毕。

  接下来修改导入的web项目的jdk版本，右键项目，点击properties（属性），java-compiler与project facets的版本都改至1.8版本。

  接下来右键项目，点击build path(建立路径)-configure build path，在libraries（文库）里add-library,添加本地默认的jre环境，
如果项目自带了一部分所需jar包，接下来最重要的一步就是点击order and export,将上一步导入的本地jre一直up到第二的位置（处于一个文件下方）。
就不会报类似The type XXX is not generic; it cannot be parameterized with arguments <String, Integer>的错误。原因是项目自带的
jar包可能包含了jdk5.0以下的jar包，不选择顺序的话本地jre在最下方就无法优先执行。
