# CSS笔记 by zeo

## CSS

### CSS概述

    Css(Cascading Style Sheets)是用来样式化和排版网页的

### 选择器

#### 选择起器类别

* 简单选择器
  通过元素类型、class 或 id 匹配一个或多个元素。
* 属性选择器
  通过 属性 / 属性值 匹配一个或多个元素
* 伪类
  匹配处于确定状态的一个或多个元素，比如被鼠标指针悬停的元素，或当前被选中或未选中的复选框，或元素是DOM树中一父节点的第一个子节点。
* 伪元素
  匹配处于相关的确定位置的一个或多个元素，例如每个段落的第一个字，或者某个元素之前生成的内容
* 组合器
  这里不仅仅是选择器本身，还有以有效的方式组合两个或更多的选择器用于非常特定的选择的方法。例如，你可以只选择divs的直系子节点的段落，或者直接跟在headings后面的段落。
* 多重选择器
  这些也不是单独的选择器；这个思路是将以逗号分隔开的多个选择器放在一个CSS规则下面， 以将一组声明应用于由这些选择器选择的所有元素。

#### 属性选择器

```css
[attr]该选择器选择包含 attr 属性的所有元素，不论 attr 的值为何。
[attr=val]该选择器仅选择 attr 属性被赋值为 val 的所有元素。
[attr~=val]该选择器仅选择具有 attr 属性的元素，而且要求 val 值是 attr 值包含的被空格分隔的取值列表里中的一个。
```

#### 子串值选择器

```css
[attr|=val]值是val或者以val-开头
[attr^=val]以val开头
[attr$=val]以val结尾
[attr*=val]包含val的元素
```

#### 伪类和伪元素

名称|组合器|选择
---|:--:|---:
选择器组|A，B|满足A或B的任何元素
后代选择器|A B|匹配B元素，B是A的子元素
子选择器|A >B|匹配B元素，B是A的直接子节点
相邻兄弟选择器|A+B|匹配B元素，B是A的下一个兄弟节点
通用兄弟选择器|A～B|匹配B元素，B是A的兄弟节点的任意一个

### 数值与单位

### 串联与继承

1. 重要性(Importance)
   通过```!important```
2. 专用性(Specificity)
    1. 千位：如果声明是在style 属性中该列加1分（这样的声明没有选择器，所以它们的专用性总是1000。）否则为0。
    2. 百位：在整个选择器中每包含一个ID选择器就在该列中加1分。
    3. 十位：在整个选择器中每包含一个类选择器、属性选择器、或者伪类就在该列中加1分。
    4. 个位：在整个选择器中每包含一个元素选择器或伪元素就在该列中加1分。

3. 源代码次序(Source order)

### 区块模型

![框模型](https://mdn.mozillademos.org/files/13647/box-model-standard-small.png)

## 样式化文字

### 链接

链接样式修改要保持**L**o**V**e **F**ears **HA**te

1. link
2. visited
3. focus
4. hover
5. active

## 样式化区块

### box model 回顾与补充

#### margin塌陷

两个box在一起时，margin为两个中的最大值

#### 宽和高的约束

```max-width``` 的另一个用法是将媒体限制在容器内部


```css

display:block;
margin:0 auto;
max-width:100%

```

#### 完全改变盒模型

使用box-sizing调整盒模型（border-box）

### 背景

元素背景是指，在元素内容、内边距和边界下层的区域。

#### 背景的基本内容

1. color
2. image
3. position
4. repeat

#### 颜色渐变

linear-gradient(方向,开始颜色,结束颜色)

## css排版

### 浮动

建议使用百分比宽度

#### 清除浮动

```css
    clear:both
```

### 定位



#### 静态定位

每个元素的默认值，意味着元素处于正常位置

#### 相对定位

相对于元素本来的位置作出变换```top bottom left right```

#### 绝对定位

相对于父级元素定位

#### z-index

决定元素重叠时的显示顺序

#### 固定定位

相对于html

```css
    position:fixed
```

### 弹性布局

```css
    display:flex
```

#### 弹性布局模型

![弹性布局模型](https://developer.mozilla.org/files/3739/flex_terms.png)



1. **主轴**是沿着 flex 元素放置的方向延伸的轴（比如页面上的横向的行、纵向的列）。该轴的开始和结束被称为 main start 和 main end
2. **交叉轴**是垂直于 flex 元素放置方向的轴。该轴的开始和结束被称为 cross start 和 cross end。
3. 设置了 ```display: flex ```的父元素（在本例中是 ```<section>```）被称之为 flex 容器（flex container）


```flex-direction```选择列或者行
```flex-wrap```换行

##### 水平和垂直对齐

```algin-items```控制item在交叉轴的位置 ```justify-content```控制flex在主轴的位置