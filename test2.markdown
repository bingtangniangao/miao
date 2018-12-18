大喵教育前端培训
================

## 阶段性测试 2018.12.07

### 大喵教育版权所有 | 出题人：谢然


01. 用文字描述如下选择器将选择哪些（个）元素
    ```css
    div, h1 {} 0002
    div[class] [id="abc"] {}0021
    div:hover ul li > div {}0014
    body :active {}0011
    div:hover::after {}0021
    ::selection {} 
    :target {}
    input + ul + p ~ span {}
    ```
	答:  div 和 h1
	  	 元素为 abd 的标签
	    当选中 div 时,的后代元素 ul 的后代元素 li 的子元素 div
	    标签被激活时 鼠标按下为松开手时 
	    在 div 后面添加元素
	    鼠标选中时 只能设置 前景色和背景色
	     选中 id 为 地址栏中#后面的元素
	    input 的相邻 ul 的相邻 p 的普通兄弟 span
	    
	    伪类就是实实在在的元素, 伪元素就不是了, 伪元素后面只能是文字,不能有其他标签或类 ,* {}是直接选不中active的,  可以写成* :active{}
02. 分别写出如下几个选择器的优先级
    ```css
    * * * {} 0000
    div * span {} 0002
    div[title] {}0011
    fieldset legend + input {} 0003
    #some  #thing .not:hover .abc:hover {}     0240
    ```
  	
03. https://www.example.com/a/b/ 页面中有如下代码
    ```html
    <link rel="stylesheet" href="//test.example.com/path/../the/../path/c.css">
    ```
    请问最终引入的c.css的完整路径是什么？
     <link rel="stylesheet" href="https://test.example.com/path/c.css"    9.23没听
04. `em,px,rem,vw,vh` 分别代表多长？
     px 屏幕的像素 系统分辨率同显示器物理分辨率相同  
     em  相对于父
     rem 相对于 html的字号大小
     vw 视窗宽度，1vw等于视窗宽度的1%。
     vh：viewpoint height，视窗高度，1vh等于视窗高度的1%。
	  VMAX VW与 vh 的 jiaodaze
	  vimin  vmyu vh 的教下者
05. 显示器的物理分辨率为 `1920x1080`，操作系统设置的分辨率为 `1280x720`，网页的放大倍数为 `110%`，请计算一个 CSS 像素对应多少个显示器物理像素（面积与长度）？
    长度:110* (1920/1280 )
    面积 1.65*1.65	
06. 写出如下代码显示在浏览器后**每个单词**的字号
    ```html
    <style>
      html {
        font-size: 20px;
      }
      section {
        font-size: 10rem;
      }
      p {
        font-size: 24px;
      }
      span {
        font-size: 150%;
      }
      .sucks {
        font-size: inherit;
      }
    </style>
    <body>
      <section>
        <h2>Brown</h2>
        <p>quick</p>
        <p>jumps <span>over <span>lazy</span> dog</span></p>
        <p class="sucks">sucks</p>
      </section>
    </body>
    ```
    h2  200px  300px 要先看在浏览器中是多大
    p  24px
    over  24*150%  ; lazyy  53px;  dog 36px
    
07. 字体的 italic 与 oblique 的区别是？
		都是字体倾斜  当  oblique 是文字物理倾斜, italic 是一种字体  obsolete 废弃
08. 写出满足如下条件的选择器
    * 第  8个子结点之后，倒数第 5 个子结点之前的li结点
    * 【类名】以“damiao-”开头的元素
    * rel 属性中有 nofollow 这个单词的标签
    答:li:nth-child(n+8):nth-last-child(n+5){}
       class="damiao-desk"
       class^="damiao-"
    
09. 链接伪类的几种状态书写的顺序是什么？为什么？
    a:link
    a:visited
    focus
    a:hover
    a:active
    link 和 visited 是未激活和激活,不能同时存在
     link和visited是常态效果，hover和active是瞬时效果。
     再讨论hover和active的顺序，若把hover放在active后面，当点击链接一瞬，实际你在激活active状态的同时触发了hover伪类,hover在后面覆盖了active的颜色，所以无法看到active的颜色。故hover在active之前
10. 如下 font 属性的值哪一个是书写正确的？
    * font: serif 24px;
    * font: serif bold 24px/1.2;
    * font: bold 24px/1.2 serif;
    答:  font: bold 24px/1.2 serif;
11. vertical-align 取 middle 时元素如何对齐？
     居中对齐
12. 什么是 baseline？
     基线对齐  x 字符的下方为基线  对应汉字来说没有基线  图片的底部就是基线  表单元格的内容在单元格中垂直居中
13. 详述你对盒模型的理解。
     边距border  外边距margin  内边距padding  内容content
     
      padding 可以看到元素的背景 
     
14. 如何让一个元素可被 focus？如何去掉其被 focus 时的虚框？
      input{text-indent: 1em;}
 		#search1{ }
	   #search2{ border-width: 0; }
 		#search3{ border:1px solid red; }
 		#search4{ outline:medium;}
		 /*获取焦点时 外边框显示红色*/
 			#search4:focus{ border:1px solid red; }
 		#search5:focus{ border:1px solid red; }
 		#search5{ appearance: none; }
15. 如何给css添加注释
     <!--  -->
     /*  */
     x  /
16. 指出如下css代码中的错误
    ```
    p,h1,{
        
        background-color: rgba:(abc)
        font-varient; abc;
        colr: #ff048;
        font: "serif" 25px;
    }
    ```
   答  p,h1
    rgba(0,0,0,0)
    colr: #ff0468;
    font: 25px serif;
    variant
    color: 可以是 3 位 4位  6位 8位  
17. 元素的高度写百分比在什么情况下【无效】，为什么？在什么情况下【有效】，有效时是以哪个元素的高度为基准值？
	  %是相对父元素  , 可以把 html, body 设置为100%;  或者自身设置为 position:fixed,相对于窗口.
	  为 auto, 父元素有子撑大, 子元素由父决定,形成依赖,逻辑有矛盾
	  
	  
	  
	  
18. 解释 box-sizing 可以取哪些值，以及每个值的意义
  

   box-sizing: content-box; 不影响边框和内边距
   box-sizing: border-box;  从边框开始为宽度
19. 如下结构中，div 有两个伪元素，分别标出伪元素的位置，用 `<before></before>` 表示 `::before` 伪元素，用 `<after></after>` 表示 `::after` 伪元素
    ```html
    <div>
      <h1>The article</h1>
      <p>the quick brown fox</p>
    </div>
    ```
     <after> <h1>The article</h1></after>
      <before><p>the quick brown fox</p></before>
20. 如何在伪元素中插入换行符？如何让这个换行符在页面中生效？
     
		<span class="loading"></span>
			.loading::after {
 			 display: inline-table;
 			 content: "\A.\A..\A...";
 			 white-space: pre;
			 animation: spin4 2s steps(4) infinite;
				}
			
	<dot>...</dot>
	 		dot::before {
  			display: block;
 			content: '...\A..\A.';
  			white-space: pre-wrap;
  			animation: dot 3s infinite step-start both;
			}

21. 简述 ie7 市场份额比 ie6 低的原因并在网络上找出目前各大浏览器在中国和全球的市场份额
   肯定有很多老机器只能用IE 6，原因就是盗版XP了，
   https://www.oschina.net/news/58359/ie6-when-to-died
   360 32.2%     
   chrome 20.4%
   qq  13.6%    
   --手机--
      uc 28%  qq 24%  360 20.6%    //全球 chrome55 safari 14 uc 7 firefox  5
22. 页面有无 `doctype` 声明会有什么区别？

1、定义：

DOCTYPE标签是一种标准通用标记语言的文档类型声明，它的目的是要告诉标准通用标记语言解析器，它应该使用什么样的文档类型定义（DTD）来解析文档。

<!DOCTYPE> 声明必须是 HTML 文档的第一行，位于 <html> 标签之前。 

2、作用：

声明文档的解析类型(document.compatMode)，避免浏览器的怪异模式。

document.compatMode：

BackCompat：怪异模式，浏览器使用自己的怪异模式解析渲染页面。

CSS1Compat：标准模式，浏览器使用W3C的标准解析渲染页面。

 
    这个属性会被浏览器识别并使用，但是如果你的页面没有DOCTYPE的声明，那么compatMode默认就是BackCompat，

    浏览器按照自己的方式解析渲染页面，那么，在不同的浏览器就会显示不同的样式。

    如果你的页面添加了<!DOCTYPE html>那么，那么就等同于开启了标准模式

    那么浏览器就得老老实实的按照W3C的标准解析渲染页面，这样一来，你的页面在所有的浏览器里显示的就都是一个样子了。

这就是<!DOCTYPE html>的作用。
23. 有一张高为 100 宽为 50 的图片，内有一个直径为 40 的圆，其做为一个 200x200 的元素的背景图片，background-size 为 contain 和 cover 时，圆的直径分别为多少？

 
 




24. 写出实现小米网首页 logo 返回主页的动画效果的代码。
    div{
     width:50px;
     height:50px;
     background-imge:url  ,url
     background-position:00,50px 0;
              repeat:
    }
    
25. 给出至少 5 种水平垂直居中方案。
		表格  定位  行内块居中  定位+translate  flex

26. 简述 em 框，内容区，行内框，行框的构成以及其需要注意的问题。
		em 高度是字号 字形是可以高出 em 框
		内容区为 em 框串起来的内容区
		行内框 
    
27. 如何确定一个行内框的baseline及其最高点和最低点？
    
		inline  
		 文字的 baseline
		 行高的最高点和最低点
		 
		 其他行内 yuans
		 最后一行的内容 baseline
		 margin-box 的上边缘和下边缘


28. `td` 元素的 `headers` 属性是干嘛的？
   有助于读屏软件读取单元格的表头                            
      
29. color 这个属性有什么需要注意的地方？
    边框会继承
   
30. 如何理解 inline-block 元素？它有什么需要注意的地方？
		空格解决  font-size 为0  
		          word-spacing:-6px;
}
       https://www.zhangxinxu.com/wordpress/2012/04/inline-block-space-remove-%E5%8E%BB%E9%99%A4%E9%97%B4%E8%B7%9D/  
       
       从外面看是行内元素  考虑自身位置时 为行内元素, 布局时为块
       
       没有内容与有内容 baseline 不一样,自身有 bfc
31. 什么是 CSS Sprite？为什么要使用 CSS Sprite？它有哪些优缺点？

 	  把多个图片 整合到一块减少 服务器请求
32. 找出如下代码中的错误
    ```
    <style>
      div::after：hover {
        opacity: 85%；
        transition: opactiy .3s step(5,end);
      }
      a:visited {
        font-size: 28px;
      }
    </style>
    <div>
      <a href="jd.com”>京东商场<a>
      <a href="mi.com”>小米网<a>
    </div>
    ```
    伪元素 只能在最尾部\透明度是0~1之间\ stps\a 没有闭合\visited 只能改变颜色    \ 引号

33. 如下内容渲染在【同一行】中，请计算那一行的理论行高
    ```html
    <!DOCTYPE html>
    <html>
    <head>
      <meta charset="utf-8">
      <meta name="viewport" content="width=device-width">
      <title>JS Bin</title>
      <style>
        div {
          margin: 80px;
          background-color: violet;
        }
        span {
          display: inline-block;
          border: 1px dotted;
          background-color: pink;
        }

        .a {
          vertical-align: -15px;
          width: 30px;
          height: 30px;
        }
        .b {
          margin-top: -50px;
          width: 30px;
          height: 30px;
          vertical-align: top;
        }
        .c {
          margin-bottom: 10px;
          vertical-align: middle;
        }
        .d {
          width: 30px;
          height: 30px;
        }
      </style>
    </head>
    <body>
      <div>
        x<span class="a">foo</span>
        <span class="b">bar</span>
        <span class="c">baz</span>
        <span class="d"></span>
      </div>
    </body>
    </html>
    ```
     有内容最后一行内容
     
     无内容

34. `vertical-align` 取值为 `baseline` 时在不同情况下分别是如何对齐的？


35. 解释常规流与包含块的概念

   常规流可以和外界接触 ,包含块不可以
     如果一个元素没有定位 没有浮动 就是常规流
     从上到下,从左到右,不会重叠,
36. 在各种情况下，一个元素的包含块分别是什么？

      
37. 默写与背景相关的属性并说明每个属性的作用和会产生的效果

     background-size: 图片大小
     background-image:url 图片地址
     background-position:图片位置
     background-color:颜色
     background-repeat: 平铺
     background-origin: 图片相对位置, content-box/padding-box/border-box
     background-clip: 剪切 ,content-box/padding-box/border-box
     background-attachment:scroll 滚动 / fixed固定
     
38. 如何实现单方向的盒子阴影？
    box-shadow
      模糊,会大于面积
       扩散半径为负会向内
  
39. 默写与表格布局相关的 CSS 属性，并说明相关属性的作用
		
    
40. `visibility:hidden`，`display:none`，`opacity:0`分别有什么不同？
   visibility 还占用空间
   display    不占用空间
    opacity     占用空间

41. 当页面中出现表示时间的文字但表意不明确时，比较优雅且富有语义的做法是什么？
   
  
42. CSS 中一般为何不使用 `cm`，`mm` 等长度单位？

     what
43. 表格布局中各层的层次是？
      从上往下 
      单元格, 行,行 组,
     
44. 为什么要在文件的最后一行加一个回车？
       便于后续编辑
       文件在拼接时更可能不出错
       diff 信息中不会有额外信息
   
45. 用 CSS 画出一个半圆形，分别给出实心与空心的的画法。实心和空心分别给出两种方案。
       
    
46. 表单元素有哪些伪类选择器？
    :enabled 启用状态
    :disabled 禁用
    ;checked  被选中的
    :default  默认
    :valid 有效选择 input
    :invalid  无效 input
    :required  有 required
    :optional 无 required
    :

47. 如何禁用 textarea 元素默认的可缩放行为？
     resize 属性
         none 禁止
         both  上下左右
         horizontal  左右
         vertical  上下

48. reset与normalize分别是什么，区别是什么，何种场景会使用到？

     reset 浏览器自带,不同的浏览器效果会不同
     normalize.css 标准化,跨浏览器的高度一致性
     https://www.jianshu.com/p/d8f96c28c932
49. 表布局中边框合并的原则是什么？
     border-collapse /separate 独立 /collapse 合并/
     empty-cells  show 显示  hide 不显示
     table- layout fixed内容过长 不拉伸 , auto 拉伸
     border-spancing 间距
     
     

50. 如何让背景图片从元素的左下角向上偏移5像素，往右偏移3像素；图片不重复平铺？写出代码。

    background-repeat:no-repeat;
    background-position-bottom:5px;
    background-position-left:3px;
    background-position:3px calc(100%-5px)                    
51. 写出创建如下目录结果的命令行脚本（注：有扩展名的为文件，没有扩展名的为文件夹）。
    ```
    a
    │  readme.md
    │
    ├─foo
    │  └─c
    └─bar
        │  a.txt
        │  b.txt
        │
        └─y
                a.js
    ```

52. 中英互翻

    omit，multiple，驼峰式，中划线式，layout，typo，code review，半径，config，集合，矩形，binary，decimal，十六进制，八进制，SEO，HTML实体，语义化，兼容性，quirk，reference，大小写敏感，别名
    省略  多重  CamelCase     布局  排版 代码  复习  radius 系统配置 gather 
    rectangle  二进制  十进制  hexadecimal  octonary 搜索引擎优化 compatibility  参考  case sensitive  alias
    
    