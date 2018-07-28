## 几种常见的设计模式
1、单例模式
```javascript
var single = (function(){
    var unique;

    function getInstance(){
　　　　// 如果该实例存在，则直接返回，否则就对其实例化
        if( unique === undefined ){
            unique = new Construct();
        }
        return unique;
    }

    function Construct(){
        // ... 生成单例的构造函数的代码
    }

    return {
        getInstance : getInstance
    }
})();
```

2、构造函数模式
```javascript
/**
 * 构造一个动物的函数 
 */
function Animal(name, color){
    this.name = name;
    this.color = color;
    this.getName = function(){
        return this.name;
    }
}
// 实例一个对象
var cat = new Animal('猫', '白色');
console.log( cat.getName() );
```

3、工厂模式
```javascript
function Animal(opts){
    var obj = new Object();
    obj.name = opts.name;
    obj.color = opts.color;
    obj.getInfo = function(){
        return '名称：'+obj.name +'， 颜色：'+ obj.color;
    }
    return obj;
}
var cat = Animal({name: '波斯猫', color: '白色'});
cat.getInfo();
```

4、模块模式
```javascript
/**
 * 模块模式 = 封装大部分代码，只暴露必需接口
 */
var Car = (function(){
    var name = '法拉利';
    function sayName(){
        console.log( name );
    }
    function getColor(name){
        console.log( name );
    }
    return {
        name: sayName,
        color: getColor
    }
})();
Car.name();
Car.color('红色');
```

5、发布订阅模式
