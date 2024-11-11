[TOC]

## HTML+CSS+JS第三阶段学习

### HTML

基本框架：

```html
<!DOCTYPE html><!--相当于头文件-->
<html lang="zh-CN"><!--网站默认语言-->
    <head>
        <meta charset="UTF-8"/> <!-- 注释：为了告诉浏览器（解码地）的解码方式 -->
        <title>标签</title> <!-- 打开的网页的名字 -->
    </head>
    <body>
        <marquee><!--编辑内容,而且会滚动-->
            张若晨是个大美女          
        </marquee>
        <input type="text"><!--网页输入框-->      
    </body>
</html> 
```

#### HTML标签

> 常用标签：
>
> - \<h1>,\<h2>…表示标签级数，共六级标签(==联想==：Markdown标签)
>
> - \<hr>添加水平线
>
> - \<p>表示段落，两个P之间会有一段空行
>
> - \<br>表示折行，可以在P内使用，出现br就会直接换到下一行
>
> - \<div>被调用的时候相当于换行（两行之间没有空隙）
>
> - 图片标签+超链接
>
>   - \<a href=“网址” target=“_blank”>网址名字</a>:==跳转链接==格式，引号里面加上网址，后面的target代表跳转链接的时候会开一个新的网页面，后面则代表着你给这个链接取得名字
>
>   - <img scr=“图片地址”,alt=“你取的名字”>scr是指向图片的地址，alt是你给这个照片链接取得名字
>
>     ==注意==：上方的图片地址也可以是本地的路径
>
>     - 综合上方两点可以写出带有图片标签的网址：
>
>       ```html
>       <a href=“网址”>
>       <img scr=“图片网址” alt=“图片名字”>
>       <a>
>       ```
>
>   - 跳转锚点
>
>     ```html
>     <a href=“#名字”>跳转到某处</a>
>     ```
>
>     上方是点击可以跳转，下方是跳转的位置
>
>     ```html
>     <a name=“名字”></a>
>     <img scr=“名字后面附带的网址” alt=“网址名字”>
>     ```
>
>   ​       扩展：跳转到页面最顶部：\<a href=“#”>回到顶部<\a>
>
>   ​		   刷新页面：\<a href=“ ”>刷新页面</a>
>
>   ​		   弹出弹窗：\<a href=“javascript:alert(你按这个的时候弹出的内		    容)；”点我弹窗<\a>
>
>   + 唤起指定应用：
>
>     + \<a href=“tel:19965827801”>拨打电话<\a>
>     + \<a href=“mailto:zhang20050507@qq.com”>邮件联系</a>
>     + \<a href="sms:10086">短信联系</a>
>
>   + ```html
>     <o1>或者是<u1>//区别就是u1会往后一个tap
>     <li>内容1<\li>
>     <li>
>         <span>内容2</span>
>         <u1>
>             <li>内容2包括的小内容</li>
>         </u1>
>     <\li>
>     <\o1>或者是<u1>
>     
>     <d1>//没有那个小点
>     	<dt>内容1</dt>
>         <dd>内容1下一行，但是会往后一个Tap</dd>
>     </d1>
>     ```
>
> - \<button class="favorite styled" type="button">Add to favorites</button>：这个代码会在网页中显示出一个按钮，但是按钮的关联属性要具体定义
>

#### 块级元素和行级元素

> 块级元素：能够造成块级布局，在该布局中，从包含块的顶部开始，里面的盒子都是一个接一个垂直放置的，每个盒子的左外边缘初级包含快的左边缘，块级元素总是开始在新的行或列上，每个块元素会单独占一行例如\<p>生成段落
>
> 行级元素：造成行内布局，在该布局中，写着写着就可以使用一个行级元素，并且不会对行间布局造成任何改变，多个行内元素会共用一行比如:\<span class=“highlight”>内容<\span>只是把这里面包含的内容打上了高光

#### HTML标签样式

> style属性：
>
> - 背景颜色：\<body style=“background-color:yellow”>
>
>   ​		  \<h2 style="background-color:red">h2内容<\h2>
>
>   ​		   \<p style="background-color:green">p段落内容</p>
>
>   ​		    </body>
>
> - 字体、颜色和尺寸：\<p style=“font-family:varial;color:red;font-size:20px;”>从左到右分别定义了字体系列、颜色还有字体尺寸
>
> - 文本对齐方式：\<p style=“text-align:center”>内容</p>

### CSS

> - 一种样式表语言，选择性的为HTML元素添加样式
>
> - 分为三类
>
>   - 内联式：在标签内部即可使用
>
>     ```html
>     <p style="color:red;font-size=20px">
>     </p>
>     ```
>
>   - 嵌入式:写在\<style></style>之中，并且放在\<head></head>内
>
>     ```html
>     <head>
>         <style>
>             p{
>     			color:red;
>             	font-size:20px;
>             }
>         </style>
>     </head>
>     ```
>
>   - 外部式:写在外部.css文件中
>
>     下方例子中：href里面写.css的文件路径，可以是绝对路径或者相对路径，相对路径类似于：../../css/index.css，而绝对路径类似于：/css/index.css
>
>     ```html
>     <link rel="stylesheet" type="text/css" href="css/index.css">
>     ```
>
> ==注意==：嵌入式和外部式需要用到选择器

#### CSS的作用

> 用于给文档添加样式——>改变文本特性/创建文档布局/做一些特效(动画)

#### CSS选择器

> CSS选择器用于选择你想要的元素样式的模式

> - 通用选择器
>
>   - 页面内的所有元素内容style都会改变
>   - 使用方法
>     - *{ }
>
> - 元素选择器
>
>   - 使用方法：通过元素名称选择HTML元素
>
>     例如下面就代表着所有的p元素里面的内容都会变成红色
>
>     ```html
>     p{
>     	color:blue;
>     }
>     ```
>
> - 类选择器
>   - 使用方法
>     - 先在标签里面使用类标记某处文档：class=“myClass”
>     - 然后这个类对应的选择器格式就是.myClass{ }
>
> - ID选择器
>   - 使用方法
>     - 先在标签内用ID标记某处文档，类似:id=“myId”
>     - 然后这个ID对应的选择器的格式就是#myId{ }

#### 使用CSS设置元素的基础样式

> - 文本颜色的设置
>   - 直接写出颜色的英文即可
>   - 设置三原色的比例：rgh(30，120，200)
> - 字体的设置(font-family)
>   - 常见字体
>     - serif(衬线字体族):New Roman\MS Georgia\宋体….
>     - sans-serif(无衬线字体族)：MS Trebuchet\幼圆\隶书\楷体…
>     - cursive:(手写体族 楷体)Caflisch Script\迷你简黄草\华文行草……
>     - monospace：(等宽字体族 )Courier\MS Courier New\Prestige……
>     - fantasy：(梦幻字体族)WingDings\ 3Symbol…
> - 大小的设置
>   - font-size
>     - 常用单位：px\em\rem…
>     - 可以设置小数，但是一般不设置奇数
>   - 宽度(width)/高度(height)
>   - 四个边距:p{ *margin*:2cm 4cm 3cm 4cm;} 
> - 字体风格(font-style)
>   - 斜体:\<dfn>,\<i>,\<address>,<em>
>   - 加粗：\<b>,\<strong>
>   - 上/下脚注：\<sup>，\<sub>
>   - 小体：\<code>,<samp>,\<kbd>
>   - 小体+斜体：\<var>

#### CSS重要的属性之display

> 由于不同的 HTML 元素，其默认的展示形式是不同的。例如 p 元素（段落）的 display 属性默认值是 block，而 a 属性（链接）的 display 属性默认值则是 inine。所以我们就可以使用display来更改展示形式。

> 就像 display 的名字一样，其用来定义元素块的展示形式，不同的展示形式会有不同的展示效果。

>  display 属性的常用属性有：
>
> - inline：表示元素是行内元素，多个元素会共用一行。
> - inline-block：表示元素是行内块元素，多个元素会共用一行。与 inline 的区别是，==inline-block 元素可以设置元素的长和宽==，但是 inline 元素不可以设置元素的长和宽。
> - block：表示元素是块元素，每个块元素会单独占用一行。
>
> 举例：
>
> - ```html
>   <body>
>     <p class="display">段落1</p>
>     <p class="display">段落2</p>
>     <p class="display">段落3</p>
>   </body>
>   ```
>
> - 设置的 CSS 属性如下所示：
>
> ```css
> .display {
>   background-color: red;
> }
> ```
>
> 显示效果如下图所示，每个段落占据一行
>
> ![-w524](https://shuyi-tech-blog.oss-cn-shenzhen.aliyuncs.com/halo_blog_system_file/16948334993245.jpg)
>
> - 如果我们把 p 元素设置成 inline 显示形式，那么它们就会多个元素排列在一行内。如下图所示。
>
> ```css
> .display {
>   display: inline;
>   background-color: red;
>   /* width/height 属性设置无效 */
>   width: 200px;
>   height: 200px;
> }
> ```
>
> ![-w228](https://shuyi-tech-blog.oss-cn-shenzhen.aliyuncs.com/halo_blog_system_file/16948336423899.jpg)
>
> - 如果我们把 p 元素设置成 inline-block 显示形式，并且设置了宽高，那么它们就会多个元素排列在一行内，并且宽高设置会生效,如下图所示。
>
> ```css
> .display {
>   display: inline-block;
>   background-color: red;
>   /* width/height 属性设置无效 */
>   width: 200px;
>   height: 200px;
> }
> ```
>
> ![-w639](https://shuyi-tech-blog.oss-cn-shenzhen.aliyuncs.com/halo_blog_system_file/16948337786196.jpg)
>

#### CSS的float类型

> 相当于diaplay的inline-block属性，向左浮动之后三个块块就可以在一行

```html
.display {  
	display: block;  
	float: left;  
	width: 200px;  
	height: 100px;  
	background-color: red;
}
```

#### CSS的盒模型

> 在CSS中所有的元素都被一个个的“盒子”包裹着

> ![CSS box-model](https://www.runoob.com/images/box-model.gif)
>
> - 盒子类型：
>   - 外部显示
>     - block外部显示
>       - 盒子会换行
>       - width和height属性可以发挥作用
>       - 内边距/外边距/边框会将其他元素从当前盒子周围“推开”
>       - 如果未指定width，放款将沿着行向扩展去填充容器中的可用空间
>     - inline外部显示
>       - 盒子不会产生换行。
>       - width 和 height属性将不起作用。
>       - 垂直方向的内边距、外边距以及边框会被应用但是不会把其他处于 inline状态的盒子推开。
>       - 水平方向的内边距、外边距以及边框会被应用且会把其他处于 `inline` 状态的盒子推开。
>   - 内部显示类型
>     - 一般会使用dispaly:flex等

#### CSS的5种position定位

> position:指定了元素的定位类型
>
> - static(HTML的默认值，也就是没有定位)
>
>   - 静态定位的元素不会受到top/buttom/left/right
>
>   - 实例格式：(下面四种也是这个格式，就不再示范了)
>
>      在\<head>内，\<style>里面使用
>
>     ```html
>     div.static {
>         position: static;
>         border: 3px solid #73AD21;
>     }
>     ```
>
>     下面的代码在\<body>里面
>
>     ```html
>     <div class="static">
>     该元素使用了 position: static;
>     </div>
>     ```
>
> - relative
>
>   - 相对定位元素的定位是相对其正常位置，可以选择进行移动
>
>   - h2.pos_left {
>
>     ​	position:relative;    
>
>     ​	left:-20px; 
>
>     }
>
>   - ==注意==：如果两个文本位置移到同一处就会重叠在一起
>
> - fixed==这个很好用的感脚==:heart:
>
>   - 元素的位置相对于浏览器窗口是固定位置,就是打开一个网页的时候，不管如何滚动这个页面，这个元素的位置都是相对于目前页面不变的
>
>   - p.pos_fixed {    
>
>     ​	position:fixed;    
>
>     ​	top:30px;    
>
>     ​	right:5px;
>
>      }
>
> - absolute
>
>   - 绝对定位的元素的位置相对于最近的已定位父元素，如果没有已经定位的父元素，那么他的位置就是相对于\<html>的
>
>     h2 {    
>
>     ​	position:absolute;    
>
>     ​	left:100px;   
>
>     ​	 top:150px;
>
>      }
>
>   - ==注意==：两个文本位置移到同一处就会重叠在一起
>
> - sticky
>
>   - 粘性定位的元素在用户滚动页面超过它之后，他也会跟着用户的界面动起来，超过它之后他就会在页面最上方
>
>     div.sticky {   
>
>      	position: -webkit-sticky; //这一行可以不写   	 position: sticky;    
>
>     ​	 top: 0;   
>
>     ​	 background-color: green;   
>
>      	border: 2px solid #4CAF50; 
>
>     }
>
> - 补充:出现重叠的元素的时候，可以设置谁在上方
>
>   - 比如说图片在下面，设置z-index为-1
>
>     img {   
>
>      	position:absolute;    
>
>     ​	 left:0px;    
>
>     ​	 top:0px;   
>
>      	z-index:-1; 
>
>     }

#### CSS常用布局

> ![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/8066949eac2e4187bfcbe982b0d02856~tplv-k3u1fbpfcp-zoom-in-crop-mark:1512:0:0:0.awebp?)
>
> - 单个模块布局
>
>   - 书写顺序
>     - 位置属性：position,top,right,z-index,display,float
>     - 大小:width,height,padding(用来控制内容周围区域边距),margin(用来设置外边距)
>     - 文本:font.line-height,letter-spacing,color-text-align
>     - 背景:background,border
>     - 其他:animation,transition
>
> - 水平垂直居中布局
>
>   - 行内元素
>     - 水平:text-align:center
>     - 垂直:height=line-height
>
> - 单列布局
>
>   - 普通布局:head+container+footer(三个宽一样)
>   - 内容居中:中间container宽度单独设置
>
> - 两栏布局：左盒子固定，右盒子自适应
>
>   - float类型
>     - 左盒子宽度确定,含有float:left属性，右盒子宽度(设置为100%)就自动填满页面
>   - flex类型
>     - 父元素diaplay:flex属性，子元素左盒子宽度自定，右盒子不用设置宽度，直接flex:1属性就自动填满
>
> - 三栏布局：左右盒子固定，中间自适应
>
>   ==注意==：中间盒子要放在文档流(body)最前面以保证优先加载
>
>   - flex类型
>
>     ```html
>     .box{
>         min-width: 800px;
>         height: 600px;
>         background: gray;
>         display: flex;
>     }//总盒子宽度确定
>     .left{
>         width:200px;
>         height: 600px;
>         background: pink;
>         order:-1
>     }//根据order确定左右中
>     .center{
>         height: 600px;
>         background: aquamarine;
>         width:100%;
>         flex:1
>         order:1
>     }
>     .right{
>         width:200px;
>         height: 600px;
>         background: skyblue;
>         order:2
>     }
>     ```
>
> - 等高布局(子元素等高)
>
> - 粘性布局
>
>   - 无论如何，footer会粘在main后面

#### CSS的伪类

> CSS伪类是用来添加一些选择器的特殊效果

> - 点击网页链接之前之后的一些颜色显示效果
>
>   - ```html
>     a:link {color:#FF0000;} /* 未访问的链接 */
>     a:visited {color:#00FF00;} /* 已访问的链接 */
>     a:hover {color:#FF00FF;} /* 鼠标划过链接 */必须在前两个之后
>     a:active {color:#0000FF;} /* 已选中的链接 */必须在上面那个之后
>     ```
>
>   - 配合CSS标签使用
>
>     - a.red:visited {color:#FF0000;}/在\<head>,\<style>里面
>     - \<a class="red" href="css-syntax.html">CSS 语法</a>/和上面对应的body里面的语句
>
> - 用来选择父元素的第一个子元素：first-child伪类
>
>   - 和body中任何一个含有p元素的元素里面的第一个p元素对应
>
>     p:first-child {
>
>     ​	color:blue;
>
>      }
>
>   - 和body中所有p元素的第一个i元素对应
>
>     p > i:first-child {    
>
>     ​	color:blue;
>
>      }
>
>   - 和body中作为第一个子元素的p元素里面所有的i元素对应
>
>     p:first-child i {    
>
>     ​	color:blue; 
>
>     }
>
> - lang伪类
>
>   - 在下面的例子中，:lang 类为属性值为 no 的q元素定义引号的类型：
>     - q:lang(no) {quotes: "~" "~";}//在\<head>里面
>     - \<p>Some text \<q lang="no">A quote in a paragraph</q> Some text.</p>//在body里面，这里呈现出来的效果就是q中间的内容会两侧会有波浪线

### JavaScript

> 放在body里面的\<script>标签里面编写

> 工作方式：先整体解析代码，获取所有被声明的变量，然后再一行一行的运行(变量提升)

#### JavaScript基本语法

> - 语句：var a=1+3;//输出结果就是1+3
>
>   ==注意==：多个语句可以写在一行里面
>
> - 标识符：Unicode(包括英文字母和其他语言的字母)/美元符号/下划线+Unicode(包括英文字母和其他语言的字母)/美元符号/下划线/0-9
>
>   ==注意==：中文是合法的表示符号，也可以作变量名
>
> - 注释
>
>   - 单行：//
>   - 多行：/* 内容*/
>
>   ==注意==：兼容HTML注释
>
> - 区块：{ }
>
> - 条件语句：if和switch
>
> - 循环语句：while和for和do…while和break/continue和lable(跳转到lable里面的语句位置)

#### JavaScript数据类型

> 拥有动态类型，相同变量可以作不同类型

> - 字符串(String）
>
>   - 是存储字符的变量，可以用单引号或者双引号
>
>   - ```html
>     <script>
>     var carname1="Volvo XC60";
>     var carname2='Volvo XC60';
>     var answer1='It\'s alright';
>     var answer2="He is called \"Johnny\"";
>     var answer3='He is called "Johnny"';
>     document.write(carname1 + "<br>")
>     document.write(carname2 + "<br>")
>     document.write(answer1 + "<br>")
>     document.write(answer2 + "<br>")
>     document.write(answer3 + "<br>")
>     </script>
>     ```
>
> - 数字(Number)
>
>   - 可以带小数点，也可以不带小数点
>
>   - ```html
>     <script>
>     var x1=34.00;
>     var x2=34;
>     var y=123e5;
>     var z=123e-5;
>     document.write(x1 + "<br>")//34
>     document.write(x2 + "<br>")//34
>     document.write(y + "<br>")//12300000
>     document.write(z + "<br>")//0.00123
>     <script>
>     ```
>
> - 布尔(Boolean)(逻辑)
>
>   - true或者flase
>
> - Null:清空变量
>
>   Undefined:这个值表示变量不含有值
>
>   - ```html
>     <script>
>     var person;
>     var car="Volvo";
>     document.write(person + "<br>");//输出undefined
>     document.write(car + "<br>");//输出Volvo
>     var car=null
>     document.write(car + "<br>");//输出null
>     </script>
>     ```
>
> - 对象(Object)
>
>   - ```html
>     <script>
>     var person=
>     {
>     	firstname : "John",
>     	lastname  : "Doe",
>     	id        :  5566
>     };
>     document.write(person.lastname + "<br>");//输出Doe
>     document.write(person["lastname"] + "<br>");//输出Doe
>     </script>
>     ```
>
> - 数组(Array)：三种形式
>
>   - ```html
>     var cars=new Array();
>     cars[0]="Saab";
>     cars[1]="Volvo";
>     cars[2]="BMW";
>     ```
>
>   - ```html
>     var cars=new Array("Saab","Volvo","BMW");
>     ```
>
>   - ```html
>     var cars=["Saab","Volvo","BMW"];
>     ```

## 三者之间的关系

> html定义网页的结构，css描述网页的样子，js则是用来链接html和后台服务器的桥梁

## 参考网站

- [菜鸟教程](https://www.runoob.com/)
- [MDN](https://developer.mozilla.org/zh-CN/)
- [W3school](https://www.w3school.com.cn/h.asp#google_vignette)
- [稀土掘金](https://juejin.cn/)
- [网到](https://wangdoc.com/)
