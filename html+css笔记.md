### font的复合属性
- 取值：font:style weight size family
- 省略要求：只能省略前两个，如果省略了就等于设定为默认值。
```css
	<style>
        h2 {
            font-family: '微软雅黑';
            font-size: 18px;
            /* 文子变细 */
            font-weight: 400;
            /* font-style: italic; */
        }
        
        p {
            /* font-family: 'Microsoft YaHei', Arial, Helvetica, sans-serif; */
            font-family: 'Times New Roman', Times, serif;
        }
        
        em {
            /* 倾斜的字体不倾斜 */
            font-style: normal;
        }
        
        .bold {
            /* font-weight: bold; */
            /* 700 后面不跟单位 等价bold 都是加粗 */
            font-weight: 700;
        }
    </style>
```
### 文本缩进
- 属性名：text-indent
- 取值：数字+px，数字+（2）em
```css
	<style>
        p {
            font-size: 24px;
            /* 文本的第一行首行缩进 多少距离  */
            /* text-indent: 20px; */
            /* 如果此时写了2em 则是缩进当前元素 2个文字大小的距离  */
            text-indent: 2em;
            line-height: 25px;
        }
        
        div {
            line-height: 26px;
        }
    </style>
```
### 文本水平对齐方式
- 属性名：text-align
- 取值：left左，center中，right右
### 文本修饰
- 属性名：text-decoration
- 取值：underline(下划线)，line-through（删除线）
### 行高
- 属性名：line-height
- 取值：数字+px,倍数：当前标签font-size的倍数 
### 复杂选择器
#### 后代选择器:空格
- 语法：选择器1 选择器2 {css}
```css
	<style>
        /* 我想要把ol里面的小li选出来改为pink */

        ol li {
            color: pink;
        }

        /* 中国 山东 济南 蓝翔 */
        ol li a {
            color: red;
        }

        .nav li a {
            color: yellow;
        }
    </style>
```
#### 子代选择器:>
- 语法：选择器1>选择器2{css}
- 只选择子代
```css
	<style>
        .nav>a {
            color: red;
        }
```
#### 并集选择器
- 语法：选择器1，选择器2{css}
```css
	<style>
        /* 要求1: 请把熊大和熊二改为粉色 */
        /* div,
        p {
            color: pink;
        } */

        /* 要求2: 请把熊大和熊二改为粉色 还有 小猪一家改为粉色 */
        div,
        p,
        .pig li {
            color: pink;
        }

        /* 约定的语法规范,我们并集选择器喜欢竖着写 */
        /* 一定要注意,最后一个选择器 不需要加逗号 */
    </style>
```
#### 交集选择器  
- 语法：选择器1.选择器2{css}
```css
	<style>
        /* p {
            color: red;
        } */
        /* .box {
            color: red;
        } */
        /* 交集选择器 */
        
        p.box {
            color: red;
        }
    </style>
```
#### 伪类选择器
- 作用：选中鼠标悬停在元素中的状态，设置样式
- 语法：选择器:hover{css}
```css
	<style>
        body {
            color: red;

        }

        a {
            color: #333;
            text-decoration: none;
        }

        a:hover {
            color: #369;
            text-decoration: underline;
        }
    </style>
```
### 背景相关属性
#### 背景平铺
- 属性名：background-repeat(bgr)
- no-repeat(不平铺),repeat-x(顺着x平铺),repeat-y(顺者y平铺)
```css
	<style>
        div {
            width: 800px;
            height: 800px;
            background-color: rgb(26, 165, 165);
            margin: 0 auto;
            background-image: url(./back.jpg);
            background-repeat: repeat-x;
        }
    </style>
```
#### 背景位置
- 属性名：background-position(bgp)
- 属性值:background-position:水平位置 垂直
- 背景色和背景图只显示在盒子里，外面的不显示
- 水平方向：left,center,right
- 垂直方向：top,center,bottom
```css
	<style>
        div {
            width: 800px;
            height: 800px;
            background-color: rgb(26, 165, 165);
            margin: 0 auto;
            background-image: url(./back.jpg);
            background-repeat: no-repeat;
            /* background-position: center center; */
            background-position: center;
            /* 背景中的复合属性写法 */
        }
    </style>
```
#### 背景相关属性连写
- 属性名：background(bg)
- 书写顺序：background:color image repeat positior
- 背景图位置如果是英文单词可以跌倒顺序，如果都用像素就不可以跌倒顺序
```css
	<style>
        div {
            width: 800px;
            height: 800px;
            /* background: pink url(./back.jpg) no-repeat center bottom; */
            /* 测试背景是数值 水平50px 垂直100px*/
            background: pink url(./back.jpg) no-repeat 100px 50px;
        }
    </style>
```
#### img和背景图片的区别
- img是一个标签(插入图)实现重要的图片
- background(背景图)

### 元素的显示模式(<>)
#### 块级
- 特点:独占一行
- 宽度默认是父元素宽度,高度默认由内容撑开
- 可以设置宽高
- 代表标签:div,p,h系列,ul.li,di.dt,dd,form,header
```css
	<style>
        div {
            width: 300px;
            height: 300px;
            background-color: pink;
        }
    </style>
```
#### 行内
- 特点:一行显示多个
- 宽度个高度默认由内容撑开
- 不可以设置宽高
- 代表标签:a,span,b,u,i,s,strong,ins.em,del...
```css
	<style>
        span {
            width: 300px;
            height: 300px;
            background-color: pink;
        }
    </style>
```
#### 行内块
- 特点:一行显示多个
- 可以设置宽高
- 代表标签:input,textarea,button,select.....
```css
	<style>
        img {
            width: 100px;
            height: 100px;
        }
    </style>
```
#### 转换
- 语法：display:block（块级）/display:inline-biock(行内块)/display:inline
#### html嵌套注意点
- 块级元素作为大容器，可以嵌套：文本，块级元素，行内块元素
- a标签不能嵌套自己，其他标签都可以嵌套
### Css特性
#### 继承性
- 特性：文字控制属性都可以继承（子承父业）
- 注意：继承性特点就是（子有特性，就显示自己的特性，否则就继承父特性 ）
#### 层叠性
- 给同一个标签设置相同的样式，写在最后的样式会生效
- 给补同的标签设置不同的样式，会共同作用在标签上
- 当样式冲突时，只有当选择器优先级相同时才能通过对叠加判断 结果
#### 优先级
- 特性：不同选择器具有不同的优先级，优先级高的样式会覆盖优先级低的样式
- 公式：继承《通配符《标签《类《id《行内《！important
- 注意：！important写在属性的后面，分号的前面！它不能提高继承的优先级，只要是继承优先级最低！，实际开发中不建议使用!important(谁更精准选到标签，谁的优先级高，谁的范围越广，谁的优先级越低)
#### 权重叠加计算
- 场景：如果是复合选择器，此时需要通过权重叠加计算方法，判断最终哪个选择器优先级最高会生效。
- 权重叠加计算公式：（每一级不存在进位）
- （0行内样式个数，0id选择器个数，0类选择器个数，0标签选择器个数）
- 比较规则：先比较第一级，比较出来统统不看，如果最终所有数字都相同，则比较层叠性（谁写在下面，谁说了算！）
### 盒子模型
- 概念：页面中的每一个标签都可以看作盒子，通过盒子的视角更方便进行布局
- 浏览器在渲染网页时，会将网页中的元素看作是一个个的矩形区域，我们也形象的称之为盒子
- css中规定每个盒子分别由：内容区域（ ），内边距区域（），边框区域（），外边距区域（）构成，这就是盒子模型。
#### 宽高
- width,heigth
#### 边框（border）-连写形式
- 属性名：border
- 属性值：单个取值的连写，取值之间用空格隔开
- border 10px soild red;（不分先后顺序）
- 快捷键：bd+tab
- solid 实线，dashed虚线，dotted点线
- 单方向设置：属性名border-方位名词（中间不能有空格）left,right,top,bottom
#### 内边距
- 一个padding可以添加四个方向的内边距
- padding属性可以当作符合属性使用，表示单独设置某个方向的内边距（给了四个值，顺序顺时针，上，右，下，左）
- 三个值：padding:10px 40px 80px (第一个值是左边的，第二个值是左右，第三个值是下)
- 两个值：padding:10px 80px(第一个值是上下，第二个值是左右）)
- 总结：多值写法，永远都是从上面顺时针转一圈，如果没有就看对面
#### css盒模型（自动内减）
- 手动：自己计算多余大小
- 自动：个盒子设置box-sixing:border-box；即可
#### 外边距
- 设置方式和padding一样
- 位置在最外边
##### 外边距折叠现象（1.合并现象）
- 场景：垂直布局的块级元素 上下的margin会合并
- 结果：最终两者距离为margin的最大值
- 解决办法：避免就好
- 只给其中一个盒子设置Margin就可以 
```css
	<style>
        div {
            width: 100px;
            height: 100px;
            background-color: pink;
        }
        
        .one {
            margin-bottom: 60px;
        }
        
        .two {
            margin-top: 50px;
        }
    </style>
```
##### 外边距折叠现象（2.塌陷现象）
- 场景：互相嵌套的块级元素，子元素的margon-top会作用在父元素上
- 结果：导致父元素一起往下移动
- 解决办法：
	1.给父元素设置border-top或者padding-top
	2.给夫元素设置overflow:hidden
	3.转换成行内块元素
	4.设置浮动
```css
 .father {
            width: 300px;
            height: 300px;
            background-color: pink;
            /* 设计稿没有border就不能用 */
            /* border: 1px solid #000; */
            /* 最完美方法 */
            /* overflow: hidden; */ 
        }
```
##### 行内元素的垂直内外边距
-注意：
	1.如果想要通过margin或者padding改变行内标签的垂直位置，无法生效
	2.行内标签的margin-top和bottom不生效
	3.行内标签的padding-top和bottom不生效

```css
 span {
            /* margin: 100px; */
            /* padding: 100px; */
            line-height: 100px;
        }
```
#### 清除默认的内外边距
- 通配符 {margin:0; padding:0}
#### 版心居中
- 版心：网页的有效内容
### 去掉列表的小点点
- list-style:none

### 结构伪类选择器
- 目标：能够使用结构伪类选择器在html中定位
- 作用与优势：
	1. 作用：根据在html中的结构关系查找元素
	2. 优势：减少html中类的依赖（保持洁净）
- 选择器：
	1.li:first-child（选中第一个）
	2.li:last-child（选中最后一个）
	3.li:nth-child(x)（任意一个）
	4.li:nth-last-child(x)(倒数第xx个)
```css
 /* 选中第一个 */
        /* li:first-child {
            background-color: green;
        } */
        /* 选中最后一个 */
        
        li:last-child {
            background-color: pink;
        }
        /* 任意一个 */
        
        li:nth-child(4) {
            background-color: blue;
        }
        /* 倒数第xx个 */
        
        li:nth-last-child(1) {
            background-color: red;
        }
        /* 去除列表前的小点点 */
        ul {
            list-style: none;
        }
```
### 结果伪类公式
- n的注意点
	1.n为：0，1，2，3...
	2.通过n可以组成常见公式
| 功能 | 公式|
|:-----:|:------:|
| 偶数|2n,even |
| 奇数|2n+1，2n-1,odd |
|找到前5个|-n+5 |
| 找到从第5个往后|n+5 |
```css
li:nth-child(2n+1) {
            background-color: pink;
            color: rgb(110, 13, 155);
        }
        
        li:nth-child(-n+3) {
            background-color: rgb(52, 23, 179);
            color: rgb(155, 13, 13);
        }
        
        li:nth-child(4n) {
            background-color: rgb(201, 204, 16);
            color: rgb(8, 1, 1);
        }
```
### 伪元素
- 伪元素：一般页面中的非主体内容可以使用伪元素（装饰性的）
- 区别：
	1.元素：html设置的标签
	2.伪元素：由css模拟出的标签效果
| 伪元素 | 作用|
|:-----:|:------:|
|::before|在父元素前添加伪元素 |
| ::after|在父元素后添加伪元素|
- 注意：
	1.必须设置content才能生效
	2.伪元素默认是行内元素
	3.伪元素是标签，可以设置颜色，背景等。。。
### 标准流
- 标准流又称文档流，是浏览器在渲染显示网页内容是默认采用的一套排版规则，规定了应该以何种方式排列元素。

### 浮动

作用：网页布局。
```css
<style>
        img {
            width: 100px;
            float: left;
        }
        
        div {
            width: 100px;
            height: 100px;
        }
        
        .one {
            background-color: pink;
            float: right;
        }
        
        .two {
            background-color: skyblue;
            /* float: right; */
            float: right;
        }
        /* 完美的在一行排 */
    </style>
```
#### 特点
1.浮动元素脱离标准流，在标准流中国不占位置
2.浮动元素比标准流高半个级别，可以覆盖标准流中的元素
3.浮动找浮动，下一个浮动元素会在上一个浮动元素后面左右浮动
4.浮动元素由特殊的显示效果
- 一行可以显示多个
- 可以设置宽高
- 居中和margin:0 auto无效
```css
<style>
        /*浮动： 一行可以显示多个,可以设置宽高，具备行内块的特点 */
        
        .one {
            width: 100px;
            height: 100px;
            background-color: pink;
            float: left;
            margin-top: 50px;
        }
        
        .two {
            width: 200px;
            height: 200px;
            background-color: skyblue;
            float: left;
            /* 因为浮动，不能生效，无法居中 */
            margin: 0 auto;
        }
        
        .three {
            width: 300px;
            height: 300px;
            background-color: red;
        }
    </style>
```
### css书写顺序：浏览器执行效率更高
1.放浮动或者display
2.盒子模型相关的属性：margin,border,padding
3.文字样式
```css
<style>
        * {
            margin: 0;
            padding: 0;
        }
        
        .top {
            height: 40px;
            background-color: #333;
        }
        
        .header {
            margin: 0 auto;
            width: 1220px;
            height: 100px;
            background-color: #ffc0cb;
            
        }
        
        .content {
            margin: 0 auto;
            width: 1220px;
            height: 460px;
            background-color: rgb(38, 173, 173);
            
        }
        
        .content .left {
            float: left;
            width: 234px;
            height: 460px;
            background-color: #ffa500;
        }
        
        .content .right {
            float: right;
            width: 986px;
            height: 460px;
            background-color: #87cdeb;
        }
    </style>
    
    
    <body>
    <div class="top"></div>
    <div class="header">头部</div>
    <div class="content">
        <div class="left">左</div>
        <div class="right">右</div>
    </div>
</body>

```
### 清除浮动
- 含义：清除浮动带来的影响
- 影响：如果子元素浮动了，此时子元素不能撑开标准流的块级元素。
- 案例：父子级标签，父级没有高度，后面的标准流盒子会受影响，显示到上面的位置
- 规避：父级加标签
```css
	<style>
        .top {
            margin: 0 auto;
            width: 1000px;
            height: 300px;(注意父级加高)
            background-color: pink;
        }
        
        .bottom {
            height: 100px;
            background-color: green;
        }
        
        .left {
            float: left;
            width: 200px;
            height: 300px;
            background-color: #ccc;
        }
        
        .right {
            float: right;
            width: 790px;
            height: 300px;
            background-color: skyblue;
        }
    </style>
```
### 清除浮动的方法
#### 父级加高（规避）
#### 额外标注法：(特点：缺点：会在页面中添加额外的标签，会让html结构变复杂)
	1.在父级元素内容最后添加一个块级元素
	2.给添加的元素设置clear:both
###### 额外标注法
```html
	<style>
        .top {
            margin: 0 auto;
            width: 1000px;
            height: 300px;
            background-color: pink;
        }
        
        .bottom {
            height: 100px;
            background-color: green;
        }
        
        .left {
            float: left;
            width: 200px;
            height: 300px;
            background-color: #ccc;
        }
        
        .right {
            float: right;
            width: 790px;
            height: 300px;
            background-color: skyblue;
        }
        
        .clearfix {
        	<!--清除左右两侧浮动影响-->
            clear: both;
        }
    </style>
    
    
    
    <body>
    <!-- 父子级标签，父级没有高度，后面的标准流盒子会受影响，显示到上面的位置 -->
    <div class="top">
        <div class="left"></div>
        <div class="right"></div>
        
        <div class="clearfix"></div>
    </div>
    <div class="bottom"></div>
</body> 
    

```
#### 单伪元素清除法
	1.用伪元素替代了额外标签
###### 基本写法
```css
	 .clearfix::before {
            content: '';
            /* 伪元素添加的是行内的，我们需要的是块级的 */
            display: block;
            clear: both;
        }
```
######  补充写法
```css
	 .clearfix::before {
            content: '';
            /* 伪元素添加的是行内的，我们需要的是块级的 */
            display: block;
            clear: both;
            height: 0;
            visibility: hidden;
        }
```
#### 双伪元素清除法
```css
	 /* 清除浮动 */
        /* .clearfix::before 用来解决外边距塌陷 */
        
        .clearfix::before,
        .clearfix::after {
            content: '';
            display: table;
        }
        /* 真正清除浮动的标签 */
        
        .clearfix::after {
            clear: both;
        }
```
#### 给父元素设置overflow:hidden
- 给父元素直接设置overflow:hidden
``` css
	.top {
            margin: 0 auto;
            width: 1000px;
            height: 300px;
            background-color: pink;
            overflow: hidden;
        }
```
### 学成在线项目
- css文件需要引用
```css
<link rel="stylesheet" href="./css/index.css">
```
### 定位
1.可以让元素自由的钉在网站的任何位置上。
- 应用场景
	1.可以始终让盒子固定在页面中的某个位置
- 属性名：plsition（只加position位置不会改变）
- 如果left和right都有,以left为准,top和bottmo都有，以top为准
- 常见属性值：
|定位方式 | 属性值|
|:-----:|:------:|
| 静态位置|static |
| 相对位置|relative |
|绝对定位|absolute |
| 固定定位|fixed |
- 设置偏移值
	1.偏移值分为水平和垂直方向
	2.选取原则一般是就近原则(离哪边近用哪个)
|方向 | 属性名|属性值|含义|
|:-----:|:------:|:------:|:------:|
| 水平|left |数字+px |距离左边的距离|
| 水平|right |数字+px |距离右边的距离|
|垂直|top |数字+px |距离上边的距离|
| 垂直|bottom |数字+px |距离下边的距离|
#### 相对定位
- 介绍：相对于自己之前的位置进行移动
- 代码：position:relative:
- 特点：
	1.需要配合方位属性实现移动
	2.相对于自己原来的位置进行移动
	3.在页面中占位置-没有脱标
- 应用场景
	1.配合绝对定位组CP()
	2.用于小范围移动
#### 绝对定位（绝对定位的盒子具备行内块的特点）
- 介绍： 绝对定位: 先找已经定位的父级, 如果有这样的父级就以这个父级为参照物进行定位;有父级, 但父级没有定位, 以浏览器窗口为参照为进行定位
```css
	<style>
        /* css书写: 1. 定位 / 浮动 / display ; 2. 盒子模型; 3. 文字属性 */
        
        .box {
            /* 绝对定位: 
                先找已经定位的父级, 如果有这样的父级就以这个父级为参照物进行定位;
                有父级, 但父级没有定位, 以浏览器窗口为参照为进行定位
            */
            position: absolute;
            /* left: 50px; */
            left: 0;
            top: 0;
            /* 
            1. 脱标, 不占位
            2. 改变标签的显示模式特点: 具体行内块特点(在一行共存, 宽高生效)
            */
            width: 200px;
            height: 200px;
            background-color: pink;
        }
    </style>
    
    
    
    
    <style>
        .father {
            position: relative;
            width: 400px;
            height: 400px;
            background-color: pink;
        }
        
        .son {
            /*  相对, 绝对 */
            /* 父级相对定位; 子级绝对定位 -- 子绝父相 */(广义的父级)
            /* position: relative; */
            /* position: absolute; */
            /* right: 100px; */
            width: 300px;
            height: 300px;
            background-color: skyblue;
        }
        
        .sun {
            position: absolute;
            /* left: 20px;
            top: 30px; */
            right: 20px;
            bottom: 50px;
            width: 200px;
            height: 200px;
            background-color: green;
        }
        /* 绝对定位查找父级的方式: 就近找定位的父级, 如果逐层查找不到这样的父级, 就以浏览器窗口为参照进行定位 */
    </style>
```
#### 固定定位
- 介绍：死心眼型定位，相对于浏览器进行定位移动
- 代码：position:fixed
- 特点:
	1.需要配合方位属性实现移动
	2.相对于浏览器可视区域进行移动
	3.在场景中不占位置->已经脱标
- 应用场景：
	1.让盒子固定在屏幕中的位置。
```css
	<style>
        .box {
            /* 脱标，不占位置，具备行内块特点 */
            /* 改变位置参考浏览器窗口 */
            position: fixed;
            left: 0;
            top: 0;
            width: 200px;
            height: 200px;
            background-color: pink;
        }
    </style>
```
#### 元素的层级关系
- 不同布局方式元素层级关系：标准流<浮动<定位
- 不同定位之间的层级关系：相对，绝对，固定默认层级相同。
- 此时HTML中写在下面的元素层级更高，会覆盖上面的元素。
```css
	<style>
        div {
            width: 200px;
            height: 200px;
        }
        
        .one {
            position: absolute;
            background-color: pink;
            /* 在第1层 */
            z-index: 1;
            left: 20px;
            top: 50px;
        }
        
        .two {
            position: absolute;
            left: 50px;
            top: 100px;
            background-color: skyblue;
        }
        /* 如果是默认情况下，后来者居上 */
        /* z-index：整数，数值越大，显示行数越靠上，默认值是0，配和定位才能生效 */
    </style>
```
### css布局方式
- 浮动，标准流，定位
### 装饰
#### 文字对齐问题
- 场景：解决行内(行内块)元素垂直对齐问题
- 问题：当图片和文字在一行中显示时，其实底部是不对齐的
- 属性名：vertical-align
- 属性值：
| 属性值 |效果|
|:-----:|:------:|
| baseline|默认基线对齐|
| top|顶部对齐 |
|middle|中部对齐 |
| bottom|底部对齐 |
- 注意：浏览器遇到行内和行内块标签当作文字处理，默认文字是按照基线对齐的。
```css
	.son img {
            width: 300px;
            /* 浏览器吧行内和行内块标签当作文字处理，默认基线对齐 */
            /* vertical-align: middle; */
            display: block
            /*(两种解决办法都可以)*/
        }	
```
#### 光标类型
- 场景：设置鼠标光标在元素上显示的样式
- 属性名：mursor
- 常见属性值：
| 属性值 |效果|
|:-----:|:------:|
| default|默认值，通常时箭头|
| poInter|小手效果，提示用户可以点击 |
|text|工字型，提示用户可以选择文字 |
| move|十字光标，提示用户可以移动 |
```css
	<style>
        div {
            width: 200px;
            height: 200px;
            background-color: pink;
            /* 手型 */
            /* cursor: pointer; */
            /* 工字型 */
            cursor: text;
            /* 十字 */
            cursor: move;
        }
    </style>
```
#### 边框圆角
- 场景：让盒子四个角变得圆润，增加页面细节
- 属性名：border-radius
- 常见取值：数字+px，百分比（多个取值中间需要用空格隔开）
- 赋值规则：从左上角开始赋值，然后顺时针开始赋值，没有赋值的看对角
```css
	<style>
        div {
            width: 300px;
            height: 300px;
            background-color: skyblue;
            margin: 50px auto;
            /* 一个值表示四个角是相同的 */
            /* border-radius: 10px; */
            /* 4值：左上，右上，右下，左下 */
            /* border-radius: 10px 20px 30px 40px; */
            /* 3值:没有赋值的看对角 */
            /* border-radius: 10px 40px 80px; */
            /* 2值：没有赋值看对角 */
            border-radius: 10px 80px;
        }
    </style>
```
#####  画正圆
1.盒子必须是正方形
2.设置边框圆角是盒子的一半（最大值50%）
```css
	<style>
        .one {
            width: 200px;
            height: 200px;
            background-color: pink;
            border-radius: 100px;
            /* 50%取盒子尺寸的一半 */
            border-radius: 50%;
        }
    </style>
```
#####  胶囊按钮
1.盒子必须是长方形
2.设置：border-radius:盒子高度的一半
```css
	.two {
            width: 600px;
            height: 300px;
            background-color: skyblue;
            border-radius: 150px; 
        }
```
####  overflow溢出部分显示效果
- 溢出部分：指的是盒子内容部分所超出的盒子范围区域。
- 场景：控制内容溢出部分的显示效果，如：显示，隐藏，滚动条。。。
- 属性名：overflow
- 常见属性值;
| 属性值 |效果|
|:-----:|:------:|
| visible|默认溢出部分可见|
| hidden|溢出部分隐藏 |
|scroll|无论是否溢出，都显示滚动条 |
| auto|根据是否溢出，自动显示或隐藏滚动条|
```css
	<style>
        .box {
            width: 300px;
            height: 300px;
            background-color: pink;
            /* 溢出隐藏 */
            /* overflow: hidden; */
            /* 这里是滚动的意思 ，无论内容是否超出都显示滚动条*/
            /* overflow: scroll; */
            /* auto根据内容是否超出显示滚动条 */
            overflow: auto;
        }
    </style>
```
#### 元素本身显示隐藏
- 场景：让元素本身在屏幕中不可见。如鼠标:hover后的元素隐藏
- 常见属性：
	1. visiblity：hidden
	2. display：none(重点!)
```css
	<style>
        div {
            width: 200px;
            height: 200px;
        }
        
        .one {
            /* 占位隐藏效果 */
            /* visibility: hidden; */
            /* 不占位置的隐藏 */
            display: none;
            background-color: green;
        }
        
        .two {
            background-color: pink;
        }
    </style>
    
    
     .code {
            position: absolute;
            left: 50%;
            top: 41px;
            transform: translate(-50%);
            display: none;
        }
        /* 鼠标悬停显示二维码图片 */
        
        .nav li a:hover img {
            display: block;
        }
```
#### 拓展-元素整体透明度
- 场景：让元素包括内容一起变透明
- 属性名：opaticy
- 属性值：0~1之间的数字（1表示完全不透明，0表示完全透明）
- 注意点：opacity会让元素整体透明，包括里面的内容，如：文字。。。
```css
	<style>
        /*  */
        
        div {
            width: 400px;
            height: 400px;
            background-color: green;
            opacity: 0.5;
        }
    </style>
```
### 精灵图
- 使用步骤
  1.创建一个盒子，设置盒子的尺寸和小图尺寸相同
  2.将精灵图设置为盒子背景
  3.修改背景位置：通过PxCook测量小图片左上角坐标，分别取负值设置给盒子的background-position：x y
```css
	<style>
        span {
            display: block;
            width: 57px;
            height: 57px;
            background-color: pink;
            background-image: url(./sprites.png);
            /* 水平方向和垂直方向 */
            /*往左边移动，取负数 */
            background-position: -3px 0;
        }
        
        b {
            display: block;
            width: 35px;
            height: 28px;
            background-color: skyblue;
            background-image: url(./sprites.png);
            background-position: -205px -15px;
        }
    </style>
```
### 背景图片的大小
- 作用：设置背景图片的大小
- 语法：background-size：宽度，高度
- 取值：
| 取值 |场景|
|:-----:|:------:|
| 数字+px|简单方便实用|
| 百分比|相对于当前盒子自身的宽高比 |
|contain|包含，将背景图片等比例缩放，知道不会超出盒子的最大 |
| cover|覆盖，将背景图片等比例缩放，直到刚好填满整个盒子没有空白|
#### background连写拓展
- 完整连写：background:color image repeat position：size;
- 注意点：backgruond-size和background连写同时设置时，需要注意覆盖问题
- 解决：1 要么单独的样式写连写的下面 2. 要么单独的样式写在连写的里面。

### 盒子阴影
- 作用：给盒子添加阴影效果
- 属性名：box-shadow
- 取值：
| 参数|作用|
|:-----:|:------:|
| h-shadow|必须，水平位移量，允许负值|
| v-shadow|必须，垂直位移量，允许负值 |
|blur|可选，模糊度 |
| spread|可选，阴影扩大|
| color|可选，阴影颜色|
| inset|可选，将阴影改为内部阴影|
### 过渡
- 作用：让元素的样式慢慢变化，常配合hover使用，增强网页交互体验
- 属性名：transition
- 常见取值：
| 参数|取值|
|:-----:|:------:|
| 过渡属性|all:所有能过渡的属性都过渡。具体属性名：width:只有width过渡|
| 过渡时长|数字+s |
- 注意点：
	1.过渡需要：默认状态和hover状态样式不同，才能有过渡效果。
	2.transition:属性给需要过渡的元素本身加
	3.transition:属性设置在不同的状态中，效果不同
		1.给默认状态设置，鼠标移入移出都有效果
		2.给hover状态设置，鼠标移入有过渡效果，移出没有过渡效果

### 项目前置认知
#### DOCTYPE文档说明
- <!DOCTYPE html>文档类型声明，告诉浏览器该网页的html版本
- 网页语言
	1.《heml lang=''en""》标识网页使用语言
	2.作用：搜索引擎归类+浏览器翻译
	3.常见语言：zh-CN简体中文/en英文
- 字符编码
	1.《meta charset="UTF-8"》标识网页使用的字符编码
	2.作用：保存和打开的字符编码需要统一设置否则可能会出错
	3.常见字符编码：- utf-8：万国码，GB2312:6000+汉字，GBK:20000+汉字


#### SEO
- 作用：搜索引擎优化
- 提升SEO常见的方法
 1.上升排名
 2.将网页改成html后缀
 3.标签语义化
```html
	<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="京东全球版-专业的综合网上购物商城，为您提供正品低价的购物选择、优质便捷的服务体验。商品来自全球数十万品牌商家，囊括家电、手机、计算机、服装、居家、母婴、美妆、个护、食品等丰富品类，满足各种购物需求。支持香港自提、京东集运和国际卡支付，现时已覆盖香港、澳门、台湾、新加坡、马来西亚、美国、加拿大、澳大利亚、新西兰和日本等海外200多个国家和地区。">
    <meta name="keywords" content="网上购物,家电,手机,计算机,服装,国际,海外,居家,母婴,美妆,个护,食品,京东,集运,全球">
    <title>京东全球版-专业的综合网上购物商城</title>
</head>
```
#### ico图标设置
- 场景：显示在标签页标题左侧的小图标
- 常见代码：
```html5
	<link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
```