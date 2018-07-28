## 如何实现多列等高布局
1、万能的flex
```
.container {
  display: flex;
  align-items: stretch;
}
```

2、使用table或者伪table
```css
.container {
  display: table;
}
.item {
  display: table-cell;
}
```

3、使用绝对定位
```css
.container {
  position: relative;
}
.left, .center, .right {
  position: absolute;
}
.left {
  top: 0;
  left: 0;
  bottom: 0;
  width: 200px;
}
.right {
  top: 0;
  right: 0;
  bottom: 0;
  width: 200px;
}
.center {
  top: 0;
  right: 200px;
  bottom: 0;
  left: 200px;
}
```

4、使用margin-bottom和padding-bottom大小相反的方式
```css
.container {
  overflow: hidden;
}
.item {
  float:left;
  margin-bottom: 100px;
  padding-bottom: -100px;
}
```