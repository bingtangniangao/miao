# css
- 内嵌样式
`<p style="color:red;font-size50">文本</p>`
- 文档内嵌
```
<style>p{color=red;font-size:40;}
</style>
```
- 外部引入
`link rel="stylesheet" type="text/css" href="style.css"`  
- @import "text.css"
- 优先级
  - 内嵌>文档>外部>浏览器自带
  - 浏览器自带
  `< b>加粗</b>`
  `<span style="font-weight:bold">加粗</span>`
`<b style="font-weight:normal">去加粗</b>`
- !important 强制最高优先级
- 继承
  - <p><b>文字</b></p>
  - b 会继承 p 的元素外观如文字颜色字体,但是布局样式不会被继承如外边框 border, 强制继承布局inherit
  ```
  <p><b>htmle</b></p>
  <style>
    p{
      border:1 solid red;
    }
    b{
      border:inherit;
    }
  </style>
  ```
## 选择器
### 基本选择器
- * 通用
- 元素选择器
- #abc id 选择器
- .abd 类选择器
  - p.abc  多个 class选择之一
  - 也可单个class 定义多个值
    `class=abc edf`
### 属性选择器 
- [href] 属性名
- [type="password"] 属性名+值
- [href^=] 头
- [href$=] 尾
- [href*=]  指定模糊找
- [href~=] 属性多个值时,匹配其中
- [lang|=]  使用-号连接  如ch-zh
### 复合选择器
- p,b,i,span,#abc,.bcs{color:red}
- 后代选择器 p b{...};所以 p 里面的 b 不在乎深度
- 子选择器  P>b{...}孙子无法选择
- 相邻兄弟 p+b {...}彼此之间不能有其他元素,
- 普通兄弟 p~b p 后面所有的 b 只能是同级,和和后代的区别.
### 伪元素 ::
- 只能对块级元素有效果,sapn 无效默认是定位到了 body
- ::first-line{我}
    - 快级首字母可以是中文,::前可以加元素
-  :: before 文本前插入文字
- :: after 文本后插入文字
### 伪类选择器
#### 子元素系列
- :root 根选择器
- ul>li :first-child{}第一个子元素,如果把 ul 和 li 去掉,则全部加红:选择 body 下 ul 的全部子元素.伪类元素都需要加前置选择器,限定范围.
- ul>li:last-child{} 最后一个
- ul>li:only-child只选择只有一个的子元素,相同也不行.
- ul>p:only-of-type{}子啊子元素里 p 是唯一的类型也只有一个,才行,有多个相同的也不行,但可以有不同的,区别于上一个.
- ul>li:only-child(2) 选择子元素是第2个是 p.
#### nth-child
- ul > li:nth-child(2){第二个}
-  ul > li: nth- liast - child(2){倒数第2个}
- div > p:nth-of-type(2){这个没有唯一,只要是p 类型是第二的就行}
- div>p:nth-last-of-type(2){第二个}
#### ui伪类
```
UI 伪类选择器是根据元素的状态匹配元素。 1.:enabled
:enabled {
       border: 1px solid red;
    }
  解释:选择启用状态的元素。
2.:disabled
    :disabled {
       border: 1px solid red;
}
  解释:选择禁用状态的元素。
3.:checked
    :checked {
       display: none;
}
解释:选择勾选的 input 元素。
4.:default
    :default {
       display: none;
}
解释:从一组类似的元素中选择默认元素。比如 input 被勾选的即默认的。 5.:valid 和:invalid
     input:valid {
       border: 1px solid blue;
    }
    input:invalid {
       border: 1px solid green;
    }
  解释:输入验证合法与不合法显示时选择的元素。
6.:required 和:optional 
      input:required {
       border: 1px solid blue;
    }
    input:optional {
       border: 1px solid green;
}
解释:根据是否具有 required 属性选择元素。

```
#### 三.动态伪类选择器
  ```
  动态伪类选择器根据条件的改变匹配元素。
1.:link 和 visited a:link {
color: red; }
    a:visited {
       color: orange;
}
解释::link 表示未访问过的超链接，:visited 表示已访问过的超链接。
2.:hover
    a:hover {
       color: blue;
}
  解释:表示鼠标悬停在超链接上。
3.:active
    a:active {
       color: green;
}
  解释:表示鼠标按下激活超链接时。
4.:focus
    input:focus {
       border: 1px solid red;
}

解释:表示获得焦点时。
```
#### 四.其他伪类选择器
```
1.:not
    a:not([href*="baidu"]) {
       color: red;
}
  解释:否定选择器，反选。
2.:empty
    :empty {
       display: none;
}
  解释:匹配没有任何内容的元素,在俩个元素之间加入空元素
3.:lang
    :lang(en) {
       color: red;
}
解释:选择包含 lang 属性，属性值前缀为 en 的元素。和属性选择器匹配结果一致。
4.:target
    :target {
       color: red;
}
  解释:定位到锚点时，选择此元素。
    5.::selection
    ::selection {
       color: red;
}
解释:这是一个伪元素选择器，当选择文字时触发选择。CSS3 版本下的选择器。
```
####  CSS 颜色与度量单位
-  em 是相对单位，与字号大小挂钩，会根据字体大小改变自己的大小

- x 也是相对单位，但由于和分辨率挂钩，导致他其实就变成一个绝对单位 了，自然灵活性没有 em 高，但是使用难度较低，
-  %百分比,长度比较好理解，就是挂钩它所在区块的宽度。而 font-size 则是继承到的原 始大小的百分比。
#### CSS 字体(font)样式
- font-size
  - `p{
       font-size: 50px;
    }`
  - `p{font-size: smaller;}`
- font-variant 英文字体是否转换为小型大写 
   ```
    //先让父元素设置小型大写
     body {font-variant: small-caps; }
    //让子元素设置恢复小写 
    p{font-size: 50px;font-variant: normal;}
  ```
- font-style

|值|说明
|--|--|
normal|表示让倾斜状态恢复到正常状态。
italic|表示使用斜体,有些字不会倾斜,调用系统字库
oblique|表示让文字倾斜。区别在没有斜体时使用。
```
p{
font-style: italic;
}
```
- font-weight设置字体是否加粗

|值|说明
|--|--|
normal|表示让加粗的字体恢复正常。
bold|粗体
bolder|更粗的字体,用在包裹了的标签
lighter|轻细的字体
100 ~ 900 之间的数字|600 及之后是加粗，之前不加粗
```
p{
font-weight: bold;
}
```

- font-family  设置 font 字体
`//备用字体有,分开p{font-family: 楷体,微软雅黑,宋体; serif}`
- 简写 font:small-caps italic bold 50px 楷体,顺序除了字号和字体在最后,其他不限制.
- web 字体
  - 当用户没有安装字体时,从服务器下载(是先检测还,没有在下载?)
  ```
  @font-face { //引入
       font-family: abc; //至少要写俩个样式
        src: url('BrushScriptStd.otf'); }//地址
      p{
      font-size: 50px; font-family: abc;}
  ```
    - 不建议使用字体,太大了
#### CSS 文本(text)样式
- 文本总汇

属性名|说明|CSS 版本
|-|:-:|-:
text-decoration|装饰文本出现各种划线。|1
text-transform|将英文文本转换大小写。|1
text-shadow|给文本添加阴影|3
text-align|设置文本对齐方式|1,3
white-space|排版中的空白处理方式|1
letter-spacing|设置字母之间的间距|1
word-spacing|设置单词之间的间距|1
line-height|设置行高|1
word-wrap|控制段词|3
text-indent|设置文本首行的缩进|1
1. text-decoration
```
p{
       text-decoration: underline;
    }
```
值|说明
-|-|
none|让本身有划线装饰的文本取消掉
underline|让文本的底部出现一条下划线
overline|让文本的头部出现一条上划线
line-through|让文本的中部出现一条删除划线
blink|让文本进行闪烁，基本不支持了
2. text-transform
```
p{
text-transform: uppercase;
}
```
值|说明
-|-|
值|说明
none|将已被转换大小写的值恢复到默认状态
capitalize|将英文单词首字母大写
uppercase|将英文转换为大写字母,英文字前加空格
lowercase|将英文转换为小写字母
3. text-shadow
```
p{
text-shadow : 5px 5px 3px black;
}
解释:给文本添加阴影。其中四个值，第一个值:水平偏移;第二个值:垂直偏移;第 三个值:阴影模糊度(可选);第四个值:阴影颜色(可选)。
```
#### 文本控制
1. text-align
```
    p{
       text-align: center;
    }
```
值|说明
--|--|
left|靠左对齐，默认
right|靠右对齐
center|居中对齐
justify|内容两端对齐,最后一行不能两端对齐
start|让文本处于开始的边界
end|让文本处于结束的边界
- justify在表单的标签名字要俩端对齐方法是文字底下加 span 且属性为inline-block
2. white-space
```
p{
white-space: nowrap;
}
```
解释:处理空白排版方式。
值|说明
-|-|
normal|默认值，空白符被压缩，文本自动换行
nowrap|空白符被压缩，文本不换行
pre|空白符被保留，遇到换行符则换行
pre-line|空白符被压缩，文本会在排满或遇换行符换行
pre-wrap|空白符被保留，文本会在排满或遇换行符换行
3. letter-spacing
```
p{
letter-spacing: 4px;
}
```
解释:设置文本之间的间距。

4. word-spacing
```
p{
word-spacing: 14px;
}
```
解释:设置英文单子之间的间距。
值|说明
--|--|
normal|设置默认间距
长度值|比如:“数字”+“px”

5. line-height
```
p{
line-height: 200%;
}
```
解释:设置段落行高。
值|说明
-|-|
normal|设置默认间距
长度值|比如:“数字”+“px”|
数值|比如:1,2,3
%|比如:200%
6. word-wrap
```
p{
word-wrap: break-word;
}
```
解释:让过长的英文单词断开。
值|说明
-|-|
normal|单词不断开
break-word|断开单词
7. text-indent
```
p{
text-indent: 20px;
}
```
解释:设置文本首行的缩进。

值|说明
-|-|
normal|设置默认间距
长度值|比如:“数字”+“px”
## CSS 盒模型
#### 元素尺寸

属性|值|说明|CSS 版本
-|-|-|-|
width|auto、长度值或百分比|设置元素的宽度|1
height|auto、长度值或百分比|设置元素的高度1
min-width|auto、长度值或百分比|设置元素最小宽度|2
min-height|auto、长度值或百分比|设置元素最小高度|2
max-width|auto、长度值或百分比|设置元素最大宽度|2
max-height|auto、长度值或百分比|设置元素最大高度|2
```
div {
    width: 200px;auto
    height: 200px;auto
}
```
- 解释:auto 是默认值，width 在 auto 下是 100%的值;height 在 auto 下是自适应。body 也是有边距的,没有高度,margin
#### 内边距
属性|值|说明|CSS 版本
-|-|-|-|
padding-top|长度值或百分比|设置顶部内边距|1
padding-bottom|长度值或百分比|设置底部内边距|1
padding-left|长度值或百分比|设置左边内边距|1
padding-right|长度值或百分比|设置右边内边距|1
padding|1 ~ 4 个长度值或百分比|简写属性|1
```
//设置四个内边距 div {
    padding-top: 10px;
    padding-bottom: 10px;
    padding-left: 10px;
    padding-right: 10px;
}
//简写形式，分别为上 10px、右 10px、下 10px、左 10px 
div {padding: 10px 10px 10px 10px;}
//简写形式，分别为上 10px，左右 50px，下 200px 
div {padding: 10px 50px 200px;}
//简写形式，分别是上下 10px，左右 20px
 div {padding: 10px 20px;}
//简写形式:上下左右均 10px 
div {padding: 10px;}
```
#### 元素外边距
属性|值|说明|CSS 版本
-|-|-|-:
margin-top|长度值或百分比|设置顶部内边距|1
margin-bottom|长度值或百分比|设置底部内边距|1
margin-left|长度值或百分比|设置左边内边距|1
margin-right|长度值或百分比|设置右边内边距|1
margin|1 ~ 4 长度值或百分比|简写属性|1
```
//设置四个内边距 div {
    margin-top: 10px;
    margin-bottom: 10px;
    margin-left: 10px;
    margin-right: 10px;
}
//简写形式，分别为上 10px、右 10px、下 10px、左 10px 
div {margin: 10px 10px 10px 10px; }
//简写形式，分别为上 10px，左右 50px，下 200px 
div {
       margin: 10px 50px 200px;
    }
//简写形式，分别是上下 10px，左边 20px 
div {
       margin: 10px 20px;
    }
//简写形式:上下左右均 10px 
div {
       margin: 10px;
    }
  ```
#### 溢出
属性|值|说明|CSS 版本
-|-|-|-
overflow-x|溢出值|设置水平方向的溢出|3
overflow-y|溢出值|设置垂直方向的溢出|3
overflow|溢出值|简写属性|2
溢出处理主要有四种处理值:
值-|说明
|-|-|
auto-|浏览器自行处理溢出内容。如果有溢出内容，就显示滚动条，否 则就不显示滚动条。
hidden-|如果有溢出的内容，直接剪掉。
scroll-|不管是否溢出，都会出现滚动条。但不同平台和浏览器显示方式 不同。
visible-|默认值，不管是否溢出，都显示内容。
```
//设置溢出为 auto 值 div {
    overflow-x: auto;
}
```
####  盒模型[下]
- 元素可见性
使用 visibility 属性可以实现元素的可见性，这种样式一般可以配合 JavaScript
来实现效果。样式表如下:

属性|值|说明|CSS 版本
-|-|-|-
visibility|visible|默认值，元素在页面上可见。|2
visibility|hidden|元素不可见，但会占据空间。|2
visibility|collapse|元素不可见，隐藏表格的行与列， 如果不是格，则和 hidden 一样。|2
```
//设置元素隐藏，但占位 div {
       visibility: hidden;
    }
//隐藏表格的行或列，但不占位，Chrome 和 Opera 不支持 table tr:first-child {
       visibility: collapse;
    };
```
- 元素盒类型
  - 1.块级元素(区块);2 行内元素(内联);3 行内-块级元素(内联块);4.隐 藏元素。

属性|值|说明|CSS 版本
-|-|-|-
display|block|盒子为块级元素|1
display|inline|盒子为行内元素|1
display|inline-block|盒子为行内-块元素|2
display|none|盒子不可见，不占位|1
```
//将行内元素转成块级元素 span {
    background: silver;
    width: 200px;
    height: 200px;
    display: block;
}
//将块级元素转换成行内元素 div {
    background: silver;
    width: 200px;
    height: 200px;
    display: inline;
}
//将块级元素转化成行内-块元素 div {
    background: silver;
    width: 200px;
    height: 200px;
    display: inline-block;
}//当 span 紧挨着是没有空格,换行有空格
//将元素隐藏且不占位 div {
    display: none;
}
```
- 元素的浮动
  - CSS 盒模型有一种叫浮动盒，就是通过 ***float*** 属性建立盒子的浮动方向，样式表如下:

属ft|ft|说ft|CSS 版本
-|-|-|--:|
float|left|浮动元素靠ft|1
float|right|浮动元素靠ft|1
float|none|禁用浮动 默认?|1
- 不浮动框架会上移,文字没动
```
//实现联排效果 #a {
       background: gray;
       float: left;
    }
    #b {
       background: maroon;
       float: left;
}
#c {
       background: navy;
       float: left;
    }
//实现元素右浮动 #c {
       background: navy;
       float: right;
    }
//取消元素的浮动 #c {
       background: navy;
       float: none;
    }
```
- clear 属性
- 刚才的浮动有一个问题:当一个元素盒子被浮动后，下面的元素会自动堆叠处理，导致 元素不可见或部分不可见。我们可以使用 clear 属性来处理。

属性|值|说明|CSS 版本
-|-|-|-:|
clear|none|允许两边均可浮动|1
clear|left|左边界不得浮动|1
clear|right|右边界不得浮动|1
clear|both|两边都不得浮动|1
```//两边均不可浮动 #c {
    background: navy;
    clear: both;
}```