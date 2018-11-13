# HTML 复习
- 文档结构
```<!doctype>
    <html>
        <head>
            <meat charset="utf-8">
           <title>头</title>
           <!--  -->
        </head>
        <body>
        <a herf="www.baidu.com" target="_blank">a链接</a>
        </body>
        </html> 
```
- 元素分为 
  - 单标签和双标签
    - meta img
    - a p
  - 文本元素
    - b 加粗
    - strong 加粗强调
    - br 换行
    - wbr 安全换行 用在英文中
    - i  倾斜
    - em 倾斜加强
    -  s del 删除线
    - u ins xia 划线
    - small 小号字
    - sub 和 sup 上移动和下移
    
    > ```<code>HTML5</code>
     >   <var>HTML5</var>
      >  <samp>HTML5</samp>
       > <kdb>HTML5</kdb>
      解释:`<code>`表示计算机代码片段;`<var>`表示编程语言中的变量;`<samp>`表示程序或计算机的输出;`<kdb>`表示用户的输入。由于这属于英文范畴的，必须将 lang="en"英语 才能体现效果。 

>  `<ruby>`语言元素
    >>```
    > ><ruby> 
    > >饕<rp>(></rp><rt>tāo</rt><rp>)</rp>
    >>餮<rp>(</rp><rt>tiè</rt><rp>)</rp> </ruby>

- `<mark>HTML5</mark>`
  -<mark>HTML5</mark>`<mark>`突出显示文本
-  `<time>`表示日期和时间
   - `<time>2015-10-10</time>`
   - <time>2015-10-10</time>

- a 元素
  > 1. href属性
  > 2. target="_blank" )(_parent/_self/_top 在 iframe 中用,)
- 绝对与相对
  `<a href="file:///D:/备课/HTML5 第一季/code/index2.html">index2</a>`
  > 如果对应文件夹地址变了则地址失效

  `<a href="index2.html">index2</a>`
  > 相对没影响  
  > 同一个目录:index2.html 或./index2.html;  
  > 在子目录:xxx/index2.html;  
  > 在孙子目录:xxx/xxx/index2.html;  
  > 在父目录:../index2.html;  
   在爷爷目录:../../index2.html;

- 锚点链接
 ```//链接
<a href="#1">第一章</a> <a href="#2">第二章</a> <a href="#3">第三章</a> //锚点
<a name="1"></a> <a id="3"></a>
```
 - name 和 id 都可用



#### 分组元素
  - p
  - div
    - 和`<p>`段落的区别就是，两 段文本的上下空隙是没有的，空隙间隔和<br>换行一样。
- `<blockquote>`元素实际作用除了和`<p>`元素一样，有段落空隙的功能，还包含
了首尾缩进的功能。语义上表示，大段的引用他出的内容。
- `<pre>`展现格式化内容 
- `<hr>`
- `<ul><li>添加无序列表`
- `<ol><li>`添加有序列表
   - 属性`start:从第几个序列开始统计:<ol start="2">`
  - reversed  是否倒序排列
  - type :值分别为:1、a、A、i、I
  - li 的属性 value 强制是某个编号
- dl dt dd 说明列表
- figure figcaption
```figure>
<figcaption>这是一张图</figcaption>
    <img src="img.png">
</figure>
```
#### 表格
- table tr th td
##### 元素
- 简易表格

    ```
    <table border=1 style="width:300px;">
        <th><td>标题</td></th>
        <tr> <td>中</td> </tr>
    </table>
    *表格默认没边框要加 border*
  *th 字体默认居中加粗* 
  *style 是 css*
    ```
 ```
 <thead>
    <tr> <th>姓名</th>
    <th>性别</th>
    <th>婚姻</th> </tr>
</thead>
```   
  

- `<tfoot>`添加表脚
- `<tbody>` 表体
   **表意有助于 javascript css 控制**
- caption 标题
```
 - <colgroup>设置列
    <colgroup span="2" style="background:red;"> 
    解释:<colgroup>元素是为了处理某个列，span 属性定义处理哪些列。
    1 表示第一列，
    2 表示前两列。如果要单独设置第二列，那么需要声明两个，先处理第一个，将列点移入第 二位，再处理第二个即可。
 - <col>更灵活的设置列 <colgroup>
    <col>
    <col style="background:red;" span="1"> </colgroup>
解释:<col>元素表示单独一列，一个表示一列，控制更加灵活。如果设置了 span 则， 控制多列。
```   
#### 文档元素总汇
- header 首部
- footer 尾部
- h1~h6
- hgroup
  - 组合标题,当表头和表尾同时出现h1h4的标签,但是样式不同,则需要通过组合来区分.
- section 主题内容
- nav 导航
- article添加一个独立成篇的文档,里面可以包涵以上标签,
- aside 如博客的侧栏
- address>表示文档或 article 元素的联系信息
- details  不支持
#### 嵌入元素
- img
  - src 
  - alt 图片识别显示文字
  - width/height
  - ismap 服务器相应
  - usemap 关联 map
- iframe 在一个框里嵌入另一个网页 一个框里切换百度和360搜索
```
      <a href="www.baidu.com" target="in
      ">baidu</a>
      <a  href="www.360.com" target
      ="in">baidu</a>
  <iframe src="www.qq.com"name="in" width="300" height="300"></iframe>
  ```
- embed 嵌入插件
  - embed [src type] 
- progress [value ,max]进度条
*******
```<meter>显示范围里的值
<meter value="90" min="10" max="100" low="40" high="80" optimum="60"></meter>
``` 
> 解释:`<meter>`元素显示某个范围内的值。其下的属性包含:min 和 max 表示范围边界， low 表示小于它的值过低，high 表示大于它的值过高，optimum 表示最佳值，但不出现效 果。IE 浏览器不支持此元素。

#### 音频和视频
- `<video src="test.webm" width="800" height="600"></video>`
  - autoplay自动开始播放  
  - controls 显示播放控件(不加该属性显示第一针)
  - loop 循环 /muted 静音
  - poster ="img.png" 封面
  - preload 预加载 有3个值
    - none 不加载封面是灰色/ metadate 显示第一针/ auto尽快下载默认值
- audio 音频
  - 同 video 一样/
  - src autoplay preload controls
#### 表单
- form
  - action 提交的页面
  - method 请求方式(post/get 默认)
  - enctype 上传服务器 
    - application/x-www-form-urlencoded(默认编码， 不能将文件上传到服务器)
    - multipart/form-data(用 于上传文件到服务器)
    - name 程序员调试用不提交
    - target 
    - autocomplete 记住用户的数据
    - novalidate 有效性检查
- input
  - autofocus 光标焦距
  - disabled 禁用
  - autocomplete 提示数据(on/off)
    - form默认提示,单独在 input 中设置
  - form  让表单外的 input 与 form 挂钩
    - `form`  di=register   /form
    - input form=register这就是挂钩
   - name 提交时用
   - value 是用户输入的值也要提交
- label
  1. 点击文字也可选择
  2. 可以在 label 外关联
      - label for=123;input id=123
  3. 翻遍 css 调用
- fieldset,多个表单分为一组便于管理
  - 属性: name/form 挂钩/ disabled 禁用
- legend 分组说明,在 fieldset中
- button
  - submit 默认
  - reset 重置
  - button  没有任何作用配合 js 用
  **当 button 的属性值为 submit 时会有额外的属性**
   ` <button type="submit" formaction="http://www.sogou.com">提交</button `

   |属性名|说明|
   |-----|--:|
   |form| 对应|
   |formaction|action|
   |formenctype|enctype|
   |formmethod|method|
   |formtarget|target|
   |formnovalidate|formnovalidate|
   `<button type="submit" form="register">提交</button>`
#### type 中汇
- text

|名称|说明|
|--|--:|
|maxlength|设置文本框最大字符长度|
|size|设置文本框宽度|
|value|设置文本框初始值|
|required|必须输入一个值|
|readonly|文本框处于只读状态|
|disabled|禁用状态,表单不会提交看地址栏没有后缀|
|placeholder|输入字符的提示灰色字体|
|list| datalist 元素|
|pattern|正则表达|
   **list用法**
   ```
   <input list="footlist">
<datalist id="footlist">
<option value="苹果">苹果</option> <option value="桔子">桔子</option> <option value="香蕉" label="香蕉"> <option value="梨子">
</datalist>
```
- password

|名称|说明|
|--|--:|
|maxlength|设置文本框最大字符长度|
|size|设置文本框宽度|
|value|设置文本框初始值|
|required|必须输入一个值|
|readonly|文本框处于只读状态|
|disabled|禁用状态,表单不会提交看地址栏没有后缀|
|placeholder|输入字符的提示灰色字体|


- search
  - 文本框里输入文字后个错号取消键
-	number、range(范围滑动横杠上的圈) 时

|名称|说明|
|--|--:|
|max|最大值|
|min|最小值|
|value|设置文本框初始值|
|required|必须输入一个值|
|readonly|文本框处于只读状态|
|value|初始|
|list|输入字符的提示灰色字体|
- type 为 date 系列时
```
<input type="date">
<input type="month">
<input type="time">
<input type="week">
<input type="datetime">
<input type="datetime-local">
```
- type 为 color 时,
`<input type="color" name="color">`
- type 为 checkbox、radio 时
```
  音乐 <input type="checkbox"> 体育 <input type="checkbox">
<input type="radio" name="sex" value="男">男
<input type="radio" name="sex" value="女">女
```
|名称|说明|
|--|--:|
|checked|复选框、单选框是否为勾选状态|
|required|必须勾选|
|value|设置文本框初始值默认为 on|
- type 为 submit、reset 和 button 时
  - 与 button 标签一样,submit 时，还提供了和`<button>`元素一样的额外属性:formaction、 formenctype、formmethod、formtarget 和 formnovalidate。
- type 为 image 

  - `<input type="image" src="img.png">`
  - src/alt/width/height
  - formaction、formenctype、formmethod、formtarget 和 formnovalidate。
- 为 hidden 隐藏
- file
  - accept,MIME 类型
  - required
  - accept="image/gif, image/jpeg, image/png"
- select 下拉列表

 ``` <select name="fruit">
<option value="1">苹果</option> <option value="2">橘子</option> <option value="3">香蕉</option>
</select>
  ```
|名称|说明|
|-|-|
|name|设定提交时的名称|
|disabled|将下拉列表禁用|
|form|将表单外的下拉列表与某个表单挂钩|
|size|设置下拉列表的高度|
|multiple|设置是否可以多选|
autofocus|获取焦点
required|必须选择
```
//默认首选
<option value="2" selected>橘子</option>
```
```
optgroup 进行分组，label 为分组名称，disabled 可以禁用分组 <optgroup label="水果类">
<option value="1">苹果</option>
<option value="2" selected>橘子</option> <option value="3" label="香蕉">香蕉</option>
</optgroup>
```
- textarea 多行文本框

|名称|说明|
|--|--:|
|name|设定提交时的名称|
|form|将表单外的多行文本框与某个表单挂钩|
|readonly|设置多行文本框只读|
|disabled|将多行文本框禁用|
|maxlength|设置最大可输入的字符长度|
|autofocus|获取焦点|
|placeholder|设置输入时的提示信息|
|rows|设置行数|
|cols|设置列数|
|wrap|设置是否插入换行符，有 soft 和 |hard 两种
required|设置必须输入值，否则无法通过验|证|
#### 全局属性和其他
- meta
```
<meta name="author" content="bnbbs">
<meta name="description" content="这是一个 HTML5 页面"> 
<meta name="keywords" content="html5,css3,响应式">
 <meta name="generator" content="sublime text 3">
```
- id(唯一)  class(多个) 
- dir =rtl 文字方向
- hidden 隐藏
- lang 语言
- title 文字提示
- style 样式