## 前端怎么实现跨域？
1、通过jsonp跨域


2、通过修改document.domain+iframe来跨子域


3、使用window.name+iframe来进行跨域


4、使用HTML5中新引进的window.postMessage方法来跨域传送数据


5、CORS需要浏览器和服务器同时支持，header("Access-Control-Allow-Origin:*");


6、使用代理跨域


7、动态创建script


8、location.hash+iframe