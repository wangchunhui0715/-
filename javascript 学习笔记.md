## javascript 学习笔记

### js书写位置           

​	行内式   

```html
<input type="button"  onlick="点击提示语">
```

​     内联式    

```html
<script>   alert("你好"); </script>
```

​	 外链式

```html
<script src="地址">  </script>
```

### js注释      

```js
//我是单行注释
```

```js
/*   我是多行注释  */
```

### js输入输出语句

```js
alert("你好");    //alert() 弹出警示框
prompt("请输入内容");	//prompt() 用户输入提示框 
console.log("在控制台中才可以看到我"); //consloe.log() 控制台打印   
```

### js变量

​	**本质:变量是程序在内存中申请的一块用来存储数据的空间

​	在声明变量时直接赋值可以叫做**变量初始化**

##### 	**变量的声明**

<script>
        var name;         //使用var关键字声明变量;
        name="王春辉"   //给name变量赋值
</script>

​	同时声明多个变量

```javascript
var name = "wang", age = 18;
```

##### 	**变量的命名**

​	只能用数字 字母 下划线  $ 符号组成

​	严格区分大小写

​	不能是数字开头 ,不能使用js保留关键字

​	命名需要有意义   推荐使用驼峰命名法

### 数据类型

​	简单数据类型

##### 	Number 数字类型        isNaN方法   判断某个值是否是数字

​			整数   

​			浮点数 

​			无穷大 infinity

​			负无穷大 -infinity

​			NAN   不是数字

#####   String字符串型 

​		加在引号内的就是字符串  ''   ""  单引号和双引号都可以

​		转义符:  \n 换行    \  \   斜杠    \  ' 单引号   \    "  双引号    \  t  缩进   \  b  空格

​		lenght   检测字符串的长度

​		字符串拼接   +号    字符串 + 任何数据 = 字符串

#####    Boolean布尔型

​		true   表示真

​		false  表示假

##### 	**undefined未定义** 类型      

​		当声明了一个变量,但未赋值是就是undefined

​		**undefined和数字相加  值是NaN**

##### 	**null 空值**      属于object类型

​		**null和数字相加 值是数字本身**

​	复杂数据类型

#### 检测数据类型

```js
typeof 变量名;   返回变量的数据类型
```

#### 数据类型转换

​	**转成字符串方法**

```js
var num = 10;
number = num.toString();   //变量.toString()方法
number = String(num);      //String(变量)方法
number = num + "";         //加号拼接字符串方法  隐式转换
```

​	**转成数字类型**

```js
parselnt(变量);   //取整
parseFloat(变量);   //取小数
Number(变量);强制转换  
js隐式转换(+ - * / );
```

​	**转成boolean类型**

```js
boolean()函数
代表空或者否定得值会被转成false 如 '' 0 NaN NULL undefined 其余全是true
```

### js运算符

##### 	算数运算符	

```js
+ 加 - 减 * 乘 /  除 %取余
```

##### 	递增和递减

```js
++递增   
前置递增 ++i;  先自加,在返回值
后置递增 i++;   先返回值,在自加
--递减
前置递减 --i;  先自减,在返回值
后置递减 i--;   先返回值,在自减
```

##### 	比较运算符

​		比较后返回 true 或  false

```js
> 大于  < 小于  == 等于  >= 大于等于   <= 小于等于 != 不等于  ===全等  !== 不全等
```

​		比较是否相等时,会自动转换数据类型

##### 	逻辑运算符

```js
&& 与  
两侧都是true返回true ,一侧为false返回false
||或 
只要有一侧为true,返回true
! 非
取反 !true  返回false  !false 返回true
```

​	逻辑短路运算  逻辑中断

​		&&

​		原理:在有多个表达式进行比较时左边表达式的值可以确定结果时,就不在运行右侧表达式.

​					表达式1为真,返回表达式2,  表达式1为假,返回表达式1

​		||

​					表达式1为真,返回表达式1,  表达式1为假,返回表达式2

##### 		赋值运算符

```js
+=  n += 2;    等同于n=n+2;
-=
```

##### 		运算符优先级		![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210626170459702.png)

### js流程分支控制

##### 	if else分支    

```js
if (条件表达式) {
    表达式
}else {}   //条件表达式为真,执行{}内部代码.为假跳过{}执行下面代码


if (条件表达式) {
    语句1
} else if (条件表达式){
        语句2   
 }   // 条件符合1执行完1模块就退出 
```

##### 	switch    针对特定值,变量值是固定的推荐使用switch   **值必须是全等值(===)**

```js
语法结构:switch(表达式) {
		case value:
		执行语句1;
		break;
		case value:
		执行语句2;
		break;   //break不可以忘记
		.....
		default:
		最后执行的语句;
}				//表达式得值跟case后面的值相匹配,谁匹配上执行谁,都没有执行最后一句   
```



##### 	三元表达式 

​		由三元运算符组成的表达式我们叫三元表达式	

```js
语法结构   条件语句 ?  表达式1 : 表达式2   条件为true 返回表达式1 ,false返回表达式2
number > 5 ? "是的" : "不是的";
```

![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210627213307766.png)

### js循环语句

##### 	for循环 

​		目的:可以重复执行某一段代码

```js
			for( 初始化变量; 条件表达式;操作表达式) {
			/循环体
}
```



##### 	while循环

```js
//初始化变量 写在外面
while(条件表达式){
//循环体
//计数器要有,
    }


do while 循环
do{
    //循环体         //先执行代码在做判断
}while(条件表达式)   //do while至少执行一次
```




##### 断点调试   

​		控制台sourcer   选好要调试的代码 点击前面的数字刷新页面 

##### 关键字

​	

```js
	continue   //退出当前循环,继续执行下面代码

	break    //直接退出循环


```

### 数组 array

​	![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210701084046569.png)

##### 	创建数组   

​		关键字new创建

```js
var arr = new Array();
```

数组字面量创建

```js
var 数组名 = [1,2,3,];
```

##### 	索引数组

​		索引(下标) 用来访问数组元素

```js
 var arr = ["小黑","小白","小黄"];
     alert (arr[0]);  //获取数组
```

#####  	遍历数组

```js
	遍历:从头到尾访问一边数组
    var arr = [1,2,3]
    for(i= 0; i<3 ;i++) {
        console.log(arr[i]);
    }
```

##### 	数组长度:数组.length;

##### 新增数组元素

![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210701123401494.png)

##### 冒泡排序

![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210701202122643.png)

### 函数

​	函数就是封装了一段可以被重复调用的代码块.可以重复使用

##### 	函数声明和调用

```js
	function 函数名(){
        //函数体
    }
//调用  函数名+()就可以调用了 小括号里放参数
函数名();

```

##### 	函数的封装 

​		把一个或多个功能通过函数的方式封装起来,对外只提供一个简单地函数接口.

![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210701205010374.png)

![](C:\Users\王春辉\AppData\Roaming\Typora\typora-user-images\image-20210701205840946.png)

##### 函数的返回值

```js
//return
function 函数名(){
    //函数体 
    return  //返回值           函数里不可以有输出语句
}
//调用函数
函数名();   return后面不在执行后面 代码
```

