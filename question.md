## 没弄明白的问题
```javascript
for (var i = 0; i < 10; i++) {
	setTimeout(function() {
		console.log(i);
	});
}
// 打印出10个10
```
```javascript
for (let i = 0; i < 10; i++) {
	setTimeout(function() {
		console.log(i);
	});
}
// 打印出0-9
```


```javascript
function fun(n,o) {
  console.log(o)
  return {
    fun:function(m){
      return fun(m,n);
    }
  };
}
var a = fun(0);  a.fun(1);  a.fun(2);  a.fun(3);//undefined,0,0,0
var b = fun(0).fun(1).fun(2).fun(3);//undefined,0,1,2
var c = fun(0).fun(1);  c.fun(2);  c.fun(3);//undefined,0,1,1
```