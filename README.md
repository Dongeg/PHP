# PHP
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





















