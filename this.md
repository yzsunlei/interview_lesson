# this的指向问题
* this的指向在函数定义的时候是确定不了的，只有函数执行的时候才能确定this到底指向谁，实际上this的最终指向的是那个调用它的对象

* 这个函数中包含多个对象，尽管这个函数是被最外层的对象所调用，this指向的也只是它上一级的对象

* 如果返回值是一个对象，那么this指向的就是那个返回的对象，如果返回值不是一个对象那么this还是指向函数的实例。
function fn()  
{  
    this.user = '追梦子';  
    return function(){};
}
var a = new fn;  
console.log(a.user); //undefined

function fn()  
{  
    this.user = '追梦子';  
    return undefined;
}
var a = new fn;  
console.log(a); //fn {user: "追梦子"}

* js中typeof的返回值类型有Number、String、Null、Undefined、Object、Function

* 对于所有的对象，都有__proto__属性，这个属性对应该对象的原型.
对于函数对象，除了__proto__属性之外，还有prototype属性。
当一个函数被用作构造函数来创建实例时，该函数的prototype属性值将被作为原型赋值给所有对象实例（也就是设置实例的__proto__属性）
所有的原型对象都有constructor属性，该属性对应创建所有指向该原型的实例的构造函数.
函数对象和原型对象通过prototype和constructor属性进行相互关联