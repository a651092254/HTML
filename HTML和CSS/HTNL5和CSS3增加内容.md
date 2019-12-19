# HTML5新增内容
## 一·新增语义化标签
- header    --头部标签
- nav   --导航标签
- article   --内容标签
- section   --块级标签
- aside --侧边标签栏
- footer    --尾部标签  
**主要是替代之前的`<div class="header/nav/.../footer"></div>`效果**  
*有以下需要注意的:*
1. *主要用于搜索引擎收录*
2. *可以多次使用*
3. *在IE9中需要转为块级元素*
4. *语义化的标签，在移动端比较友好*  
##### 代码示例：
```
<body>
    <header class="pink">
        <h3>header</h3>
    </header>
    <nav class="pink">
        <h3>nav</h3>
    </nav>
    <article class="pink">
        <h3>article</h3>
    </article>
    <section class="pink">
        <h3>section</h3>
    </section>
    <aside class="pink">
        <h3>aside</h3>
    </aside>
    <footer class="pink">
        <h3>footer</h3>
    </footer>
</body>
```
##### 标签效果：
![新标签效果](img/h5_new_tag.png "新标签效果")
## 二·新增多媒体标签
### 1.音频标签--audio
原来在不使用标签的情况下也可以用音频，新加标签后可以支持更多的音频文件格式（ogg/mp3/wav）  
不同的浏览器对音频文件支持不同，具体如下：

格式|IE9|Firefox3.5|Opera10.5|Chrome3.0|Safari3.0
--|:--:|:--:|:--:|:--:|:--:|
Ogg Vorbis| |支持|支持|支持| |
MP3|支持| | |支持|支持|
Wav| | 支持|支持| |支持|
<!-- ![不同浏览器对音频文件支持不同](img/audio.png) -->
##### 标签属性：
属性|值|描述
--|--|--
autoplay|autoplay|音频会自动播放（google浏览器除外）
controls|controls|加上该属性会在面板显示一个控制面板
loop|loop|音频循环播放
src|url|要播放音频的url，为避免兼容问题，一般会加上多种资源

##### 代码示例：
```
<audio controls>
    <source src="media/芒种.mp3">
    <source src="media/芒种.ogg">
您的浏览器不支持audio标签
</audio>
```
##### 标签效果：
![audio标签](img/audio标签效果.gif)
### 2·视频标签--video
以前都是flash来实现视频播放，但是flash本身存在漏洞  
不同浏览器对标签的兼容性：  

格式|IE|Firefox|Opera|Chrome|Safari
--|--|--|--|--|--
Ogg|No|3.5+|10.5+|5.0+|No
MPEG4|9.0+|No|No|5.0+|3.0+
WebM|No|4.0+|10.6+|6.0+|No
##### 标签属性
属性|值|描述
--|--|--
autoplay|autoplay|视频就绪就自动播放（谷歌浏览器需要添加muted静音来实现自动播放）（重点）
controls|controls|显示视频播放控件
width|px|设置播放器宽度
height|px|设置播放器高度
loop|loop|循环播放
preload|auto/none|是否预先加载视频
src|url|视频文件地址
poster|imgurl|视频加载画面显示的图片
muted|muted|静音播放
##### 代码示例
```
    <video controls preload="none" loop muted poster="img/video_1.jpg" width="500px">
        <source src="media/tvc.mp4"> 
    </video>
```
##### 标签效果
![video标签](img/video标签效果.gif)
## 三·新增input属性

属性值|说明
--|--
type="email"|限制用户输入必须为邮箱地址
type="url"|限制用户输入必须为URL类型
type="date"|限制用户输入必须为日期类型
type="time"|限制用户输入必须为时间
type="month"|限制用户输入必须为月类型
type="week"|限制用户输入必须为周类型
***type="number"***|限制用户输入必须为数字类型
***type="tel"***|限制用户输入必须为手机号格式
***type="search"***|搜索框
type="color"|颜色选择表单

##### 代码示例
```
    <form action="">
        <ul>
            <li>邮箱：<input type="email"/></li>
            <li>网址：<input type="url"/></li>
            <li>日期：<input type="date"/></li>
            <li>时间：<input type="time"/></li>
            <li>月份：<input type="month"/></li>
            <li>周：<input type="week"/></li>
            <li>数量：<input type="number"/></li>
            <li>手机号码：<input type="tel"/></li>
            <li>搜索：<input type="search"/></li>
            <li>颜色：<input type="color"/></li>

            <li> <input type="submit" value="提交"></li>
        </ul>
    </form>
```
##### 标签效果
![new_input](img/new_input.png)
## 四·新增表单属性
### 1、required
设置表单内容变为必填，值为"required"
##### 代码示例：
```
<li><input type="text" required="required"></li>
```
##### 代码效果：
![required属性](img/required属性.png)
### 2、placeholder
设置表单内默认显示的文字，输入内容会消失，值是要显示的内容；
##### 代码示例：
```
<li><input type="text" placeholder="带placeholder的表单"></li>
```
##### 代码效果：
![placeholder属性](img/placeholder属性.png)
### 3、autofocus
设置网页打开时自动聚焦到该表单，值设置autofocus
##### 代码示例：
```
<li><input type="text" autofocus="autofocus" placeholder="带autofocus的表单"></li>
```
#### 代码效果：
![aotofocus属性](img/autofocus.gif)
### 4、autocomplete
设置记录历史填入信息，可以自动完成历史信息输入，值设置"on"/"off";
##### 代码示例：
```

```
##### 代码效果：

# CSS3新增内容
## 一、新增选择器
### 1、属性选择器
选择器|匹配结果
--|--
a[b]|匹配具有b属性的a标签
a[b="c"]|匹配具有b属性且属性值是c的a标签
a[b^="c"]|匹配具有b属性并且属性值以c开头的a标签
a[b$="c"]|匹配具有b属性并且属性值以c结尾的a标签
a[b*="c"]|匹配具有b属性并且属性值包含c的a标签

> 注意事项：  
>用中括号来表示属性;  
>标签和中括号之间不用保留空格；
>类选择器、属性选择器、伪类选择器权重都是10；
##### 代码示例：
```
<div class="father">
    <span class="son1">大儿子</span>
    <span class="son2">小儿子</span>
    <span class="grandson1">大孙子</span>
    <span class="grandson2">小孙子</span>
    <span>捡来的</span>
</div>

<style>
    .father {
        width: 500px;
        height: 500px;
        background-color: aquamarine;
    }
    span{
        float:left;
        width: 50px;
        height: 50px;
        background-color:pink;
        border: black 1px solid;     
    }
    span[class]{
        background-color:blue;
    }
    .father span[class^="grand"]{
        background-color: yellow;
    }
    .father span[class$="dson1"]{
        background-color: red;
    }
    .father span[class*="i"]{
        background-color: purple;
    }
</style>
```
##### 代码效果：
![属性选择器](img/属性选择器.png)
### 2、结构伪类选择器
选择器|匹配结果
--|--
A:first-child|匹配父级元素中的第一个子元素,相当于a:nth-child(1)；
A:last-child|匹配父级元素中的最后一个元素,a：nth-last-child(1)；
A:nth-chile(n)|匹配父级元素中的第n个a元素，n可以是**整数**、**关键词**（even/odd）,也可以是**公式**;n从1开始(常见公式：2n,2n+1,5n,5-n,5+n)；
A:nth-last-child|匹配父级元素中倒数第n个元素；
A:first-of-type|选择父元素中第一个类型为A的子元素；
A：last-of-type|选择父元素中最后一个类型为A的子元素
A:nth-of-type(n)|选择父元素中第n个类型为A的子元素
>**A:nth-child和A:nth-of-type的区别**  
nth-child会从所有子元素中选取，如果最后选中的不是A类型会导致未选中任何元素，nth-of-type是先把A类元素选出来，再挑第n个。
##### 代码示例：
```
    <ul class="child">
        <li>1</li>
        <p>2</p>
        <li>3</li>
    </ul>
    <ul class="type">
        <li>1</li>
        <p>2</p>
        <li>3</li>
    </ul>

     .child li:nth-child(2) {
            width: 100px;
            height: 100px;
            background-color: blue;
        }
        
        .child li:nth-child(3) {
            width: 100px;
            height: 100px;
            background-color: yellow;
        }
        
        .type li:nth-of-type(2) {
            width: 100px;
            height: 100px;
            background-color: red;
        }

```
##### 代码效果：
![结构伪类选择器](img/结构伪类选择器.png)
### 3、伪元素选择器
选择器|作用
--|--
A::before|在A元素内容的前面加入一个行内元素
A::after|在A元素内容的后面加入一个行内元素
>**注意事项**  
选择器内必须包含content属性；  
伪元素选择器和标签选择器一样，权重是1；  
加入的内容是**行内元素**；
##### 代码示例
```
<div class="weiyuansu">原本内容</div>

.weiyuansu {
            width: 200px;
            height: 200px;
            margin: 20px auto;
            background-color: green;
        }
        .weiyuansu::before{
            display: block;
            content: "我是前面插队的";
            height: 60px;
            line-height: 60px;
            background-color: pink;


        }
        .weiyuansu::after{
            content: "我是后面插队的";
            height: 60px;
            line-height: 60px;
            background-color: pink;   
        }
```
##### 代码效果
![伪元素选择器](img/伪元素选择器.png)
## 二、转换
### 1、2D转换
#### （1）位移
语法|作用
--|--
transform:translate(x,y)|在平面上平移
transform:translateX(x)|沿x轴位移
transform:translateY(y)|沿y轴平移
移动盒子的方式：定位、外边距、2D移动
>**注意点：**  
移动按照坐标轴方向移动；  
不会影响其他元素的位置；  
还可以按照自身的百分比来移动；  
对行内元素是不起作用的。
##### 代码示例：
```
    <ul>
        <li>translate(20px,20px)</li>
        <li>translateX(20px)</li>
        <li>translate(20px)</li>
    </ul>

    li:nth-child(1):hover{
            transform:translate(20px,20px);
    }
    li:nth-child(2):hover{
            transform:translateX(20px);
    }
    li:nth-child(3):hover{
            transform:translateY(20px);
    }
```
##### 代码效果：
![2D位移](img/2D位移.gif)
#### （2）旋转
语法|作用
--|--
transform:rotate(度数)|旋转指定度数  
transform-oringin|指定旋转中心（默认是中心）
>**注意点：**  
旋转单位是度数deg；  
旋转中心单位可以用**方位名词**、**百分比**、**px**;  
旋转正值是顺时针，负值是逆时针；
##### 示例代码：
```
    <div class="banner">
        <div class="shunshi">顺时针<br/>中心</div>
        <div class="nishi">逆时针<br/>右下角</div>
    </div>

    .shunshi:hover{
            transform:rotate(360deg);
            transition: all 2s;           
    }
    .nishi{
        transform-origin:right bottom;
    }
    .nishi:hover{
        transform:rotate(-360deg);
        transition: all 2s;
    }

```
##### 代码效果：
![2D旋转](img/2D旋转.gif)
#### （3）缩放
##### 语法：
transform:scale(x,y)
>**注意点：**  
参数里面不需要带单位，指的是缩放的倍数；  
参数小于1是缩小，大于1是放大；  
只写一个参数表示缩放相同倍数；  
缩放效果不会影响到其他元素；
##### 代码示例：
```
<div class="banner">
    <div class="shunshi">放大两倍</div>
    <div class="nishi">缩小一半 <br/>右下角</div>
</div>

.shunshi:hover{
    transform:scale(2,2);
    transition: all 2s;   
}
.nishi{
    transform-origin:right bottom;
}
.nishi:hover{
    transform:scale(0.5);
    transition: all 2s; 
}
```
##### 代码效果：
![缩放](img/缩放.gif)
#### （4）综合写法
##### 语法：
transform:translate(x,y) rotate(度数) scale(x,y);
>**注意点：**  
当位移和其他转换综合时，位移要写在前面；
##### 示例代码：
```
.zonghe:hover{
    transform:translate(100px,100px) rotate(360deg) scale(2);
    transition: all 2s;
}
```
##### 代码效果：
![2d转换综合](img/2D转换综合写法.gif)

### 2、3D转换
#### （1）三维坐标系
相对于之前的二维多一个z轴，方向为从屏幕垂直指向外面
#### （2）3D移动
语法|作用
--|--
translate3d(x,y,z)|设置三维的移动
translate(z)|沿Z轴方向进行移动
>**注意点：**  
translate3d中三个参数不能有省略，如果没有位移需要填充0；  
3D移动需要借助透视来实现效果；  
Z轴位移，正值是向屏幕外位移，负值是向屏幕内侧；
##### 示例代码：
```
<div class="banner">
    <div class="trans3d">3D位移</div>
</div>

.banner{
    perspective: 500px;
    width: 600px;
    height: 500px;
    margin: 60px auto;
    padding: 100px;
    background-color: #60e160;
}
div{
    margin: 100px;;
    width: 100px;
    height: 100px;
    border:black solid 1px;
    line-height: 50px;
    text-align: center;
    background-color: pink;
}
.trans3d:hover{
    transform:translate3d(100px,100px,200px);
    transition: all 2s;
}
```
##### 代码效果：
![3D位移](img/3D位移.gif)
#### （3）3D旋转
语法|作用
--|--
transform:rotateX(*deg)|绕X轴旋转
transform:rotateY(*deg)|绕Y轴旋转
transform:rotateZ(*deg)|绕Z轴旋转
transform:rotate3d(x,y,z,deg)|绕x,y,z定义的矢量旋转指定度数（仅作了解）
>**注意点：**  
旋转的方向遵循左手法则（大拇指指向轴的正方向，其他手指指向的就是旋转方向）
##### 示例代码：
```
<div class="banner">
    <div class="xuanzhuanX">X轴旋转</div>
    <div class="xuanzhuanY">Y轴旋转</div>
    <div class="xuanzhuanZ">Z轴旋转</div>
    <div class="xuanzhuanS">矢量轴旋转</div>
</div>

div[class^="xuanzhuan"]{
    float: left;
    margin: 10px;
}
.xuanzhuanX:hover{
    transform:rotateX(360deg);
    transition: all 1.5s;
}
.xuanzhuanY:hover{
    transform:rotateY(360deg);
    transition: all 1.5s;
}
.xuanzhuanZ:hover{
    transform:rotateZ(360deg);
    transition: all 1.5s;
}
.xuanzhuanS:hover{
    transform:rotate3d(1,1,0,360deg);
    transition: all 1.5s;
}
```
##### 代码效果：
![3D旋转](img/3D旋转.gif)
#### （4）透视
定义：透视也称为视距，视距是眼睛到屏幕的距离。就是将3d物体投影到屏幕上，产生近大远小的效果。
>**注意点：**  
透视的单位是px，perspective: * px；  
要写在被透视元素的父级元素
#### （5）3D呈现
语法|作用
--|--
transform-style：flat|默认属性，子元素不开启3d状态
transform-style：preserve-3d |子元素保持3D状态
>**注意点：**  
transform-style属性是写在父级上的  
z-index可以设置前后顺序
##### 示例代码：
```
<div class="banner">
    <div class="red1"">红色的</div>
    <div class="blue1">蓝色的</div>
</div>

.banner{
    transform-style: preserve-3d;
    position: relative;
    perspective: 500px;
    width: 200px;
    height: 200px;
    margin: 60px;
}
div[class$="1"]{
    position: absolute;
    top:20px;
    left: 20px;
    width: 200px;
    height: 200px;
    background-color: pink;
}
.blue1{
    transform:rotateX(75deg);
    background-color: blue!important;
}
.banner:hover{
    transform:rotateY(360deg);
    transition: all 2s;
}
```
##### 代码效果：
![3d呈现](img/3D呈现.gif)
## 三、动画
### 1、基本使用
(1)定义动画 
``` 
@keyframes 动画名{
0%{开始状态}		
100%{结束状态}
}
```
(2)调用动画
```
animation-name:动画名称；
animation-duration:持续时间；
```
### 2、动画序列
0% 100% 和 from to 等同效果都是设置动画关键帧
>**注意点：**  
可以通过不同百分比设置多个关键帧；  
百分比就是总时间的划分；
### 3、动画属性
##### 常用属性：
动画属性|作用|属性参数
--|--|--
@keyframes|规定动画|命名规则
animation-name|动画名称|已设置的动画名称
animation-duration|动画完成一个周期的时间|s/ms
animation-timing-function|速度曲线|ease/linear/steps( )
animation-delay|动画开始时间|s/ms
animation-iteration-count|动画循环次数|正整数/infinite
animation-direction|动画在下一周期播放的方向|normal/alternate
animation-fill-mode|动画结束时的状态|保持forwards/回到起始backwards
animation-play-state|动画播放状态|running/paused

##### 属性简写：
animation: 动画名称 持续时间 运动曲线 何时开始 播放次数 是否反方向 动画起始或结束的状态;  
animation: name duration timing-function delay iteration-count direction fill-mode;  
前两个属性不能省略。  
简写不包含暂停播放的状态，状态经常和鼠标操作搭配使用。
##### 速度曲线详解
值|描述
--|--
linear|匀速
ease|默认，低速开始变快，结束变慢
ease-in|以低速开始
ease-out|以低速结束
ease-in-out|以低速开始和结束
steps( )|指定时间函数中的步长 (突变式，上面其他的是渐变式)
##### 代码示例：
```
<div class="dh">动画</div>

body{
        transform-style: preserve-3d;
    }
@keyframes move{
    0%{
        transform:translate(0,0);
        background-color:pink;
    }
    25%{
        transform: translate(400px,0) rotateY(180deg);
        background-color: red;
    }
    50%{
        transform: translate(400px,200px) rotateY(360deg);
        background-color: blue;
    }
    75%{
        transform: translate(0,200px) rotateY(540deg);
        background-color:yellow;
    }
    100%{
        transform: translate(0,0) rotateY(720deg);
        background-color: pink;
    }    
}
.dh{
    width: 100px;
    height: 100px;
    animation: move 2s linear 0s infinite normal forwards;
}
```
##### 代码效果
![动画](img/动画.gif)
## 四、浏览器私有前缀
私有前缀是为了兼容老版本的浏览器
前缀|作用
--|--
-moz-|代表firefox浏览器私有属性
-ms-|代表ie浏览器私有属性
-webkit-|代表safari、chrome浏览器私有属性
-o-|代表opera浏览器私有属性
##### 代码示例：
```
-moz-border-radius:50%;
-o-border-radius:50%;
-webkit-border-radius:50%;
border-radius:50%;
```






