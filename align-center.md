1、table-cell的方式
```css
#wrapper {
    display: table;
}

#cell {
    display: table-cell;
    vertical-align: middle;
    text-align: center;
}
```

2、position: absolute、top:50%、margin-top: -height的方式
```css
#content {
    position: absolute;
    top: 50%;
    height: 240px;
    margin-top: -120px; /* negative half of the height */
}
```

3、 position: absolute、top: 0、bottom: 0、margin: auto固定宽度的方式
```css
#content {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
    height: 240px;
    width: 70%;
}
```
4、height和line-height相等的方式，使文本居中
```css
#content {
    height: 100px;
    line-height: 100px;
}
```

5、position: absolute、top: 50%、transform: translate(0, -50%)，可针对不定大小
```css
#box {
    width: 300px;
    height: 300px;
    background: #ddd;
    position: relative;
}
#child {
    background: #93BC49;
    position: absolute;
    top: 50%;
    transform: translate(0, -50%);
}
```

6、flex布局，最简单的方式，flex有兼容性
```css
#box {
    display: flex;
    align-items: center;
    justify-content: center;
}
```