# 循环：

利用循环，能够让一些重复的事情，变得更加容易实现，比如打印一些有固定规律的星星，再比如使用循环计算1加到100的和，比如打印九九乘法表。使用循环，能够让我们事半功倍。

## while循环

主要作用：

​	能够执行循环，重复执行代码。

语法：

​	while(条件){

​			循环的内容	

​	}

执行顺序：

​	小括号-->大括号-->小括号-->大括号.

特点：

​	先判断后执行，while循环有可能一次都不执行。

例子1：

​	循环5次,依次输出1，2，3，4，5

```
let i = 1;
while(i<=5){
	document.write(i);
	i++;
}
```

例子2：

​	循环5次，依次输出5，4，3，2，1

```
let i = 5;
while(i>0){
	document.write(i);
	i--;
}
```

## do..while

主要作用：

​	表示循环的意思，能够重复执行代码.

语法：

​	 do{

​		循环内容(循环体)

​	}while(条件)

执行顺序：

​	 大括号-->小括号-->大括号-->小括号-->

特点：

​	先执行，后段判断，这种循环至少会执行一次。

例子1：

​	输出1,2,3,4,5

```
let i  = 1;
do{
	document.write(i);
	i++
}while(i<=5)
```

例子2：

​	使用嵌套循环，输出九九乘法表

```
let x = 1;
do{
	
	
	let y = 1;
    do{
document.write(x+"*"+y+"="+x*y+"&nbsp;&nbsp;&nbsp;&nbsp;")
        y++
    }while(y<=x);
    document.write("<p></p>")
	

	x++
}while(x<=9);
```

## for循环

主要作用：

​	表示循环的意思，能够重复执行代码.

语法：

​	for(定义变量(1);条件(2);加减(3)){

​			循环的内容(4)

​	}

执行顺序：

​	1-->2-->4-->3-->2-->4-->3-->2-->4-->........

特点：

​	语法相对于另外两个循环来说要更加的精简。for循环是通过小括号来控制循环是否执行，执行多少次的。大括号是内容。

例子1：

​	输出1,2,3,4,5

```
for(let i = 1;i<=5;i++){
	document.write(i+"<br/>")
}
```

练习

​	1.使用for循环打印9,9乘法表

​	2.使用for循环打星星

```
*******
 *****
  ***
   *
```

## 循环的停止

方式1：通过改变条件，让循环自然停止

​			 如果是嵌套循环，我们要停止内层循环，就改变内层循环的条件，如果要停止外层循环，我们就改变内层循环的条件即可。

```
方式1：通过改变条件来达到目的。
该循环依次输出0,1,2,3,....50。
for(let i=0;i<100;i++){
    document.write(i+"<br/>");
    //如果当i等于50的时候，我希望循环能够停止
    if(i == 50){
    	i=101;
	}
}
```

方式2：通过break关键字，强制停止循环

​		     如果要停止嵌套循环，如果是停止内层循环，我们就直接使用break即可，如果要停止外层循环，需要给外层循环取一个名字才行(其实所有的循环都可以取一个名字，名字要写字母+数字)。

```
该循环依次输出0,1,2,3,....50。
for(let i=0;i<100;i++){
		document.write(i+"<br/>");
		//如果当i等于50的时候，我希望循环能够停止
		if(i == 50){
			break;  //休息--永远
		}
	}
```

例子：循环的停止

	MINGZI:for(let x=0;x<100;x++){		
			MZ:for(let y=0;y<10;y++){
				if(y==5){
					break MINGZI;	//停止MINGZI循环
					break MZ;		//停止MZ循环
				}
			}
		}

## 循环的继续

关键字：continue

含义：当次循环剩下的内容不执行了，会继续执行下一次循环的内容。

案例1：

使用break

```
for(let i=0;i<2;i++){
		document.write("<p>床前明月光</p>")
		document.write("<p>心里有道光</p>")
		if(i==0){
			break/continue;
		}
		document.write("<p>明天去哪里</p>")
		document.write("<hr/>")
	}
```

使用break的结果

<img src="mdimg/1.png"/>

使用continue的结果,结果只是跳过了两句话

<img src="mdimg/2.png" />

## 数组

变量同一时间只能表示一个值。但是数组，容许我们同一时间表示多个值。

数组的结构

​	![](.\mdimg\8.png)

操作数组

创建

​	创建一个不限定长度的数组

​	let arr = new Array();

放值

​	arr[位置] = 值;

​	arr.push(值);

取值

​	let zhi = arr[位置];

其他操作

​	获取数组的长度

​	let len = zhi.length;



循环遍历数组

```
let ar01 = ["红旗","比亚迪","五零红光","汗血宝马","宝骏","奔驰"];

方式1：
for(let i = 0 ;i<ar01.length;i++){
		document.write(ar01[i]);
		document.write("<br/>")
}

方式2：
ar01.forEach(zhi=>{
	document.write(zhi);
	document.write("<br/>")
})
```

## 函数

函数就是lv，能够将很多代码装到一个包(函数，方法)里面,之后要使用这些代码的时候，只要打开包(调用函数)就可以了。

定义函数（打包)

```
function  lv(){
	内容
}
```

调用函数(打开包)

```
lv();
```



## 事件

比如我们的轮播图，需要点一下，就切换一张，比如我们的菜单，要把鼠标放上去，他才会弹出来。那么这个点一下，鼠标放上去，就是我们的事件，切换图片，显示菜单，这个是我们的dom操作。

事件决定着我们什么时候出效果（常见的事件，点击事件，鼠标放上去的事件，双击事件，鼠标离开事件...)

绑定事件

```
方式1：
<button onClick="alert(666)">按钮</button>

方式2：
<button id="btn">按钮</button>
<script>
	let bt = document.getElementById("btn");
	bt.onClick=function(){
		alert(888)
	}
</script>
```

事件绑定函数

```
<button onclick="lv()">按钮</button>
<script>
	function lv(){
		alert(666)
	}
</script>
```

常用的事件：

​	鼠标事件

​		点击事件				onclick

​		右键事件				oncontextmenu	

​		双击事件				ondblclick

​		移动事件				onmousemove

​	

阻止默认事件

​		1.绑定事件时候传递event状态对象  @click="add(event)"

​		2.写函数的时候接收event对象 function add(e){}

​		3.使用event对象阻止默认事件 e.preventDefault();



event对象

​	他表示的是状态对象

​	event.clientX;			表示鼠标当前位置离浏览器最左边的距离

​	event.clientY;			表示鼠标当前位置离浏览器最上边的距离



键盘事件

​	键盘按下去				onKeyDown

​	键盘弹起来				onKeyUp

​	

​	每个按键都有自己的键盘码。我们通过键盘码更容易进行按键的判断

拖拽事件：

要想让一个标签能够拖动，一定要设置他的dragable属性的值为true(规定)

```
事件			描述			
ondrag		该事件在元素正在拖动时触发	 
ondragend	该事件在用户完成元素的拖动时触发	 
ondragenter	该事件在拖动的元素进入放置目标时触发	 
ondragleave	该事件在拖动元素离开放置目标时触发	 
ondragover	该事件在拖动元素在放置目标上时触发	 
ondragstart	该事件在用户开始拖动元素时触发	 
ondrop		该事件在拖动元素放置在目标区域时触发
```

内容改变事件

​	当输入框的内容发生改变的时候触发的事件，主要用在时间框，下拉框		onChange

## dom操作

操作页面上的标签。dom操作决定我们出什么样子的效果。



### 查找节点	

```
根据id找节点,找回来的是1个节点		
document.getElementById("id名字")

根据class的值找节点，找回来的是多个节点
document.getElementsByTagName("class名字");

根据css选择器查找节点		--		找到一个节点
document.querySelector("#ip03");

根据css选择器查找节点        --      找到多个节点
document.querySelectorAll("div .tab")

查找父节点
ele.parentNode;
```

### 内容操作

当我们找到一个节点之后，就能够对这个节点的内容进行操作(指的是两个尖括号中间的部分)

获取它的内容

```

找到节点
	let p = document.getElementById("p0");
获取节点的内容
	let v = p.innerHTML;
```

新增内容

```
// 找到ul节点
let cd = document.getElementById("caidan");
// 添加内容
cd.innerHTML += "<li>"+v+"</li>"
```

### 输入框内容操作(特殊)

输入框的内容就是value属性的值

获取内容

```
找到节点
	let p = document.getElementById("sg");
获取节点的内容
	let v = p.value;
```

### 属性操作

获取属性的值

```
找到节点
let im = document.getElementById("id1");
获取属性的值
let zhi = im.src;		(src表示属性名)
```

设置属性的值

```
找到节点
let im = document.getElementById("id1");
获取属性的值
im.src = zhi;		(src表示属性名)
```

### 样式操作

操作class的值

获取class的值

```
let vs = ele.classList;
```

判断是否存在某个class

```
存在返回true，不存在返回false
let r = ele.classList.contains('hui')
```

删除样式

```
ele.classList.remove("值")
```

添加样式

```
ele.classList.add("值")
```

### 属性操作

设置属性

```
ele.setAttribute("属性名字",属性的值);		属性名可以使src,width,href,onclick....
```

删除属性

```
ele.removeAttribute("属性名");
```



### 节点操作

删除节点

```
ele.remove()
```

增加节点

```
为oUl节点添加一个子节点cLi
oUl.appendChild(cLi);

可以在指定子节点的前面添加新的节点
oUl.insertBefore(cLi,oldLi);
```

创建节点

```
创建一个li节点
let cLi = document.createElement("li")
```

复制节点(克隆节点)

```
浅克隆--只克隆要克隆的那个节点本身
ele.cloneNode();

深克隆--克隆要克隆的那个节点，以及他的所有的子节点
ele.cloneNode(true)
```

## 模板

相对于传统字符串来说，有两个好处，其一支持我们换行，其二不用我们频繁的拼接，可以使用${}来完成

```
let name = `<h1>hello${name}</h1>`;  ''  "" `` 

let con = `
		<h1></h1>
		<h2></h2>
`
```

## JSON

JSON是一种数据格式。主要有数组和对象两个概念。

json表示对象

```
let person = {
	name:"老王",
	addr:"隔壁",
	age:"38"
}
```

json表示多个对象

```
let persons = [
	{},
	{},
	{}
]
```

json表示多个值

```
let names = [
	"老王","小王","小明"
]
```

json表示复杂数据

```
let persons = [
		{
			name:"老王",
			addr:"隔壁"
		},
		{
			name:"小王"
		},
		{
			name:"小明"
		}
	]
	
	// 输出老王
	document.write(persons[0].addr)
	document.write(persons[0].name)
	
	document.write("<hr/>")
	// json表示多个值  
	let names = ["老王","小明","小王",21,37,true,false]
	document.write(names[3])
	
	document.write("<br/>")
	// 表示复杂数据
	let data = [
		"老王",
		"小明",
		{
			name:"小丽",
			addr:"大学城",
			pet:[
				{
					name:"小黑"
				},
				{
					name:"小可爱"
				}
			]
		}
	]
	
	document.write(data)
	console.log(data);
	
	console.log(data[0]);
	console.log(data[1]);
	console.log(data[2]);
	console.log(data[2].name);
	console.log(data[2].addr);
	console.log(data[2].pet);
	console.log(data[2].pet[0]);
	console.log(data[2].pet[0].name);
	console.log(data[2].pet[1].name);
```

规律：

​	大括号表示对象，如果是大括号，就用.的形式，获取对象的值

​    中括号表示数组，如果是中括号，就用[下标]的形式，获取数组的某一位

### 伪元素

```
相当于在元素的内容之前添加了一个伪元素
::before{
	content:"内容";
	width:"宽度";
	display:"block";
	height:"高度"
}

相当于在元素的内容之后添加了一个伪元素
::after{
	content:"内容";
	width:"宽度";
	display:"block";
	height:"高度"
}
```

## 随机数

```
获取0-1之间的随机数
let s = Math.random();

获取0-255之间的随机数
let s = Math.random()*255;

取整
parsetInt(3.14);
```

## 字符串



字符串的长度						str.length

字符串的截图						str.subStr(start,length);		

​													从start位置开始截取，一共截取length个内容

## 音乐播放

基础播放

```
<audio class="dage" src="../music/遇见.mp3" controls></audio>
```

src:		表示音乐的资源路径

controls：如果有就显示控制条，否则就不显示控制条

下一首：  改变src即可

设置进度：

自动播放：添加autoplay属性就可以了，或者调用play方法也可以。

暂停：audio.pause()

停止：audio.load();

播放：audio.play()

## 时间(Date)

获取系统当前时间

```
let date = new Date()
```

获取具体的年月日时分秒

```
let year = date.getFullYear();		//年
let month = date.getMonth()+1;		//月
let day = date.getDate();			//号
let hour = date.getHours();			//小时
let minu = date.getMinutes();		//分钟
let secon = date.getSeconds();		//秒钟
```

每一个时间点，都有他自己特定的一个毫秒值来与它对应。

```
let hm = new Date().getTime()

new Date('2020-12-12')		--日期对象
new Date(1234324324324)		--日期对象
```



## 延时器

表示延时多长事件去执行。（执行一次)

```
时间的单位是毫秒

setTimeout("代码",时间)

```

## 定时器

表示定时去执行代码(循环执行)

```

setInterval("代码",时间)
```

## 元素的大小

```
宽度 = 内容+内间距+边框
ele.offsetWidth;

宽高 = 内容+内间距
ele.clientWidth;

宽高 = 内容
window.getComputedStyle(节点).width

宽高 = 内容+内间距-滚动条(如果没有滚动条，和clientWidth一样)
el.scrollWidth/scrollHeight ：  
```

## window窗口的各种距离

```
screen.width/height： 屏幕的宽度/高度
window.innerWidth/innerHeight ： 窗口显示区的宽度/高度
window.outerWidth/outerHeight ： 窗口的外部宽度/高度
window.pageXOffset/pageYOffset ： 当前页面相对于窗口显示区左上角的 X 位置 / Y 位置 
window.screenLeft/screenTop ：  当前窗口的左上角在屏幕上的的 x 坐标和 y 坐标；
```

## 元素的距离

```
el.offsetTop / offsetLeft： 获取元素距离最近的采用定位的祖先元素的 top/Left，如果祖先元素没有采用定位的，则计算到body的距离。
el.scrollTop/scrollLeft ： 此属性为可读写属性，为元素离父元素的滚动高度和滚动左边距。也可以设置当前元素的滚动高度。 （返回的值不带单位）
```

