## flex布局使用小结
1、flex布局的使用
```css
.box{
  display: flex;
}
```
```css
.box{
  display: inline-flex;
}
```

2、 容器的属性(6个)
1. flex-direction属性决定主轴的方向（即项目的排列方向）。
flex-direction: row | row-reverse | column | column-reverse;
2. flex-wrap属性定义，如果一条轴线排不下，如何换行。
flex-wrap: nowrap | wrap | wrap-reverse;
3. flex-flow属性是flex-direction属性和flex-wrap属性的简写形式，默认值为row nowrap。
flex-flow: <flex-direction> || <flex-wrap>;
4. justify-content属性定义了项目在主轴上的对齐方式。
justify-content: flex-start | flex-end | center | space-between | space-around;
5. align-items属性定义项目在交叉轴上如何对齐
align-items: flex-start | flex-end | center | baseline | stretch;
6. align-content属性定义了多根轴线的对齐方式
align-content: flex-start | flex-end | center | space-between | space-around | stretch;

3、项目的属性(6个)
1. order属性定义项目的排列顺序。数值越小，排列越靠前，默认为0。
order: <integer>;
2. flex-grow属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
flex-grow: <number>; /* default 0 */
3. flex-shrink属性定义了项目的缩小比例，默认为1，即如果空间不足，该项目将缩小。
flex-shrink: <number>; /* default 1 */
4. flex-basis属性定义了在分配多余空间之前，项目占据的主轴空间（main size）
flex-basis: <length> | auto; /* default auto */
5. flex属性是flex-grow, flex-shrink 和 flex-basis的简写，默认值为0 1 auto
flex: none | [ <'flex-grow'> <'flex-shrink'>? || <'flex-basis'> ]
6. align-self属性允许单个项目有与其他项目不一样的对齐方式
align-self: auto | flex-start | flex-end | center | baseline | stretch;