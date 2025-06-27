# HTML-CSS

## HTML的基本语法

### 标签

也可以叫做元素

```html
<h1></h1>
<body></body>
```



#### 自结束标签

<标签名>   

<标签名/> -->严格语法

```html
<input>
<br>
```

#### 常用标签

元素（element）之间的关系：

父元素

​	-**直接**包含子元素的元素就是父元素

子元素

​	-**直接**被父元素包含的元素就是子元素

祖先元素 - 后代元素

​	-**直接或间接** 

兄弟元素

​	-拥有相同的父元素的元素是兄弟元素



##### title

```html
<title>常用标签</title>
```

1、表示标题标签，文字会显示到标签页上

2、这部分主要是SEO相关知识（搜索引擎优化）

3、搜索引擎在抓取页面的时候，会通过title的内容来识别网页的主要内容



##### 标题标签

1、最大的是<h1></h1>    最小的是<h6></h6>

2、重要的是语义（比如通过h1标签内容来判断页面的主要内容），而不是字体大小，字体大小后续可以使用css修改



##### p

段落

##### br

换行

##### hr

水平分割线

##### b

加粗

##### 转义字符

可以通过实体在网页中来表示一些特殊的符号

语法：&实体的名字

```html
//小于号
&lt;
//大于号
&gt;
//空格
&nbsp;
//不会换行，会从页面溢出

//&copy;
```

##### 列表

有序列表

	-	使用ol来创建有序列表
	-	在ol中使用li来表示列表项目

```html
<ol>
    <li>芹菜</li>
    <li>青菜</li>
    <li>胡萝卜</li>
</ol>
```

无序列表

	- 使用ul来创建无序列表
	- 列表之间可以根据需求相互嵌套

定义列表

	- 定义列表用来描述一些内容
	- 使用dl来创建一个定义列表
	- 使用dt来定义被描述的内容
	- 使用dd来对内容进行描述

```html
<dl>
    <dt>大闸蟹</dt>
    <dd>宁波大闸蟹</dd>
    <dd>鲜香可口</dd>
</dl>
    
```



##### 语义化标签

网页除了给人看以外，还需要方便爬虫程序爬取，w3c希望能够帮助程序更好地爬取这个页面，于是添加了许多语义化标签来帮助爬虫程序识别页面

```html
main   //主要内容，一个页面中最好只有一个main标签
header  //头部内容
footer   //底部内容
```

```html
<article></article>
//表述文章中一块独立的内容（商品卡片）
```

```html
<aside></aside>
//和主题独立的内容（侧边栏）（比如广告）
```

```html
<nav></nav>
//导航
```

```html
<section></section>
//独立的区块
```

但是在实际开发中，比较常见的是使用div代替所有标签



##### pre

预格式：保留文本原本的格式

##### code

无论什么奇怪的符号在这个标签里都可以显现

##### img

- 图片标签，用来在页面中引入图片

- 是自结束标签
- 图片的格式
	- jpg：用来显示照片，不支持透明的效果
	- gif：用来显示颜色单一的图片或动图，支持简单透明
	- png：用来显示颜色丰富的图片，支持透明（网页中使用较多）
	- webp：是谷歌浏览器专门推出的一种格式，兼容上述三种格式的有点，是完美格式
	- base64：图片转化成编码（通过base64编码后，图片可以和网页一起加载，加快图片的加载速度）

选择图片的原则：

1、图片大小一致，用显示效果好的

2、显示效果一样，用图片小的

- 属性
	- src：表示要引入图片的路径
		- 相对路径：用来引入自己项目内的图片。需要使用./开头（可以省略）或 ../（当前目录的上一级目录）开头（.表示自己所在目录，几个.就表示上几级）
		- 绝对路径：通常用来引入外部图片，从头开始写
	- alt：是对图片的描述（不写，则搜素引擎不会对图片进行收录）
	- height / width  (这俩属性，只修改一个值，另一个会等比例缩放，开发中建议只改一个)

```html
<img src="1.gif" alt="大松树">
```



##### 超链接

**外部跳转**

**a** 

	- 使用a标签来定义一个超链接
	- 通过超链接可以跳转到其他页面
 - 属性
	- href：指定跳转的位置：需要一个路径作为参数（可以是绝对路径，也可以是相对路径）
	- target：用来指定页面打开的位置
		- blank：在一个新的标签页打开链接
		- self（默认值）：在当前页面打开

**内部跳转**

```html
// # 表示跳转到页面的顶部
<a href="#">回到顶部</a>

//#id 表示调到某个特定的位置
<a href="#p1">去到第一自然段</a>

```



##### 内联框架

**iframe**

	- 内联框架：用来像一个网页中引入另一个网页
 - 属性：
	- src：指定需要引入的网页的路径
	- 可以指定长宽



### 属性

可以在标签中为元素设置属性

属性用来描述元素，属性是一个名值对结构，属性名="属性值"

一个元素可以同时指定多个属性，多个属性之间可以使用空格分离

有些属性属性名和属性值相同，此时可以省略属性值

```html
<input type="password">
```



### 元素的嵌套规则

####  块元素

特点：

​	1、独占页面的一行，自上向下垂直排列

​	2、块元素用来对网页进行布局，将一个页面分成一块 一块的

​	3、最常用的块元素：div  

#### 行内元素

特点：

​	1、只会占自身大小，自左向右水平排列

​	2、行内元素一般放置文字

​	3、最常用的行内元素：span

**元素的嵌套规则**

- 块元素中可以放置行内元素，也可以放置块元素

- 行内元素中尽量不要放置块元素
- a标签可以防止除了它自身以外的所有标签
- p元素中不能放置块元素





## CSS

层叠样式表

**内联样式（行内样式）：**

 -  可以直接把CSS编写到元素的style属性中

 -  一个网页可以分成三个部分：

	- 结构、表现和行为

	一个设计优良的网站，最好要把结构、表现和行为三者分离，所以不推荐内联样式



**内部样式表**

 -  可以通过style标签来创建一个内部样式

	

**外部样式表 (推荐)**

 - 创建文件style.css 在这个文件里写css样式
 - 然后通过link标签引入外部的样式到页面

```html
<link rel="stylesheet" href="style.css">
```



### CSS的语法

基本语法：

选择器 声明块

选择器：选择器用来指定要设置样式的元素

声明块：用来设置样式，由一段大括号括起来



### 基本选择器

#### 元素选择器

- 根据标签名选中多个元素
- 例子：p{}  div{}  h1{}

##### id属性

- 根据元素的id属性选中一个元素
- **语法：#id {}**
- 例子：#p1{}  #box{}  #head{}

##### 类选择器

- 根据元素的class属性选中元素
- **语法：.class{}**
- 和id不同，可以为多个元素指定同样的class属性，也可以为一个元素同时设置多个class属性

##### 通配选择器

- *{} 选中页面的所有元素



#### 属性选择器

根据元素的属性选中元素

- 语法：
	- [属性名]{}   
	- [属性名=属性值]{}     选中指定属性值的元素
	- [属性名=^属性值]{}   选中属性值以指定内容开头的元素   
	- [属性名=$属性值]{}   选中属性值以指定内容结尾的元素
	- [属性名*=属性值]{}   选中属性值包含指定内容的元素
- 选中具有该属性的元素

```html
<style>
    [title]{
        color:orange;
    }
</style>
<body>
    <h1 title="hello">
        落霞与孤鹜齐飞
    </h1>
    <p title="abc">
        秋水共长天一色
    </p>
    <div>
        一天三顿烧烤
    </div>
</body>
```

##### 交集选择器

可以将多个选择器连着一起写**（不空格）**，这样则要求元素满足多个选择器

```css
div.box1{
    
}
//选中class为box1的div
```



#### 分组和关系选择器

##### 分组选择器

- 作用：同时选中多个选择器对应的元素
- 语法：选择器1，选择器2，选择器3...选择器n{}

```css
#p1,.p2,div{
    
}
//等价于
#p1{}
.p2{}
div{}
```



##### 关系选择器

- 根据元素之间的关系来选中元素
- 元素之间的关系
	- 父子、祖先后代、兄弟
- 子元素选择器
	- 作用：选中指定元素的子元素
	- 语法：父元素 > 子元素{}

```css
div > span{
    color:red;
}
```

- 后代元素选择器
	- 作用：选中指定元素的后代元素
	- 语法：祖先 后代{}
	- 范围更广
- 兄弟元素选择器
	- 作用：选中指定的兄弟元素
	- 语法：
		- 兄 + 弟{}：选中紧随其后的第一个兄弟元素
		- 兄 ~ 弟{}：选中后边所有的兄弟元素



#### 伪类选择器

- 伪类是一个特殊的类，用来表示元素的**状态**

	- 像超链接，一个链接有没有被访问过就是一种特殊的状态

- a的伪类

	- :link

		- 用来表示正常的超链接

	- :visited

		- 用来表示访问过的超链接
		- 它是根据用户的历史记录进行判断
		- 由于隐私的问题，通过visited只能改变文字的颜色

	- :hover

		- 表示鼠标移入的元素

		​	

#### 结构伪类

- :empty
	- 选中空元素

- :nth-child(1)      :nth-child(n+3)从第三个开始
	- 选中第n的子元素
- :nth-last-child()
	- 倒数第n个元素
- :first-child
	- 第一个子元素
- :last-child
- :only-child
	- 唯一的子元素
- :nth-of-type()
	- 同类型中的第n子元素
- :nth-last-of-type()
	- 同类型中的最后一个子元素
- :first-of-type
	- 同类型中的第一个子元素
- :last-of-type
	- 同类型中的最后一个子元素
- :only-of-type
	- 同类型中唯一的子元素



#### 否定伪类

:not ()

- 否定伪类，除了某些元素

```html
<style>
    p:not(.p1){
        color:tomato;
    }
    p:not(:nth-child(3)){
        color:tomato;
    }
</style>
<body>
    <p>
        锄禾日当午
    </p>
    <p>
        汗滴禾下土
    </p>
    <p class="p1">
        谁知盘中餐
    </p>
    <p>
        粒粒皆辛苦
    </p>
</body>
```

 

#### 伪元素

- 伪元素表示的是页面中的特殊位置
- 伪元素使用::开头
	- ::before
		- 元素开始的位置（开始标签之后）
	- ::after
		- 元素结束的位置（结束标签之前）
	- ::first-letter
		- 首字母
	- ::first-line
		- 第一行
- 作用：统一为元素的前面和后面添加内容；且以这种方式添 加的内容不会被网站识别

```html
<style>
    div::before{
        content:"before";
        color:red;
    }
    div::sfter{
        content:"after";
        color:blue;
    }
</style>
```



### 样式的继承

- 设置给祖先元素的样式，也会同时应用到其后代元素上
- 继承的存在，大大简化了样式的编写
- **但并不是所有的样式都会发生继承**
	- 所有**布局、边框、背景相关的样式**都不会发生继承，会导致网页布局变乱



### 选择器的权重

**样式的冲突**

当我们使用不同的选择器，选中同一个元素并设置相同的样式时，就发生了样式的冲突

**当发生样式冲突时，哪个样式生效由选择器的优先级决定**



#### 优先级

内联样式（1，0，0，0） > id选择器（0，1，0，0） > 类和伪类选择器（0，0，1，0） > 元素选择器（0，0，0，1） > 通配选择器（0，0，0，） > 继承的样式



#### **复合样式**

比较优先级时，如果由多个选择器组成，那么要将多个选择器的优先级加起来一起计算

优先级高的优先显示，优先级的累加不会跨越数量级

如果优先级一样，则优先显示靠下的样式



#### !important

如果为样式添加 !important ，则该样式会获得最高样式



#### a伪类的顺序

```css
<style>
a:link{
    color: red;
}

a:visited{
    color: orange;
}

a:hover{
    color: greenyellow;
}

a:active{
    color: deepskyblue;
}
</style>
```

确保这个顺序**（lvha）**(love hate)，才能让这四个样式生效



### 盒子模型

1、网页的布局指的是将元素摆到合适的位置

2、布局得先确定元素的大小，怎么确定大小呢？ --- 盒子模型（矩形）

3、所以在网页中每个元素都是一个矩形，将其想象成一个盒子（有大小，还有内部空间）

- **内容区（content）**：内容区在元素最内部，用来容纳子元素
	- **height和width设定的都是盒子内容区的大小**
- **边框（border）**：是盒子的边界，离开边框就属于盒子的外部了
	- border-width：边框的宽度
	- border-color：边框的颜色
	- border-style：边框的样式（实线、虚线）
- 边框宽度会影响到盒子可见区的大小



#### 边框

border-width 用来指定边框的宽度

- 10px 20px 30px 40px 上 右 下 左    
- 10px 20px 30px 上 左右 下
- 10px 20px 上 下    
- 10px 上 下 左 右

但是也可以写 border-top/left/right/bottom



**边框的样式**

- solid 实线 
- dotted 点状虚线 
- dashed 虚线 
- double 双线



#### 内边距

内容区和边框之间的距离称为内边距 

共有四个方向的内边距： 

- padding-top 上内边距 
- padding-bottom 下内边距 
- padding-left 左内边距 
- padding-right 右内边距

**默认情况下，背景颜色会延伸到内边距上， 所以我们无法直观的看到内边距 **

**内边距也会影响到盒子可见框的大小 **

**一个元素的可见框的大小由： ==内容区、内边距和边框共同决定==**



#### 可见框的计算

盒子的可见框指可见的部分，大小由内容区，内边距和边框共同决定

box-sizing 用来指定盒子可见框的计算方式 

可选值：    

- content-box （默认值）：width和height用来设置内容区的大小    
- border-box ：设置该值后，width和height用来设置盒子可见框的大小

使用border-box后就不需要自己计算内容区啊内边距啊边框啊需要多少，方便



#### 外边距

外边距同样有四个方向 

- margin-top 上外边距，值越大元素越靠下 
- margin-bottom 
- margin-left 左外边距，值越大元素越靠右 
- margin-right 

由于我们的浏览器默认是按照自左向右，自上向下的顺序来排列元素的，  所以**当我们设置==上和左外边距时，是改变元素自身的位置==  但是设置下和右时，会改变其他元素的位置**



##### 外边距折叠

- 垂直方向的**相邻外边距**会发生外边距折叠的现象    
- 父子元素之间子元素外边距会传递给父元素，会导致布局出问题，要避免
	- 
- **兄弟元素间**外边距折叠会取较大值 (300px)

```css
.box1{
    width: 200px;
    height: 200px;
    background-color: orange;
    margin-bottom: 200px;
}

.box2{
    width: 200px;
    height: 200px;
    background-color: deepskyblue;
    margin-top: 300px;
}
```



#### 轮廓

outline是轮廓线

- 和边框特别像，但是outline不会影响到元素可见框的大小
- 经常hover使用



#### 圆角

```css
//左上角圆角的半径
border-top-left-radius:100px
```

- 值越大越圆



#### 阴影

box-shadow：

- 可以用来为元素指定阴影

- 4个参数的含义

	- x轴偏移量
	- y轴偏移量
	- 虚化半径（值越大越模糊）
	- 扩散班级（让阴影往外延伸，值越大越往外扩散）（可以省略）
	- rgba(0,0,0,0.3)  0.3是颜色的透明度   （值越大，越不透明，颜色越浓）

- ```css
	box-shadow:0 0 0 0 rgb(0,0,0)  //要有单位啊
	```

	

### 水平居中

```
nargin=auto;
```

可以将margin的值设置为auto，设置auto后，元素的外边距由浏览器自动计算 

当我们将margin-left或margin-right中的一个设置为auto时，则浏览器会自动使其**尽量的大** 

如果将margin-left和margin-right同时设置为auto，则浏览器会使元素左右的外边距相同， 也就是**元素会在其父元素中水平居中** 

通过将一个块元素的左右外边距设置为auto，以使其在父元素中水平居中 

默认情况下，垂直外边距设置为auto时，浏览器会自动取0为外边距



### 行内元素的盒模型

行内元素的大小无法使用width或者height来设置，只能由内容撑开

行内元素可以设置内边距、边框，外边距，但垂直方向的内边距不会影响布局



### overflow

当子元素大小超过父元素内容区时，子元素会从父元素中溢出

在CSS中通过overflow样式来处理溢出内容

overflow可选值：

- visible：默认值，直接溢出

- hidden：隐藏溢出的内容
- scroll：生成**双方向**滚动条，来查看完整的元素
- auto：根据需要生成滚动条（即不是双方向的）



### display

- 用来设置元素的类型
- 可选值
	- inline：将元素设置为行内元素
	- block：块元素
	- inline-block（少用）：行内块元素：兼具行内元素和块元素的特点，**不独占一行，又可以设置行高**
		- 会像文本一样，有空格，解决方法就是连着不空格
	- ==none==：隐藏元素（不占空间，直接消失）



### visibility

可选值：

- visible：默认值，元素可见
- hedden：元素是蕴藏在页面中不可见，但是依然占据页面的位置



### 文字的居中

水平居中：

- text-align：center

垂直居中：

- line-height=height



### 清楚默认样式

**方式一**

```css
*{
	padding:0;
    margin:0;
}
```

**方式二**

reset.css

前人编写好的，直接拿来用

```css
/* http://meyerweb.com/eric/tools/css/reset/ 
   v2.0 | 20110126
   License: none (public domain)
*/

html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video {
	margin: 0;
	padding: 0;
	border: 0;
	font-size: 100%;
	font: inherit;
	vertical-align: baseline;
}
/* HTML5 display-role reset for older browsers */
article, aside, details, figcaption, figure, 
footer, header, hgroup, menu, nav, section {
	display: block;
}
body {
	line-height: 1;
}
ol, ul {
	list-style: none;
}
blockquote, q {
	quotes: none;
}
blockquote:before, blockquote:after,
q:before, q:after {
	content: '';
	content: none;
}
table {
	border-collapse: collapse;
	border-spacing: 0;
}
```

**方式三**

使用normalize.css

没有清除掉所有样式，而是将其统一



### 文本样式

#### 文本对齐方式

文本的水平对齐方式：

text-align：

-  left：（默认值）左对齐
- center：居中对齐
- right：右对齐
- justify：两端对齐



#### 首行缩进

1em就是一个字的大小

```css
text-indent:2em;
```



#### 文本修饰

text-decoration:

- none
- underline
	- underline wavy red
- overline
- line-through



text-transform:

- uppercase
- lowercase
- capitalize



#### 文本溢出

##### 禁止换行

```css
white-space:nowrap;
```

##### 禁止溢出

```css
overflow:hidden;
```

##### 省略号

```css
text-overflow:ellipsis;
```



#### 行高

line-height 用来设置元素的行高

- 行就是用来放文字的，行高就是文字所在行的高度
- 文字默认在行高中垂直居中
- 行间距=行高-字体大小

##### **水平垂直居中**

```css
div{
    width:100px;
    height:100px;
    text-align:center;
    line-height:100px
}
```

##### 垂直对齐

在网页中，每个文字被显示时都会有一个文本框与之对应 ，当我们设置元素的font-size时，实际上就是在设置文本框的大小

文本框存在一个位置叫做基线（baseline），有时候怎么也对不齐，都是因为这个



**文字的垂直对齐**

默认每个文字和父元素在垂直方向都是沿着基线对齐的

vertical-align

- 设置元素的垂直对齐的方式
- 可选值
	- baseline：（默认值）子元素和杜元素的基线对齐
	- top：子元素文本框的顶部和父元素文本框的顶部对齐
	- bottom：子元素文本框的底部和父元素的文本框的底部对齐
	- middle：（并非真的middle）
- 开发中经常通过vertical-align来消除图片下边的空白



### 文字样式

 font-size：字体的大小



font-weight：字体的字重

- normal：默认值，正常的粗细
- bold：加粗
- lighter：细的



font-style：字体的样式

- normal：默认值，正常的
- italic：斜体



font-family：

- 字体族，指定使用什么字体（微软雅黑、华文彩云）
- 字体的分类
	- serif：衬线字体
	- sans-serif：非衬线字体
	- monospace：等宽字体



**简写属性**

语法：

```css
font:任意 font-size/line-height font-family
```



font-face：通过它可以将远程字体提供给用户使用

- 首先要下载一个ttf文件（字体文件）

- ```css
	//引入字体
	@font-face{
	    src:url("./font.ttf");
	    font-family:"test";   
	}
	```

	

### 图标字体

在网页中，经常能够看到一些小图标，我们可以使用图片来表示这些图标 但是图片存在着一些不足： 

- 不便于缩放 

- 颜色无法改变

	 

图标字体（iconfont）

- 所谓的图标字体，指将小图标制作为字体文件
- 这里使用第三方图标字体库（fontawsome.com）



使用方法：

- 下载第三方图标字体库的文件并解压

- 将文件夹css和webfont复制到项目文件夹下

- 引入

	```html
	<link rel="stylesheet" href="./css/all.css">
	```

	

- 在页面中添加标签

	```css
	<i class="fa-solid fa-cat"></i>
	
	i{
	    font-size:80px;
	    color:green;
	}
	```

	

### 文档流

Normal Flow（正常布局流）

- 文档流就是网页中的其中一层 ，我们所创的元素默认都存在文档流中（相当于大地）
- 文档流中的元素，必须要遵循文档流中的规则在页面中排版
	- 块元素 ：
		- 块元素在文档流自上向下垂直排列
		- 块元素的默认宽度是auto，会把父元素撑满
		- 块元素的默认高度被内容撑开
	- 行内元素：行内元素在文档流中会自左向右水平排列，如果一行不足以容纳所有元素，则会另起一行继续自左向右水平排列
	  - 行内元素的默认高度和宽度都被内容撑开



### 包含块

containing block

- 包含块就是离当前元素最近的祖先**块元素**



### 水平布局的等式

子元素会在父元素内容区中排列，在文档流中，块元素的水平排列，必须要遵循如下三个等式：    

- 子元素可见框宽度 + 子元素的水平外边距 = 包含块内容区的宽度        200 + 600 = 800    
- margin-left + 可见框 + margin-right = 包含块内容区的宽度          100 + 200 + 500 = 800    
- 当等式不满足，同时所有的属性值中没有auto，此时浏览器会自动调整右外边距以使等式强制满足
- 当只有一个属性值设置为auto，则浏览器会自动调整该值以使等式满足 
- 当左右外边距为auto，而width有值时，则左右外边距会设置为相等的值，以使等式满足



**margin-left + border-left + padding-left + width + padding-right + border-right + margin-right = 包含块内容区的宽度**



垂直方向没有这个等式存在



### 浮动

是一种传统的网页的布局方式

- 通过浮动，**盒子可以使元素脱离文档流而横向排列**

float：

- 设置元素浮动 
- 可选值：  
	- none，默认值 元素不浮动  
	- left：向左浮动  
	- right：向右浮动 

浮动的特点：  

- 设置浮动后，元素或脱离文档流，其后的元素会自动往上移 
- 设置浮动后，元素会向其包含块的左侧或右侧移动
- 如果一行之内无法容纳所有的浮动元素，则后边的元素会自动换到下一行
- 浮动元素不会超过它上边浮动的兄弟元素，最多齐平
- **浮动元素不会盖住文字，文字会环绕在浮动元素的周围**



**元素脱离文档后的特点：**

块元素设置浮动后：

- 块元素不再独占一行，而是水平排列
- 宽度和高度都被内容撑开，没有默认值
- 浮动后，上面的布局等式无效



行内元素设置浮动后：

- 行内元素可以设置高度和宽度



总结：脱离文档流后，块元素也不再独占一行，宽高都被内容撑开，行内元素变成块元素（宽高可以设置）



### 高度塌陷问题

 在文档流中的元素，可以将其他元素的高度撑开，然而
当元素浮动脱离文档流后，它无法撑开父元素的高度，会导致父元素高度塌陷
父元素高度塌陷，其后的元素会自动上移，导致布局变得混乱

 

如何解决该问题？ 

- 可以直接将父元素的高度写死   
	- 但是这样一来父元素高度写死，无法根据子元素高度的变化而变化



### BFC

块级格式化

可以将BFC理解为一个隐藏的属性，当开启BFC后元素会具备如下的特征：
1. 开启BFC后，子元素的垂直外边距不会传递给父元素
2. 开启BFC后，元素不会被浮动元素所覆盖
3. 开启BFC后，元素可以包含浮动的子元素



```html
<style>
  .box1{
    border: 10px red solid;
    overflow: hidden;
    //overflow: auto;
  }

  .box2{
    float: left;
    width: 200px;
    height: 200px;
    background-color: #bfa;
  }

  .box3{
    width: 300px;
    height: 300px;
    background-color: orange;
  }
</style>
```



如何开启BFC:
- 需要用一些其他的样式来间接的开启BFC
- 由于BFC是通过一些样式间接开启的，所以都会有一些副作用，而我们要做的是找到一种可以额开启，同时副作用又比较小的

例如：
1. 浮动会开启元素的BFC，即给高度塌陷的父元素也设置float
2. 将overflow设置为一个非visible的值（overflow: hidden;auto）
3.  display:flow-root;  （完美，无副作用）



### clear

清除浮动元素对当前元素所产生的影响

clear
   - 清除浮动元素对当前元素所产生的影响
   - 可选值：
     left 清除左侧浮动元素对当前元素的影响
     right 清除右侧浮动元素对当前元素的影响
     both 清除两侧浮动元素对当前元素的影响



### clearfix

谁塌了就给谁加一个clearfix

```html
<style>
  .box1{
    border: 10px red solid;
  }
  .box2{
    float: left;
    width: 200px;
    height: 200px;
    background-color: #bfa;
  }
  .box3{
    clear: both;
  }
</style>
</head>
<body>
<div class="box1">
  <div class="box2"></div>
  <div class="box3"></div>
</div>
</body>
```

```html
<style>
  .box1{
    border: 10px red solid;
  }
  .box2{
    float: left;
    width: 200px;
    height: 200px;
    background-color: #bfa;
  }
  .clearfix::before,
  .clearfix::after {
  content: "";
  display: table;
  clear: both;
}
</style>
</head>
<body>
<div class="box1 clearfix">
  <div class="box2"></div>
</div>
```



### 定位

布局手段：

1、盒子模型（纵向）

2、浮动（横向）

3、定位



定位（position）：

- 通过定位可以将一个元素摆放到页面中的任意位置
- CSS中有4种定位方式
	- 相对定位
	- 绝对定位
	- 固定定位
	- 粘滞定位



#### 相对定位

将元素的position属性设置为relative则开启了元素的相对定位

position：

- 用来设置元素的定位方式
- 可选值
	- static（默认值）
	- relative
	- absolute
	- fixed
	- sticky
- 开启相对定位后的特点：
	- 开启相对定位但是**不设置元素的偏移量**，元素不会发生任何变化
	- 开启相对定位**不会使得元素脱离文档流**，不会改变元素的性质
	- 相对定位元素是参照其**原来位置**进行定位的
	- 相对定位会提升元素的优先级



偏移量

- 开启了定位的元素可以通过偏移量来设置元素的位置，对其它元素的位置不会产生影响

- 偏移量通常使用两个即可定位一个元素的位置

- 偏移量一共有四个

	- top

		- 元素的上边距离原来所在位置上边的距离

			```css
			top:200px
			```

			

	- bottom

	- left

	- right





#### 绝对定位

将元素的position设置为absolute，则开启了元素的绝对定位

  - 特点：
    1. 开启绝对定位后，如果不设置偏移量，元素的位置不会发生变化
    2. 开启绝对定位后，元素会脱离文档流，同时元素性质发生变化
    3. 绝对定位元素是参照于**离它最近的开启了定位的祖先元素**进行定位，
       如果所有的祖先元素都没有开启定位，则相对于浏览器窗口进行定位
    4. 绝对定位会提升元素的层级

所以在开发中，经常为一个元素开启绝对定位后，同时也会给它的父元素开启相对定位



##### 绝对定位的包含块

绝对定位参照于他的包含块进行定位

包含块是谁？

- 离他最近的开启了定位的祖先元素
- 如果所有的祖先元素都没有开启定位，其包含块是初始包含块 （可视窗口）



#### 垂直水平居中

当元素开启绝对定位后，一个新的等式出现了：

**left + margin-left + 可见框 + margin-right + right = 包含块内容区的宽度**

- 将left和right都设置为0，则可以实现水平方向的居中



垂直方向也可以实现居中了

**top + margin-top + 可见框 + margin-bottom + bottom = 包含块内容区的高度**



```css
.box2{
    width: 200px;
    height: 200px;
    background-color: greenyellow;
    position: absolute;
    margin: auto;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
}
```



#### z-index

开启了定位后，可以通过z-index来设置元素的层级（z代表的是空间中的一根轴，在z轴上越高，离人眼睛就越近）

**z值越大，元素越优先显示**

**祖先元素的层级再高，也无法盖住后代元素**

**z-index可以设置为负值，设置负值后元素会被文档流中的元素覆盖，消失了**



#### 固定定位

固定定位也是一种绝对定位，它的绝大部分特点和绝对定位是一样的，不同点在于，固定定位总是参照于浏览器的窗口进行定位

将元素的position设置为fixed，则开启了元素的绝对定位



#### 粘滞定位

将元素的position设置为sticky，则开启了元素的粘滞 定位 

- 粘滞定位的特点和相对元素很像（不脱离文档流）
- 不同点在于：粘滞定位相对于**离它最近的拥有滚动条的祖先元素**来定位



### 轮播图

### 导航条

### 下拉框



### 布局方法总结

1、盒子模型（box）

- 主要用来确定元素的**大小和间距**
- 主要用来确定元素的**纵向排列**

2、浮动（float）

- 本来用来处理文本环绕图片的效果，后来被用来实现元素的**水平排列**
- 因为它不是专门用来布局的，所以会有缺陷：**高度塌陷**

3、定位（position）

- 通过定位将一个元素摆到网页中特定的位置
- 主要用来处理网页中的小东西 



### 弹性盒子

1、弹性容器

- 要使用弹性盒必须先将元素设置为弹性容器

	- 要在哪使用弹性盒就把谁设置为弹性容器

		```css
		display:flex   //块级弹性容器
		display:inline-flex  //行内弹性容器
		```

2、弹性子元素（弹性项）

- 弹性容器的子元素都是弹性子元素（弹性项）

- 弹性子元素都会沿着弹性容器的主轴排列
	- 主轴：主轴就是弹性子元素的排列方向
	
		- 如何设置主轴的方向：
	
			```css
			flex-direction:row;
			//row:自左向右水平排列
			//column：自上向下垂直排列
			//row-reverse:自右向左水平排列
			//column-reverse：自下向上垂直排列
			```
	
			```css
			felx-wrap:nowrap;
			//warp 换行
			//wrap-reverse 反向换行（调整侧轴方向）
			//设置元素是否自动换行
			```
	
			```css
			flex-shrink:0
			//弹性盒子不缩减
			```
	
	- 侧轴（辅轴）：与主轴垂直的
	
	

#### flex-flow

简写，不讲究顺序

```css
flex-flow:wrap row;
```



#### 主轴侧轴对齐方式

主轴：

**justify-content:** 设置元素在主轴上对齐方式

​	可选值：

- start：默认值，元素从主轴的起始位置对齐
- end：元素靠主轴的结束位置对齐
- center：沿主轴方向居中对齐
- space-between：将主轴方向的空白位置均匀分配到元素之间（**两端无距离**）
- space-around：将主轴方向空白位置分配到元素周围。

![image-20250317145211529](../AppData/Roaming/Typora/typora-user-images/image-20250317145211529.png)

- space-evenly：将元素方向的空白位置分配到元素之间

![image-20250317145341209](../AppData/Roaming/Typora/typora-user-images/image-20250317145341209.png)



侧轴：

**align-items**：设置元素在侧轴上的对齐方式

可选值：

- start：元素从侧轴的起始位置对齐
- end：元素靠侧轴的结束位置对齐
- center：沿侧轴方向居中对齐
- stretch：默认值，元素被拉高，填满侧轴方向



align-content：

- space-between：将侧轴方向的空白位置均匀分配到元素之间（**两端无距离**）
- space-around：将侧轴方向空白位置分配到元素周围
- space-evenly：将侧轴方向的空白位置分配到元素之间（两端有距离）



#### 弹性子元素的样式

**flex-basis**：（即是宽度也是高度，根据主轴方向）

- 容器的基础大小，会根据主轴的方向自动设置width或height

- 主轴方向垂直：设置高度

	主轴方向水平：设置宽度

- 可选值：

	- auto

**felx-shrink:**

```css
flex-shrink:1  //默认值
```

当父元素容纳不下时，弹性子元素自动缩减。

收缩系数越大，缩得越多

**felx-grow**:

- 弹性子元素得生长系数
- 当容器有富裕空间时，如何分配到子元素
- 默认值：0 不生长
- 生长系数越大，长的越多

**align-self:**

- stretch

- end

**order:**

设置弹性子元素的位置

值越小，越往前



#### flex

简写：**有顺序：grow、shrink、basis**

- 可选值

	initial：默认值 0 1 auto

	auto：相当于 1 1 auto

	none：相当于 0 0 auto

```css
flex:1 1 auto;
```



### 背景相关的样式

**background-color:**

**background-image：**

不会自动缩放，贴着元素的左上角显示

若元素大小超过背景图片，会平铺（图片复制，每一个角落都撑满）

```css
background-image:url("")
```

**background-repeat:** 背景的重复方式

可选值：

- repeat：默认值，背景图片会沿元素的水平垂直方向双方向垂直
- repeat-x：水平方向重复
- repeat-y：垂直方向重复
- no-repeat：图片有多大显示多大

- repeat-space：平均分布
- repeat-round：自动适应背景大小，会缩放



**background-position:** 设置背景图片的位置

两个参数：水平偏移量 垂直偏移量

可选值：

- top bottom left right center（像九宫格选择位置）

- 如果只传了一个参数，第二个参数默认是center

- ```
	background-position:-40px -50px;
	```

**background-attachment**

可选值：

- fix
- scroll

**background-size**

最好不要同时设置宽高，只设置一个，另一边会比例缩放

```css
background-size:100% 100%;
```

- contain
- cover 可能显示不全



#### 简写属性

没有数量以及顺序要求

```
background:。。。
```



### 雪碧图

当我们第一次使用按钮时，往往会有这种闪烁的现象出现
这是因为，浏览器在加载外部资源时，是以嵌套的形式来完成的
像hover active这些图片都是下载加载触发的，网速慢使用户需要时间来完成加载
而图片加载完成前，是链接处在没有背景图片可以显示的状态，所以会显示空白

我们可以通过CSS-Sprite来解决这个问题
- 所谓CSS-Sprite就是将，将多个小的图片统一放入到一个大图片（雪碧图）中，
  然后通过位移来切换不同的图片
- 使用CSS-Sprite可以将多个小图片进行整合，减少客户端发送请求的次数，提升用户体验
- 在早期的网页中，几乎所有的小图标都是通过雪碧图来实现的。随着图标字体的广泛应用，雪碧图的使用也变得相对少了些

雪碧图
1. 雪碧图是位图，位图放大后会失真
2. 雪碧图无法修改颜色
3. 雪碧图支持彩色图标

图标字体
1. 图标字体是矢量图，可以任意放大缩小不会失真
2. 图标字体可以任意修改颜色
3. 图标字体只支持单色图标



### 表格

table

- 和日常生活中使用的表格一样
- 可以用表格来表示一些格式化的数据

表头（加粗）

<thead></thead>

<th></th>

表的主体

<tbody></tbody>

表尾

<tfoot></tfoot>

一行

<tr></tr>

一个单元格

<td></td>

#### 表格的边框

```html
<style>
    table{
        width: 80%;
        border: 1px solid #000;
        border-collapse: collapse;  //合并边框
    }

    td{
        border: 1px solid #000;
    }
</style>
```



#### 合并单元格

```css
<td colspan="3"></td> //横向合并单元格
<td rowspan="2"></td>
```

#### 表格的对齐

表格中文字的水平居中

```css
text-align:center;
//可以自动垂直水平居中
```



### 表单

```html
<!-- 使用form标签来创建一个表单 -->
<!--action用来指定表单提交到哪儿-->
<form action="target.html">
    <!-- 表单项 -->
    <!-- 文本框
         - input type属性为text
         - 如果希望表单中的数据真的被提交给服务器，
           必须为表单项指定name属性 -->
    <input type="text" name="username">
    
    <!-- 提交按钮
         - input type属性为submit
         - 可以通过value属性来修改按钮上的文字 -->
    <input type="submit">
</form>
```

单选框

- 单选框是通过name属性来分组的，**相同name属性的为一组**，这样才有单选的效果
- radio

- ```html
	<input type="radio" name="gender" value="男">男
	<input type="radio" name="gender" value="女">女
	```

	

多选框

- checkbox

- ```html
	<input type="checkbox" name="hobby" value="lq">篮球
	//...可以有多个
	```

	

下拉列表

-  select option

	```html
	<select name="language">
	  <option>JavaScript</option>
	  <option>Java</option>
	  <option>Python</option>
	</select>
	```

- 添加multiple属性可以将下拉列表设置为多选的下拉列表



文本框灰色占位符

placeholder=""

默认值

value=""



重置

```css
<input type="reset" value="重置">
```

普通按钮（使用的频率最高，通过JS给按钮加功能）

```css
<input type="button" value="按钮">
```

可伸缩文本框

```css
<textarea name="text" cols="30"></textarea>
```

扩大可点击范围

```css
<input type="radio" name="gender" value="male" id="male"> <label for="male">男</label>
<input type="radio" name="gender" value="female" checked id="female"> <label for="female">女</label>
```



### 局中的总结

#### 盒子模型

```css
margin:0 auto;
//水平居中
```

- 利用了盒子模型在水平布局的等式：左右外边距+可见框宽度=包含块宽度

- 缺点：
	- 不能解决垂直居中的问题
	- 居中的元素必须指定宽度

 

#### 定位

```css
.box1{
    width: 400px;
    height: 400px;
    border: 10px red solid;
    position: relative;
}

.box2{
    width: 200px;
    height: 200px;
    background-color: #bfa;
    
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
}
```

- 原理：利用定位后新的等式来实现居中
	- 左右偏移量 + 左右外边距 + 可见框的宽度 = 包含块的宽度
	- 上下偏移量 + 上下外 边距 + 可见框的高度 = 包含块的高度
- 缺点：
	- 设置的样式稍微多点
	- 必须指定元素的大小



#### 弹性盒子

```css
display:felx;
justify-content:center;
align-items:center
```



### 变形

通过变形可以对元素的位置大小角度进行修改

transform用来设置变形：需要通过不同的变形函数来实现元素的变形

#### 平移

正值向右（上）移

负值向左（下）移

值还可以是百分比

```css
transform:translateY(100px)
transform:translateX(100px)
transform:translateZ(100px) 
transition:all 3s
```

```css
transform:translate(100px,100px)
transform:translate3D(100px,100px,100px)
```

#### 旋转

沿着x轴旋转：rotateX()

沿着Y轴转：rotateY()

沿着Z轴转：rotateZ()

```css
transform:rotateX(90deg)
//deg度数
transform:rotateY(90deg)
transform:rotateZ(90deg) //像红手绢
```

transform-origin：指定旋转的原点

```css
transform-origin：top center
```



#### 缩放

 scaleX：X轴缩放

scaleY：Y轴缩放

scale：XY轴缩放

```css
transform:scale(3)
```

 

#### 3D

```css
transform-style:preserve-3d
```



### 过渡

通过过渡，可以是的元素在样式发生变化的，可以一点点改变，而不是一下子

**transition-property**

```css
transition-property:background-color,height,margin;
transition-duration:3s  // 时间

```

**transition-duration**

- 过渡效果所花费的时间
- 单位：
  s 秒
  ms 毫秒

**transition-delay**

- 过渡效果的延时

**transition-timing-function**

- 指定过渡的时间的曲线
- 可选值：
  ease，默认值 先加速然后减速
  linear 匀速运动
  ease-in 加速运动
  ease-out 减速运动



### 动画

#### 动画的样式

​      **animation-name**
   - 指定动画的名字

  

  **animation-duration**

   - 一次动画执行的时间

  

  **animation-iteration-count**

   - 动画执行的次数

        - infinite 一直执行

​        **animation-direction**

- 动画的方向
	    - 可选值：
	        normal 默认值
	        reverse 动画反向执行
	        alternate 动画正向反向交替执行
	        alternate-reverse 和alternate相反



**animation-fill-mode**

- 动画的填充模式
	    - 可选值：
	        none 默认值 延迟时元素保持不变，动画执行结束恢复原状
	        forwards 延迟时元素保持不变，动画执行结束保持最终状态
	        backwards 延迟时元素变为初始状态，动画执行结束恢复原状



#### 关键帧

```html
<style>
    @keyframes move {
        from {
            margin-left: 0;
        }
        50%{
            margin-left: 250px;
        }
        to {
            margin-left: 500px;
        }
    }

    .box1{
        width: 100px;
        height: 100px;
        background-color: tomato;

        animation-name: move;
        animation-duration: 10s;
    }
</style>
```

 
