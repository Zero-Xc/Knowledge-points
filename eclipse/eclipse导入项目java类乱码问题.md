  编码格式主要使用的是UTF-8编码是用以解决国际上字符的一种多字节编码，它对英文使用8位（即一个字节），中文使用24位（三个字节）来编码。
  
  BK即国标是专门用来解决中文编码的，是双字节的。不论中英文都是双字节的。
 
  首先需要确定导入的项目是什么编码，需要根据项目编码改变eclipse的编码方式。项目是UTF-8就改成UTF-8。

  若不确定项目编码，则在项目右键进入properties，Resource-Text file encoding改为UTF-8或者GBK，接着修改eclipse的编码，  
windows-preference-General-Content Types-Text-Java source File 改为UTF-8或者GBK，再接着windows-preference-General-Workspace-
Text file encoding改为UTF-8或者GBK。至此，乱码解决
