## 捕获、触发、冒泡

## 阻止事件冒泡
* event.stopPropagation()不能简单说阻止了事件的冒泡，其实也阻止了事件的继续捕获，确切的说应该是阻止事件的进一步传播
* event.stopPropagation()阻止不了该元素上的其他事件的执行，使用event.stopImmediatePropagation()可以阻止

## 事件委托
* 子元素的事件处理程序写到父元素的事件处理程序中，这就是事件委托