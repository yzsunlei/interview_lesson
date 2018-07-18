# Vue相关面试题

## MVVM框架是什么
* 一个model+view+vidwModel框架，数据模型model、viewModel连接两个，vue数据驱动，通过数据来显示视图层而不是节点操作

## 双向绑定原理是什么
* 采用的数据劫持结合发布者-订阅者模式的方式，通过Object.defineProperty()来劫持各个对象的setter、getter，在数据变动时发布消息给订阅者，触发相应的监听回调
* 1、需要observe的数据对象进行递归遍历，包括子属性对象的属性，都加上getter和setter。这样的话给这个对象的某个值赋值就会触发setter，那么就能监听到数据变化
* 2、compile解析模板指令，将模板中的变量替换成数据，然后初始化渲染页面视图，并将每一个指令对应的节点绑定更新函数，添加监听数据的订阅者，一旦数据有变动，收到通知，更新视图
* 3、watcher订阅者是observer和compile之间通信的桥梁，主要做的是：在自身实例化时往属性订阅器dep里面添加自己，自身必须有一个update方法，待属性变动dep.notice通知时，能调用自身的update方法，并触发compile中绑定的回调
* 4、MVVM作为数据绑定的入口，整合Observer、Compile和Watcher三者，通过Observer来监听自己的model数据变化，通过Compile来解析编译模板指令，最终利用watcher搭起Observer和Compile之间的通信桥梁，达到数据变化、视图更新、视图交互变化、数据model变更的双向绑定效果

## 生命周期8个阶段的理解
* 创建前/后： 在beforeCreated阶段，vue实例的挂载元素$el和数据对象data都为undefined，还未初始化。在created阶段，vue实例的数据对象data有了，$el还没有。
* 载入前/后：在beforeMount阶段，vue实例的$el和data都初始化了，但还是挂载之前为虚拟的dom节点，data.message还未替换。在mounted阶段，vue实例挂载完成，data.message成功渲染。
* 更新前/后：当data变化时，会触发beforeUpdate和updated方法。
* 销毁前/后：在执行destroy方法后，对data的改变不会再触发周期函数，说明此时vue实例已经解除了事件监听以及和dom的绑定，但是dom结构依然存在

## 你是怎么认识vuex的
* vuex可以理解为一种开发模式或框架。通过状态(数据源)集中管理驱动组件的变化
* 应用级的状态集中放在store中，改变状态的方式是提交mutations，异步逻辑封装在action中

## template编译的理解
* 先转化成AST树，再得到的render函数返回VNode
* 通过compile编译器把template编译成AST语法树(源代码的抽象语法结构的树状表现形式)，compile是createCompiler的返回值，createCompiler是用以创建编译器的。
  然后，AST会经过generate(将AST语法树转化成render function字符串的过程)得到render函数，render的返回值是VNode，VNode是Vue的虚拟DOM节点，里面有(标签名、子节点、文本等)

## 组件之间的传值通信
* 父组件通过标签上面定义传值
* 子组件通过$emit方法传递参数

## methods 计算属性 watch的区别
* 计算属性是基于他们的依赖进行缓存的
* 重新计算开销很大的话请选计算属性，不希望有缓存的请选methods

## vue如何实现按需加载配合webpack设置
* webpack中提供了require.ensure()来实现按需加载。以前引入路由是通过import 这样的方式引入，改为const定义的方式进行引入。
* 不进行页面按需加载引入方式：import  home   from '../../common/home.vue'
* 进行页面按需加载的引入方式：const  home = r => require.ensure( [], () => r (require('../../common/home.vue')))












