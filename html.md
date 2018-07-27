# HTML的一些问题
## display: none;、visibility: hidden、opacity=0区别总结
display: none;
1、浏览器不会生成属性为display: none;的元素。 
2、display: none;不占据空间（毕竟都不渲染啦），所以动态改变此属性时会引起重排。 
3、display: none;不会被子类继承，但是···子类是不会显示的，毕竟都一起被kill啦。 
4、display,是个尴尬的属性，transition对她无效。(毫无争议)
visibility: hidden;
1、元素会被隐藏，但是不会消失，依然占据空间。 
2、visibility: hidden会被子类继承，子类也可以通过显示的设置visibility: visible;来反隐藏。 
3、visibility: hidden;不会触发该元素已经绑定的事件。 
4、visibility: hidden;动态修改此属性会引起重绘。 
5、visibility,transition对她无效。(亲测)
opacity=0
1、opacity=0只是透明度为100%,元素隐藏，依然占据空间。 
2、opacity=0会被子元素继承,且，子元素并不能通过opacity=1，进行反隐藏。不能。 
3、opacity=0的元素依然能触发已经绑定的事件。 
4、opacity,transition对她有效(毫无争议)

## 行内元素和块状元素的区别
行内元素：会在水平方向排列，不能包含块级元素，设置width无效，height无效（可以设置line-height），margin上下无效，padding上下无效
块级元素：各占据一行，垂直方向排列。从新行开始结束接着一个断行

## 使用link和@import有什么区别？
1.link属于HTML标签，除了加载CSS外，还能用于定义RSS，定义rel连接属性等作用；而@import是CSS提供，只能加载CSS;
2.页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载；
3.import是CSS2.1提出的，只在IE5以上才能被识别，而link是HTML标签，无兼容问题；

## 写出几种IE6 BUG的解决方法
1、双边距BUG float引起的 使用display
2、3像素问题使用float引用的使用display:inline -3px;
3、超链接hover后点击失效，使用正确的书写顺序 link visited hover active
4、le z-index问题给父级添加position:relative
5、png 透明使用js代码改， 使用滤镜解决IE6的PNG透明问题
/*以下为IE6设置PNG透明代码*/
_background:none;
_filter:progid:DXImageTransform.Microsoft.AlphaImageLoader(src="images/W3CfunsLogo.png");
6、min-height最小高度 ！important解决
7、select 在ie6下遮盖 使用iframe嵌套
8、为什么没有办法定义1px左右的宽度器（IE6默认的行高造成的，使用over:hidden,zoom:0.08,line-height:1px）

## CSS3新属性
第 1 选择器
第 2 RGBA和透明度
第 3 多栏布局
第 4 多背景图
第 5 Word Wrap
第 6 文字阴影
第 7 @font-face属性
第 8 圆角(边框半径)
第 9 边框图片
第 10 盒阴影
第 11 盒子大小
第 12 媒体查询
第 13 语音

## 布局方式
* position：absolute；时，当left，right和width同时存在时，是width起作用；
* 如何让这两种相互帮助起作用那，就是当让图片margin：auto；时。此时和可以让图片真正的居中，但此方法只适用于IE7+；