第一步：打开Eclipse 菜单栏 Help -> Install New Software …   
例如我的 Eclipse Neon.2 Release (4.6.2) ，首先浏览器打开 http://download.springsource.com/release/TOOLS/update/3.8.3.RELEASE/e4.6/springsource-tool-suite-3.8.3.RELEASE-e4.6.2-updatesite.zip   下载了对应版本的zip包

第二步：contact all update..不需要勾选
勾选Spring IDE的四个选项  
一直点next  

eclipse 离线安装插件报cannot perform operation.Computing alternate solutions...解决办法   
eclipse长时间停留在下图所示状态，提示“cannot perform operation.Computing alternate solutions,may take a while: ...”。  
在网上查找了资料，问题可能是eclipse一直在尝试从自己的更新源下载插件，却因为局域网环境，连接不上导致。
点击 available software sites 只勾选本地插件地址  

温馨提示：若之前安装过sts未成功的，建议重装eclipse再安装sts

