1.getAttribute是取得jsp中 用setAttribute設定的attribute 

2.getParameter得到的是string；getAttribute得到的是object 

3.request.getParameter()方法传递的数据，会从Web客户端传到Web服务器端，代表HTTP请求数据；
request.setAttribute()和getAttribute()方法传递的数据只会存在于Web容器内部，在具有转发关系的Web组件之间共享。
即request.getAttribute()方法返回request范围内存在的对象，而request.getParameter()方法是获取http提交过来的数据。
