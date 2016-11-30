# PHP基础语法
没想到，搞了半天，我还是要学php，QAQ

<h3>php的八种数据类型</h3>

var_dump()函数获取数据类型

四种标量类型

布尔类型（boolean） true false

整型（integer）  $num=666;

浮点型（浮点数、双精度数或实数 float） $num_float = 1.234; 

字符串（chart） $str_string1 = 'ilice';

    字符串PS

    字符串中包含引号的时候 1：在单引号中嵌入双引号；2：在双引号中嵌入单引号；3：使用转义符“\”；

    当引号里有$时，双引号解析变量，单引号不解析变量，

    字符串很长时
```php
<?php 
//标识符GOD可以自定义
$string1 = <<<GOD

我有一根小鸡鸡，我从来也不洗。

有一天我心血来潮，急着去搞基。

我手里拿着小鸡鸡，我心里正得意。

不知怎么哗啦啦啦啦，我射了一身泥.

GOD;
echo $string1;

?>
```
两种特殊类型

resource　（资源）

NULL　（NULL）

两种复合类型：

array （数组）

object （对象）


<h3>php常量</h3>
```
<?php
$p = "PII";
define("PI",3.14);
define($p,3.14);
echo PI;
echo "<br />";
echo PII;
?>
```
result
```
3.14
3.14
```
<h3>PHP的系统常量</h3>
（1）__FILE__ :php程序文件名。它可以帮助我们获取当前文件在服务器的物理位置。

（2）__LINE__ :PHP程序文件行数。它可以告诉我们，当前代码在第几行。

（3）PHP_VERSION:当前解析器的版本号。它可以告诉我们当前PHP解析器的版本号，我们可以提前知道我们的PHP代码是否可被该PHP解析器解析。

（4）PHP_OS：执行当前PHP版本的操作系统名称。它可以告诉我们服务器所用的操作系统名称，我们可以根据该操作系统优化我们的代码。

<h3>PHP-如何判定常量是否被定义</h3>

defined()函数可以帮助我们判断一个常量是否已经定义，其语法格式为：
```
bool defined(string constants_name)   //返回一个布尔值
```
<h3>php的赋值运算符</h3>

$b = $a;   //赋值

$c = &$a;  //引用
```php
<?php 
    $a = "我在慕课网学习PHP！";
	$b=$a;
	$c=&$a;
	$a = "我天天在慕课网学习PHP！";
	
	echo $b."<br />";
	echo $c."<br />";
?>
```
result
```
我在慕课网学习PHP！
我天天在慕课网学习PHP！
```
“==”等于 $a=$b 如果$a等于$b，

“===”全等于 $a===$b 如果$a等于$b，并且它们的类型也相同，返回TRUE

“!=” 不等 $a!=$b 如果$a!=$b,

“<>” 不等 $a<>$b 如果$a不等$b,返回TRUE

“!==”非全等 $a!==$b 如果$a不等于$b,或者它们的类型不同，返回TRUE

“>” 大于 $a>$b 如果$a大于$b,返回TRUE

“<” 小于 $a<$b 如果$a小于$b，返回TRUE

“<=”小于等于 $a<=$b 如果$a小于或等于$b 返回true

“>=”大于等于 $a>=$b 如果$a大于或者等于$b 返回TURE

<h3>PHP中的字符串连接运算符</h3>
```
<?php
    $a = "先生您好";
	$tip = $a."欢迎您光临红浪漫！";
    $b = "拖鞋手牌拿好";	
    $b .= "上楼请右转";
?>
```



<h2>数组</h2>
数组种类：索引数组，关联数组

<h3>php索引数组循环</h3>
for循环
```php
<?php
$fruit=array('苹果','香蕉','菠萝');
for($i=0;$i<3;$i++){
  echo $fruit[$i];
}
?>
```
foreach循环访问索引数组里的值
```php
<?php
$fruit=array('苹果','香蕉','菠萝');
foreach($fruit as $key=>$value){
    echo $key.'：'.$value.'<br>';
}

?>
```
<h3>PHP数组之关联数组初始化</h3>

关联数组是指数组的键是字符串的数组

$fruit = array(

    'apple'=>"苹果",

    'banana'=>"香蕉",

    'pineapple'=>"菠萝"

); 
```php
<?php
$fruit=array('apple'=>"苹果",'banana'=>"香蕉",'pineapple'=>"菠萝");
foreach($fruit as $key=>$value){
    echo '<br>键是：'.$key.'，对应的值是：'.$value;
}
?>
```

<h3>php类class</h3>
```php
class Car {
    //定义公共属性
    public $name = '汽车';

    //定义受保护的属性
    protected $corlor = '白色';

    //定义私有属性
    private $price = '100000';
}
//受保护的继承后可以访问，私有的只能在该类中访问，不会被继承访问

```
<h3>PHP类和对象之构造函数和析构函数</h3>

PHP5可以在类中使用__construct() 定义一个构造函数，

具有构造函数的类，会在每次对象创建的时候调用该函数，因此常用来在对象创建的时候进行一些初始化工作。

```php
class Car {
   function __construct() {
       print "构造函数被调用\n";
   }
}
$car = new Car(); //实例化的时候 会自动调用构造函数__construct，这里会输出一个字符串
```
```php
//在子类中如果定义了__construct则不会调用父类的__construct，如果需要同时调用父类的构造函数，需要使用parent::__construct()显式的调用。

class Car {
   function __construct() {
       print "父类构造函数被调用\n";
   }
}
class Truck extends Car {
   function __construct() {
       print "子类构造函数被调用\n";
       parent::__construct();
   }
}
$car = new Truck();
```
PHP5支持析构函数，使用__destruct()  

进行定义，析构函数指的是当某个对象的所有引用被删除，或者对象被显式的销毁时会执行的函数。

```php
class Car {
   function __construct() {
       print "构造函数被调用 \n";
   }
   function __destruct() {
       print "析构函数被调用 \n";
   }
}
$car = new Car(); //实例化时会调用构造函数
echo '使用后，准备销毁car对象 \n';
unset($car); //销毁时会调用析构函数
```
<h3>PHP类和对象之Static静态关键字</h3>

静态属性与方法可以在不实例化类的情况下调用，直接使用类名::方法名的方式进行调用。

静态属性不允许对象使用->操作符调用。

```php

class Car {
    private static $speed = 10;
    
    public static function getSpeed() {
        return self::$speed;
    }
}
echo Car::getSpeed();  //调用静态方法

```
```php
//静态方法中，$this伪变量不允许使用。可以使用self，parent，static在内部调用静态方法与属性。


class Car {
    private static $speed = 10;
    
    public static function getSpeed() {
        return self::$speed;
    }
    
    public static function speedUp() {
        return self::$speed+=10;
    }
}
class BigCar extends Car {
    public static function start() {
        parent::speedUp();
    }
}
BigCar::start();
echo BigCar::getSpeed();
```































