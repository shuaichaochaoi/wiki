# PHP

# 1 基本语法格式

PHP 脚本以 `<?php` 开始，以 `?>` 结束

/* */多行注释，跟java的注释方法相同

变量以 `$` 符号开始，后面跟着变量的名称。

变量名必须以字母或者下划线字符开始

变量名只能包含字母数字字符以及下划线（A-z、0-9 和 _ ）

```php
/*static的关键字的使用
  当一个函数完成时，它的所有变量通常都会被删除。
  然而，有时候您希望某个局部变量不要被删除。
  要做到这一点，请在您第一次声明变量时使用 static 关键字：
  */
function test(){
    static $n=0;
    $n++;
    echo "调用了一次".$n."\n";
}
test();test();test();
```

# 2 数据类型

php有5种数据类型：String（字符串）, Integer（整型）, Float（浮点型）, Boolean（布尔型）, Array（数组）。

其他：Object（对象）, NULL（空值）。

```php
<?php 
$a = "字符串类型";
$b = 1234;//整形
$c = -3.1415;//浮点型
$d = 8E-3;
$e = true;//boolean类型
$f = array("A","B","C");//数组类型
class obj{//php对象的声明
    var $num;
    function name() { }
}
$o = new obj();//对象实例化类型
$g = NULL;//NULL
var_dump($a);var_dump($b);var_dump($c);var_dump($d);
var_dump($e);var_dump($f);var_dump($o);var_dump($g);
?>
```

**整型**

在PHP中提供四种整形的定义方式，十进制定义，二进制定义，八进制定义和十六进制定义。

```php
// 使用echo输出时。默认输出为十进制
decbin() // 十进制转二进制
decoct() // 十进制转八进制
dechex() // 十进制转十六进制
bindec() // 二进制转十进制
bin2hex() //二进制转十六进制   
```

**字符串**：字符串变量用于存储并处理文本。

```php
<?php
$name='你好';
//双引号 里面有变量 会 输出变量的值
$str =" $name ，很高兴认识你。";
//单引号 如果里面有变量都作为一个字符串处理
$str1 =' $name ，很高兴认识你。';
echo $str;
echo $str1;

// 字符串
$text1 = "hello";
$text2 = "world";
echo $text1." ".$text2; // "."是并置运算符（连接）
echo "返回字符串的长度：", strlen($text1);
echo "返回子串l的第一次位置：", strpos($text1, "l");
?>
```

**字符的操作函数**

```php
addcslashes — 以 C 语言风格使用反斜线转义字符串中的字符
addslashes — 使用反斜线引用字符串
bin2hex — 函数把包含数据的二进制字符串转换为十六进制值
chop — rtrim 的别名
chr — 返回指定的字符
chunk_split — 将字符串分割成小块
convert_cyr_string — 将字符由一种 Cyrillic 字符转换成另一种
convert_uudecode — 解码一个 uuencode 编码的字符串
convert_uuencode — 使用 uuencode 编码一个字符串
count_chars — 返回字符串所用字符的信息
crc32 — 计算一个字符串的 crc32 多项式
crypt — 单向字符串散列
echo — 输出一个或多个字符串
explode — 使用一个字符串分割另一个字符串
fprintf — 将格式化后的字符串写入到流
get_html_translation_table — 返回使用 htmlspecialchars 和 htmlentities 后的转换表
hebrev — 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew）
hebrevc — 将逻辑顺序希伯来文（logical-Hebrew）转换为视觉顺序希伯来文（visual-Hebrew），并且转换换行符
hex2bin — 转换十六进制字符串为二进制字符串
html_entity_decode — Convert HTML entities to their corresponding characters
htmlentities — 将字符转换为 HTML 转义字符
htmlspecialchars_decode — 将特殊的 HTML 实体转换回普通字符
htmlspecialchars — 将特殊字符转换为 HTML 实体
implode — 将一个一维数组的值转化为字符串
join — 别名 implode
lcfirst — 使一个字符串的第一个字符小写
levenshtein — 计算两个字符串之间的编辑距离
localeconv — Get numeric formatting information
ltrim — 删除字符串开头的空白字符（或其他字符）
md5_file — 计算指定文件的 MD5 散列值
md5 — 计算字符串的 MD5 散列值
metaphone — Calculate the metaphone key of a string
money_format — 将数字格式化成货币字符串
nl_langinfo — Query language and locale information
nl2br — 在字符串所有新行之前插入 HTML 换行标记
number_format — 以千位分隔符方式格式化一个数字
ord — 转换字符串第一个字节为 0-255 之间的值
parse_str — 将字符串解析成多个变量
print — 输出字符串
printf — 输出格式化字符串
quoted_printable_decode — 将 quoted-printable 字符串转换为 8-bit 字符串
quoted_printable_encode — 将 8-bit 字符串转换成 quoted-printable 字符串
quotemeta — 转义元字符集
rtrim — 删除字符串末端的空白字符（或者其他字符）
setlocale — 设置地区信息
sha1_file — 计算文件的 sha1 散列值
sha1 — 计算字符串的 sha1 散列值
similar_text — 计算两个字符串的相似度
soundex — Calculate the soundex key of a string
sprintf — Return a formatted string
sscanf — 根据指定格式解析输入的字符
str_contains — Determine if a string contains a given substring
str_ends_with — Checks if a string ends with a given substring
str_getcsv — 解析 CSV 字符串为一个数组
str_ireplace — str_replace 的忽略大小写版本
str_pad — 使用另一个字符串填充字符串为指定长度
str_repeat — 重复一个字符串
str_replace — 子字符串替换
str_rot13 — 对字符串执行 ROT13 转换
str_shuffle — 随机打乱一个字符串
str_split — 将字符串转换为数组
str_starts_with — Checks if a string starts with a given substring
str_word_count — 返回字符串中单词的使用情况
strcasecmp — 二进制安全比较字符串（不区分大小写）
strchr — 别名 strstr
strcmp — 二进制安全字符串比较
strcoll — 基于区域设置的字符串比较
strcspn — 获取不匹配遮罩的起始子字符串的长度
strip_tags — 从字符串中去除 HTML 和 PHP 标记
stripcslashes — 反引用一个使用 addcslashes 转义的字符串
stripos — 查找字符串首次出现的位置（不区分大小写）
stripslashes — 反引用一个引用字符串
stristr — strstr 函数的忽略大小写版本
strlen — 获取字符串长度
strnatcasecmp — 使用“自然顺序”算法比较字符串（不区分大小写）
strnatcmp — 使用自然排序算法比较字符串
strncasecmp — 二进制安全比较字符串开头的若干个字符（不区分大小写）
strncmp — 二进制安全比较字符串开头的若干个字符
strpbrk — 在字符串中查找一组字符的任何一个字符
strpos — 查找字符串首次出现的位置
strrchr — 查找指定字符在字符串中的最后一次出现
strrev — 反转字符串
strripos — 计算指定字符串在目标字符串中最后一次出现的位置（不区分大小写）
strrpos — 计算指定字符串在目标字符串中最后一次出现的位置
strspn — 计算字符串中全部字符都存在于指定字符集合中的第一段子串的长度。
strstr — 查找字符串的首次出现
strtok — 标记分割字符串
strtolower — 将字符串转化为小写
strtoupper — 将字符串转化为大写
strtr — 转换指定字符
substr_compare — 二进制安全比较字符串（从偏移位置比较指定长度）
substr_count — 计算字串出现的次数
substr_replace — 替换字符串的子串
substr — 返回字符串的子串
trim — 去除字符串首尾处的空白字符（或者其他字符）
ucfirst — 将字符串的首字母转换为大写
ucwords — 将字符串中每个单词的首字母转换为大写
vfprintf — 将格式化字符串写入流
vprintf — 输出格式化字符串
vsprintf — 返回格式化字符串
wordwrap — 打断字符串为指定数量的字串
```



# 3 常量

**常量**：常量是一个简单值的标识符。该值在脚本中不能改变。（在整个脚本中都能使用）

一个常量由英文字母、下划线、和数字组成,但数字不能作为首字母出现。 (常量名不需要加 $ 修饰符)

设置常量，使用 define() 函数，函数语法如下：

```php
define ( string $name , mixed $value )
/*
该函数有两个参数:
name：必选参数，常量名称，即标志符。
value：必选参数，常量的值。
*/

<?php 
// 常量
define("AAAA", "这是一个全局常量");
echo AAAA;
?>
```

**预定义常量**

PHP预定义了许多常量，这些常量无需使用define()函数定义，可直接在程序中使用。下面列举了一些常用的PHP预定义常量。

（1）`__FILE__`(FILE前后分别是两个下画线)：当前正在处理的脚本文件名，若使用在一个被引用的文件中（include或require），那么　　它的值就是被引用的文件，而不是引用它的那个文件。

（2）`__LINE__`(LINE前后分别是两个下画线)：正在处理的脚本文件的当前行数。

（3）`PHP_VERSION`：当前PHP预处理器的版本，如5.4.16。

（4）`PHP_OS`: PHP所在的操作系统的类型。如Linux。

（5）`TRUE`：表示逻辑真。FALSE：表示逻辑假。NULL：表示没有值或值不确定。

（6）`DIRECTORY_SEPARATOR`: 表示目录分隔符，UNIX或Linux操作系统环境时的值为  `/` , Window操作系统环境时的值为  `\` 。

```php
<?php
echo __FILE__;
echo "<br/>";
echo __LINE__;
echo "<br/>";
echo PHP_VERSION;
echo "<br/>";
echo PHP_OS;
echo "<br/>";
echo DIRECTORY_SEPARATOR;
?>
```



# 4 控制语句

控制语法的语句结构和其他大多数语言结构相同。

## 4.1条件语句

**if** **语句** - 在条件成立时执行代码

**if...else** 语句 - 在条件成立时执行一块代码，条件不成立时执行另一块代码

**if...elseif....else** 语句 - 在若干条件之一成立时执行一个代码块

**switch** 语句 - 在若干条件之一成立时执行一个代码块

## 4.2 循环语句

**while** - 只要指定的条件成立，则循环执行代码块

**do...while** - 首先执行一次代码块，然后在指定的条件成立时重复这个循环

**for** - 循环执行代码块指定的次数

**foreach** - 根据数组中每个元素来循环代码块

**break** - 语句用于终止本次循环

**continue** - 语句的作用是跳出本次循环，接着执行下一次循环

# 5 数组

数组是一个能在单个变量中存储多个值的特殊变量。

在 PHP 中，array() 函数用于创建数组。

在 PHP 中，有三种类型的数组：

**数值数组** - 带有数字 ID 键的数组。

**关联数组** - 带有指定的键的数组，每个键关联一个值。

**多维数组** - 包含一个或多个数组的数组。

数组的声明 $array1 = array();

```php
<?php
$cars=array("Volvo","BMW","Toyota");//简单的数组
echo count($cars),"<br/>";//count()返回数组的长度
$age=array("Peter"=>"35","Ben"=>"37","Joe"=>"43");//关联数组
//其中包含多个键值对
echo "Peter is " . $age['Peter'] . " years old.","<br/>";
foreach($age as $x=>$x_value)//关联数组的遍历方法
{
    echo "Key=" . $x . ", Value=" . $x_value;
    echo "<br>";
}
?>
```

在PHP 中定义了多个数组排序的内置函数：

```php
sort() - 对数组进行升序排列

rsort() - 对数组进行降序排列

asort() - 根据关联数组的值，对数组进行升序排列

ksort() - 根据关联数组的键，对数组进行升序排列

arsort() - 根据关联数组的值，对数组进行降序排列

krsort() - 根据关联数组的键，对数组进行降序排列
```

**数组的操作**

```php
//数组的合并
$array1 = array('a','b','c');
$array2 = array('a1'=>'php','a2'=>'python','a3'=>'java');
$array3 = array_merge($array1,$array2);
print_r($array3);
echo "<br/>";

//填加数组元素
//array_push() 函数向第一个参数的数组尾部添加一个或多个元素（入栈），然后返回新数组的长度。
array_push($array1,'d','e');
print_r($array1);
echo "<br/>";
//下表为空 自动添加参数
$array1[]='d';
//有键值的
$array1['a4']='javasciprt';

//添加到指定位置
$array1 = array('a', 'b', 'c', 'd', 'e');
$array2 = array('x');
array_splice($array1, 3, 0, $array2); // 插入到位置3且删除0个
print_r($array1);
echo "<br/>";

//array_splice(数组，位置，删除几个，增加元素）
//删除某一个元素
$array1 = array('a', 'b', 'c', 'd', 'e');
$array2 = array('x');
array_splice($array1, 3, 1); 
print_r($array1);
echo "<br/>";

//unset 销毁指定的元素
$array1 = array('a', 'b', 'c', 'd', 'e');
unset($array1[0]);
print_r($array1);
echo "<br/>";

//array_pop():将数组最后一个单元弹出（出栈）
array_pop($array1);
print_r($array1);
echo "<br/>";
//修改数组中某个元素
$array1 = array('a', 'b', 'c', 'd', 'e');
$array1[0]='aa';
print_r($array1);
```

常用的数组函数

**is_array** 判断是否为数组。

**count** 数组的元素数目。

**array_search**  在数组中搜索给定的值，如果成功则返回相应的键名。

**array_key_exists()** 在给定的 key 存在于数组中时返回 TRUE。

**array_unshift()**  将传入的单元插入到 array 数组的开头，注意单元是作为整体被插入的，因此传入单元将保持同样的顺序，所有的数值键名将修改为从零开始重新计数，所有的文字键名保持不变。

**array_shift()**  将array 的第一个单元移出并作为结果返回，将 array 的长度减一并将所有其它单元向前移动一位，所有的数字键名将改为从零开始计数，文字键名将不变。

**array_unique()**  接受 array 作为输入并返回没有重复值的新数组。注意键名保留不变。 array_unique()  先将值作为字符串排序，然后对每个值只保留第一个遇到的键名，接着忽略所有后面的键名。这并不意味着在未排序的 array 中同一个值的第一个出现的键名会被保留。 

**in_array** 检查数组中是否存在某个值  如果找到指定的值则返回 TRUE，否则返回 FALSE 。in_array()是区分大小写的。

# 6 函数

PHP 的真正力量来自它的函数：它拥有超过 1000 个内建的函数。

自定义函数 必须以function开头。

语法：

```php
function functionName(形参) {

 被执行的代码;

}
注释：函数名能够以字母或下划线开头（而非数字）。

注释：函数名对大小写不敏感。
```

**PHP 函数返回值**

如需使函数返回值，使用 return 语句：

```php
<?php
function sum($x,$y) {
  $z=$x+$y;
  return $z;
}

echo "5 + 10 = " . sum(5,10) . "<br>";
echo "7 + 13 = " . sum(7,13) . "<br>";
echo "2 + 4 = " . sum(2,4);
?>
```

**匿名函数**

匿名函数就是没有名字的函数。

将一个匿名函数"赋值"给一个变量——此时该变量就代表该匿名函数了。

```php
$a=function($name){

  return $name;

};

echo $a('Qeminco');
```

**回调函数**

回调函数是指调用函数的时候将另一个函数作为参数传递到调用的函数中，而不是传递一个普通的变量作为参数。

使用回调函数是为了可以将一段自己定义的功能传到函数内部使用。

```php
function get_name($name){
    return $name;
}

echo call_user_func('get_name','Qeminco');
```

# 7 变量作用域

在 PHP 中，可以在脚本的任意位置对变量进行声明。

变量的作用域指的是变量能够被引用/使用的那部分脚本。

PHP 有三种不同的变量作用域：

local（局部）

global（全局）

static（静态）

Local 和 Global 作用域

函数之外声明的变量拥有 Global 作用域，只能在函数以外进行访问。

函数内部声明的变量拥有 LOCAL 作用域，只能在函数内部进行访问。

```php
$x=5; // 全局作用域

function myTest() {
  $y=10; // 局部作用域
  echo "<p>测试函数内部的变量：</p>";
  echo "变量 x 是：$x";
  echo "<br>";
  echo "变量 y 是：$y";
} 

myTest();

echo "<p>测试函数之外的变量：</p>";
echo "变量 x 是：$x";
echo "<br>";
echo "变量 y 是：$y";
```

注：可以在不同的函数中创建名称相同的局部变量，因为局部变量只能被在其中创建它的函数识别。

**global 关键词**

global 关键词用于在函数内访问全局变量。

要做到这一点，请在（函数内部）变量前面使用 global 关键词。

```php
$x=5;
$y=10;

function myTest() {
  global $x,$y;
  $y=$x+$y;
}

myTest();
echo $y; // 输出 15
```

**static 关键词**

通常，当函数完成/执行后，会删除所有变量。不过，有时我需要不删除某个局部变量。

要完成这一点，在首次声明变量时使用 static 关键词。

```php
function myTest() {
  static $x=0;
  echo $x;
  $x++;
}

myTest();
myTest();
myTest();
每当函数被调用时，这个变量所存储的信息都是函数最后一次被调用时所包含的信息。
注：该变量仍然是函数的局部变量。
```

# 8 类与对象

面向对象的程序设计（OOP）中，对象是一个由信息及对信息进行处理的描述所组成的整体，是对现实世界的抽象。

在现实世界里我们所面对的事情都是对象，如计算机、电视机、自行车等。

比如 Animal(动物) 是一个抽象类，我们可以具体到一只狗跟一只羊，而狗跟羊就是具体的对象，他们有颜色属性，可以写，可以跑等行为状态。

**类** − 定义了一件事物的抽象特点。类的定义包含了数据的形式以及对数据的操作。

**对象** − 是类的实例。

**成员变量** − 定义在类内部的变量。该变量的值对外是不可见的，但是可以通过成员函数访问，在类被实例化为对象后，该变量即可称为对象的属性。

**成员函数** − 定义在类的内部，可用于访问对象的数据。

**父类** − 一个类被其他类继承，可将该类称为父类，或基类，或超类。

**子类** − 一个类继承其他类称为子类，也可称为派生类。

**多态** − 多态性是指相同的操作或函数、过程可作用于多种类型的对象上并获得不同的结果。不同的对象，收到同一消息可以产生不同的结果，这种现象称为多态性。

**析构函数** − 析构函数(destructor) 与构造函数相反，当对象结束其生命周期时（例如对象所在的函数已调用完毕），系统自动执行析构函数。析构函数往往用来做"清理善后" 的工作（例如在建立对象时用new开辟了一片内存空间，应在退出前在析构函数中用delete释放）。

 ## 8.1 类的定义

使用class关键字后加上类名定义。

类的变量使用 var 来声明, 变量也可以初始化值。

类中定义的函数只能通过该类及其实例化的对象访问。

实例：

```PHP
<?php
class Person{
    //成员变量
    var $name;
    //成员函数
    function setName($name){
        $this->name=$name;
    }
}
//类的实例化，p1就是一个对象
//this表示对象的本身
$p1 = new Person();
$p1->setName('Qeminco');
echo $p1->name;
```

## 8.2 构造函数

构造函数是一种特殊的方法，主要用来在创建对象时初始化对象， 即为对象成员变量赋初始值，总与new运算符一起使用在创建对象的语句中。

关键字：`__construct`

```php
<?php
class P{
    //成员变量
    var $name;
    //成员函数
    function __construct($name){
        $this->name=$name;
    }
}

$p2 = new P('Qeminco');
echo $p2->name;
```

## 8.3 析构函数

析构函数(destructor) 与构造函数相反，当对象结束其生命周期时（例如对象所在的函数已调用完毕），系统自动执行析构函数。析构函数往往用来做"清理善后" 的工作（例如在建立对象时用new开辟了一片内存空间，应在退出前在析构函数中用delete释放）。

关键字：`__destruct`

```php
<?php
class PP{
    //成员变量
    var $name;
    //成员函数
    function __construct($name){
        $this->name=$name;
    }
    function __destruct(){
        echo $this->name;
    }
}

$p2 = new PP('Qeminco');
```

## 8.4 继承

使用关键字 extends 来继承一个类，PHP 不支持多继承。

格式：

```php
class 子类 extends 父类{
    function setName(){
        parent::setName(); //在子类函数中调用父类的同名方法,两个方法都会输出
        return "这是子类的setName()方法";
    }
}
```

**方法重写**

如果从父类继承的方法不能满足子类的需求，可以对其进行改写，这个过程叫方法的覆盖，也称为方法的重写。

也就是说子类中有跟父类同名的函数，这个子类的实例调用这个函数时，只会调用子类中的函数。

**Final 关键字**

如果父类中的方法被声明为 final，则子类无法覆盖该方法。如果一个类被声明为 final，则不能被继承。

## 8.5 访问控制

PHP 对属性或方法的访问控制，是通过在前面添加关键字 public、protected或 private来实现的。

**public**（公有）：公有的类成员可以在任何地方被访问。

**protected**（受保护）：受保护的类成员则可以被其自身以及其子类和父类访问。

**private**（私有）：私有的类成员则只能被其定义所在的类访问。

变量用 var 定义，被视为公有。方法没有使用这些关键字，默认为公有。

## 8.6 接口

使用接口（interface），可以指定某个类必须实现哪些方法，但不需要定义这些方法的具体内容。

接口是通过 interface 关键字来定义的，就像定义一个标准的类一样，但其中定义所有的方法都是空的。

接口中定义的所有方法都必须是公有，这是接口的特性。

要实现一个接口，使用 implements 操作符。类中必须实现接口中定义的所有方法，否则会报一个致命错误。类可以实现多个接口，用逗号来分隔多个接口的名称。

```php
<?php
interface Person{
    //接口中 可以使用常量 但是不能使用变量
    const NAME="这个是常量";
    public function get_name();
    public function set_name($name);
}

interface P{
    public function run();
}

class p1 implements Person,P{
    public function get_name(){

    }
    public function set_name($name){

    }
    public function run(){

    }
}
```

## 8.7 抽象类

任何一个类，如果它里面至少有一个方法是被声明为抽象的，那么这个类就必须被声明为抽象的。

定义为抽象的类不能被实例化。

被定义为抽象的方法只是声明了其调用方式（参数），不能定义其具体的功能实现。

继承一个抽象类的时候，子类必须定义父类中的所有抽象方法；另外，这些方法的访问控制必须和父类中一样（或者更为宽松）。例如某个抽象方法被声明为受保护的，那么子类中实现的方法就应该声明为受保护的或者公有的，而不能定义为私有的。

```php
<?php
//声明抽象类 abstract
//抽象类中允许有 抽象方法和方法，抽象方法不能有具体的内容，必须为空，可以允许参数
//抽象类不能实例化
abstract class Person{
    abstract protected function get_name();
    abstract protected function set_name($name);
    public function run(){
        echo "run";
    }
}
//类只能继承一个抽象类
//必须把抽象类中的方法实现
//如果抽象类中的方法是受保护的，在子类定义中可以是protected，也可以是public，不能是私有的priva
class p1 extends Person{
    public $name;
    function __construct($name){
        $this->name=$name;
    }
    public function get_name(){

    }
    public function set_name($name){
        return "set_name".$name;
    }
}
```

## 8.8Static关键字

声明类属性或方法为 static(静态)，就可以不实例化类而直接访问。

静态属性不能通过一个类已实例化的对象来访问（但静态方法可以）。

由于静态方法不需要通过对象即可调用，所以伪变量 $this 在静态方法中不可用。

静态属性不可以由对象通过 `->` 操作符来访问。

```php
<?php
//静态方法 静态变量

use Person as GlobalPerson;

class Person{
    public static $name="Qeminco";
    public static function getString(){
        return "getString";
    }
}

echo Person::$name;
echo Person::getString();
```

# 9 PHP超级全局变量

**$GLOBALS ** ：一个包含了全部变量的全局组合数组。变量的名字就是数组的键。

```php
<?php
$name="Qeminco";
print_r($GLOBALS); //print_r() 函数用于打印变量，以更容易理解的形式展示。
```

**$_SERVER** ：一个包含了诸如头信息(header)、路径(path)、以及脚本位置(script locations)等等信息的数组。

```php
<?php

foreach ($_SERVER as $k=>$value){
    echo [$k]=>$value </br>";
}
```

**$_REQUEST** ：用于收集HTML表单提交的数据。它可以获取 cookie、 get 、post 。

```php
<?php

print_r($_REQUEST);
```

在地址栏后面输入`?name=Qeminco`提交一个get表单，被获取到。

![](http://img.qianmingchao.top/img/print_r_%243.png)

获取post表单。

```php
<form method="post">
    <input name="uaername" type="text"/>
    <input value="sub" type="submit"/>
</form>
<?php
print_r($_REQUEST);
```

**$_POST** ：广泛应用于收集表单数据，在HTML form标签的指定该属性："method="post"。

```php
<form method="post">
    <input name="uaername" type="text"/>
    <input value="sub" type="submit"/>
</form>
<?php
print_r($_POST);
```

**$_GET** ：广泛应用于收集表单数据，在HTML form标签的指定该属性："method="get"。

```php
<form method="get">
    <input name="uaername" type="text"/>
    <input value="sub" type="submit"/>
</form>

<?php
print_r($_GET);
```

**$_FILES** ：文件上传。

```php
<form method="post" enctype="multipart/form-data">
    <input name="file" type="file"/>
    <input value="sub" type="submit"/>
</form>

<?php
print_r($_FILES);
?>
```



**$_ENV** ：

**$_COOKIE** ：

**$_SESSION** ：

# 10 PHP 包含文件

服务器端包含 (SSI) 用于创建可在多个页面重复使用的函数、页眉、页脚或元素。

include （或 require）语句会获取指定文件中存在的所有文本/代码/标记，并复制到使用 include 语句的文件中。

包含文件很有用，如果您需要在网站的多张页面上引用相同的 PHP、HTML 或文本的话。

**include 和 require 语句**

通过 include 或 require 语句，可以将 PHP 文件的内容插入另一个 PHP 文件（在服务器执行它之前）。

include 和 require 语句是相同的，除了错误处理方面：

require 会生成致命错误（E_COMPILE_ERROR）并停止脚本，

include 只生成警告（E_WARNING），并且脚本会继续。

因此，如果您希望继续执行，并向用户输出结果，即使包含文件已丢失，那么请使用 include。否则，在框架、CMS 或者复杂的 PHP 应用程序编程中，请始终使用 require 向执行流引用关键文件。这有助于提高应用程序的安全性和完整性，在某个关键文件意外丢失的情况下。

包含文件省去了大量的工作。这意味着您可以为所有页面创建标准页头、页脚或者菜单文件。然后，在页头需要更新时，您只需更新这个页头包含文件即可。

语法：

`include 'filename';` 

或

`require 'filename';` 

如果有一个名为 function.php 的文件，内容如下：

```PHP
<?php
function fun1(){
    return "fun1";
}
```

在 function.php 的同级目录中有 index.php 文件如下：

```php
<?
include 'function.php';  //把另一个文件包含进来
echo fun1();  //调用包含文件中的函数
```

# 11 PHP 文件处理

## 11.1 readfile()函数

`readfile()`  函数读取文件，并把它写入输出缓冲。

如读取成功则 readfile() 函数返回文本内容和字节数。

```php
<?php
echo readfile('123.txt');
?>
```

## 11.2 文件操作

### 11.2.1 打开文件

`fopen()` 函数提供了比 readfile() 函数更多的选项。

fopen() 的第一个参数包含被打开的文件名，第二个参数规定打开文件的模式。

![](http://img.qianmingchao.top/img/202206070715231.png)

```php
<?php
//如果 fopen() 函数未能打开指定的文件，则输出 Unable to open file!
$myfile = fopen("123.txt", "r") or die("Unable to open file!");
echo fread($myfile,filesize("123.txt"));
fclose($myfile);
?>
```

### 11.2.3 读取文件

`fread()` 函数读取打开的文件。

fread() 的第一个参数包含待读取文件的文件名，第二个参数规定待读取的最大字节数。

如下 PHP 代码把 "123.txt" 文件读至结尾：

```php
<?php
$myfile = fopen("123.txt", "r");
echo fread($myfile,filesize("123.txt"));
?>
```

### 11.2.3关闭文件

`fclose()` 函数用于关闭打开的文件。

用完文件后把它们全部关闭是一个良好的编程习惯。您并不想打开的文件占用您的服务器资源。

fclose() 需要待关闭文件的名称（或者存有文件名的变量）。

```php
<?php
$myfile = fopen("123.txt", "r");

// some code to be executed....

fclose($myfile);
?>
```

### 11.2.4 遍历文件

`fgets()` 函数用于从文件读取单行。

调用 fgets() 函数之后，文件指针会移动到下一行。

下例输出 "123.txt" 文件的首行：

```php
<?php
$myfile = fopen("123.txt", "r");
echo fgets($myfile);
fclose($myfile);
?>
```

`feof()` 函数检查是否已到达 "end-of-file" (EOF)文件末尾。

feof() 对于遍历未知长度的数据很有用。

下例逐行读取 "123.txt" 文件，直到 end-of-file：

```php
<?php
$myfile = fopen("123.txt", "r");
// 输出单行直到 end-of-file
while(!feof($myfile)) {
    echo fgets($myfile)."<br>";
  }  
fclose($myfile);
?>
```

`fgetc()` 函数用于从文件中读取单个字符。

在调用 fgetc() 函数之后，文件指针会移动到下一个字符。

下例逐字符读取 "123.txt" 文件，直到 end-of-file：

```php
<?php
$myfile = fopen("123.txt", "r");
// 输出单行直到 end-of-file
while(!feof($myfile)) {
    echo fgetc($myfile);
  }  
fclose($myfile);
?>
```

### 11.2.5 创建文件

`fopen()` 函数也用于创建文件。也许有点混乱，但是在 PHP 中，创建文件所用的函数与打开文件的相同。

如果用 fopen() 打开并不存在的文件，此函数会创建文件，假定文件被打开为写入（w）或增加（a）。

下面的例子创建名为 "testfile.txt" 的新文件。此文件将被创建于 PHP 代码所在的相同目录中：

```php
<?php
$myfile = fopen("testfile.txt", "w");
?>
```

### 11.2.6 写入文件

fwrite() 函数用于写入文件。

fwrite() 的第一个参数包含要写入的文件的文件名，第二个参数是被写的字符串。

下面的例子把姓名写入名为 "newfile.txt" 的新文件中：

```php
<?php
$myfile = fopen("newfile.txt", "w");
$txt = "萧炎\n";
fwrite($myfile, $txt);
$txt = "叶凡\n";
fwrite($myfile, $txt);
fclose($myfile);
?>
```

**文件覆盖（Overwriting）**

现在 "newfile.txt" 包含了一些数据，当我们再次以w模式打开文件并写入时，会清除已有的数据并写入新数据。

```php
<?php
$myfile = fopen("newfile.txt", "w");
$txt = "张三\n";
fwrite($myfile, $txt);
$txt = "李四\n";
fwrite($myfile, $txt);
fclose($myfile);
?>
```

如果现在我们打开这个 "newfile.txt" 文件，萧炎和叶凡都已消失，只剩下我们刚写入的数据张三和李四。

## 11.3 文件复制/删除/重命名

`rename(旧名,新名)` 函数重命名文件。

`copy(要复制的文件,复制文件的目的地)` 函数复制文件。

`unlink(要删除的文件)` 函数删除文件。

## 11.4 文件的判断

`file_exists(文件路径)` 函数检查文件或目录是否存在。

`is_file(要检查的文件)` 函数检查指定的文件是否是常规的文件。

# 12 PHP获取文件属性

当我们在程序中操作文件时，可能会使用到文件的一些常见属性，比如文件的大小、类型、修改时间、访问时间以及权限等等。PHP 中提供了非常全面的用来获取这些属性的内置函数，如下表所示。

![](http://img.qianmingchao.top/img/202206070711892.png)

```php
<?php
    $file = 'test.txt';
    file_exists($file) or die('文件不存在，程序退出！');

    echo $file.' 文件大小是：'.filesize($file).' 个字节<br>';
    if(is_readable($file)){
        echo $file.' 文件是可读的。<br>';
    }else{
        echo $file.' 文件是不可读的。<br>';
    }
    if(is_writable($file)){
        echo $file.' 文件是可写的。<br>';
    }else{
        echo $file.' 文件是不可写的。<br>';
    }
    if(is_executable($file)){
        echo $file.' 文件是可执行的。<br>';
    }else{
        echo $file.' 文件是不可执行的。<br>';
    }
    echo '文件的创建时间是：'.date('Y-m-d H:i:s',filectime($file)).'。<br>';
    echo '文件的修改时间是：'.date('Y-m-d H:i:s',filemtime($file)).'。<br>';
    echo '文件上次的访问时间是：'.date('Y-m-d H:i:s',fileatime($file)).'。<br>';
?>
```

# 13 PHP目录操作

新建目录：`mkdir(路径，权限，递归创建)` 

删除目录：`rmdir()` 

移动（重命名）目录：`rename(旧名,新名)` 

打开目录：`目录句柄 = opendir()` 

读取目录 ：`文件名 = readdir(目录句柄)` 

依次读取文件名，同时向下移动文件句柄指针，读取不到则返回false。

关闭目录：`closedir()` 

当前目录：`./` 

上级目录：`../` 

递归读取目录内容：

```php
<?php
//递归遍历目录
$dirfile="c:/";

function tree($dirfile){
    $dir = opendir($dirfile);
    while (($file = readdir($dir)) !== false)
    {
        if(is_dir("$dirfile{$file}") && ($file !=".") && ($file !="..")){
            if(is_readable("$dirfile{$file}")){
                echo "目录 $dirfile{$file} </br>";
                tree("$dirfile{$file}");
            }else{
                echo "目录 $dirfile{$file} 不可访问</br>";
            }

        }
        else{
            if( ($file !=".") && ($file !="..")){
                echo "文件 $dirfile/{$file} </br>";
            }

        }
    }
    closedir($dir);
}

tree($dirfile);
?>
```

 # 14 命名空间

**PHP** **命名空间可以解决以下两类问题：** 

1.用户编写的代码与PHP内部的类/函数/常量或第三方类/函数/常量之间的名字冲突。

2.为很长的标识符名称(通常是为了缓解第一类问题而定义的)创建一个别名（或简短）的名称，以提高源代码的可读性。

**命名空间（可以理解为创建文件夹）**

定义：命名空间namespace，是指人为的将内存进行分隔，让不同内存区域的同名结构共存，从而解决在大型项目中可能出现的重名结构的问题。

语法：namespace 空间名

作用：不同的空间可以有同名的结构，如：类

空间元素：函数，常量，类，不包括变量！！

**子空间（子文件夹）** 

定义：命名空间内部再划分一个命名空间，让每个小空间独立起来。

语法:

- namespace 空间名
- namespace 空间名\子空间

命名空间.php文件内容如下：

```php
<?php
namespace mydemo; //空间名为mydemo
include '子空间.php'; //导入子空间
const NAME="Qeminco_a</br>";

function getName(){
    return 'getName_a</br>';
}
class Dog{
    static function run(){
        return 'Dog_a</br>';
    }
}
echo NAME; //非限定名称，本空间名访问
echo getName(); //非限定名称，本空间名访问
echo Dog::run(); //非限定名称，本空间名访问


echo b\NAME; //限定名称访问子空间中的元素
echo b\getName(); //限定名称访问子空间中的元素
echo b\Dog::run(); //限定名称访问子空间中的元素

echo \mydemo\NAME; //完全限定名称
echo \mydemo\getName(); //完全限定名称
echo \mydemo\Dog::run(); //完全限定名称
```

子空间.php内容如下：

```php
<?php
namespace mydemo\b; //子空间为mydemo下的b空间
const NAME="Qeminco_b</br>";

function getName(){
    return 'getName_b</br>';
}
class Dog{
    static function run(){
        return 'Dog_b</br>';
    }
}
```

**命名空间访问 （url）** 

**非限定名称访问**：直接访问空间元素的名字（只访问自己命名空间的元素）。

**限定名称访问**：使用自己当前的子空间名字+ \ + 元素名字。

**完全限定名称访问**：\ + 全局空间 + \ + 元素名字。

注：任何空间元素访问，只针对函数，类，常量。

**全局空间（C盘）** 

如果定义了命名空间，非限定名称的寻找系统常量的方式：

首先：在自己的空间内找。

然后：如果找不到元素。

​    系统常量-->进入全局空间寻找。

​    系统类 --> 不会自动进入全局空间寻找，而是会报错。

**命名空间的引入** 

1.空间引入方式：use关键字

- 引入类：use 空间名\类名
- 引入函数：use function 空间名\函数名
- 引入常量：use const 空间名\常量名

2.当引入元素时重名，通过 as 来起别名

- use 空间名\类名 as 别名

```php
<?php
namespace one;
include '子空间.php';

use mydemo\b as aa;
echo aa\NAME;

use mydemo\b\Dog;
$a=new Dog();
echo $a->run();

use const mydemo\b\NAME;
echo NAME;

use function mydemo\b\getName;
echo getName();

$b=new \mydemo\b\Dog();
echo $b->run();

echo \mydemo\b\Dog::run();
```

3.引入多个元素

```
use 空间名\{
	类名，
	function 函数名，
	const 常量
}  
```

 4.引入空间

- use 空间名 

获取当前命名空间的名字使用`__NAMESPACE__` 关键字。

```php
<?php
namespace two;
function getName(){
    return __NAMESPACE__."--getName";
}
echo getName();
```



# 15 正则表达式

**正则表达式简介**

正则表达式是用于描述字符排列和匹配模式的一种语法规则。它主要用于字符串的模式分割、匹配、查找及替换操作。到目前为止，我们前面所用过的精确（文本）匹配也是一种正则表达式。

在PHP中，正则表达式一般是由正规字符和一些特殊字符（类似于通配符）联合构成的一个文本模式的程序性描述。

正则表达式较重要和较有用的角色是验证用户数据的有效性检查。

PHP中，正则表达式有三个作用：

- 匹配，也常常用于从字符串中析取信息。
- 用新文本代替匹配文本。
- 将一个字符串拆分为一组更小的信息块。

**正则表达式的基本语法**

PCRE库函数中，正则匹配模式使用分隔符与元字符组成，分隔符可以是非数字、非反斜线、非空格的任意字符。经常使用的分隔符是正斜线 `/` 、hash符号 `#` 以及取反符号 `~` 。

元字符是用于构造规则表达式的具有特殊含义的字符。如果要在正则表达式中包含元字符本身，必须在其前加上 `\` 进行转义。

| 元字符 |                   说明                    |
| :----: | :---------------------------------------: |
|   *    |       0次、1次或多次匹配其前的原子        |
|   +    |          1次或多次匹配其前的原子          |
|   ?    |          0次或1次匹配其前的原子           |
|   \|   |            匹配两个或多个选择             |
|   ^    |           匹配字符串串首的原子            |
|   $    |           匹配字符串串尾的原子            |
|   []   |          匹配方括号中的任一原子           |
|  [^]   |     匹配除方括号中的原子外的任何字符      |
|  {m}   |          表示其前原子恰好出现m次          |
| {m,n}  | 表示其前原子至少出现m次，至少出现n次(n>m) |
|  {m,}  |         表示其前原子出现不少于m次         |
|   ()   |             整体表示一个原子              |
|   .    |       匹配除换行之外的任何一个字符        |

**边界限制**

在某些情况下，需要对匹配范围进行限定，以获得更准确的匹配结果。“^”和“$”分别指定字符串的开始和结束。

例如，在字符串“Tom and Jerry chased each other in the house until tom’s uncel come in”中

元字符“^” 置于字符串的开始确保模式匹配出现在字符串首端；

^Tom   

元字符“$” 置于字符串的结束，确保模式匹配出现字符串尾端。

in$ 

如果不加边界限制元字符，将获得更多的匹配结果。

^Tom$精确匹配     Tom模糊匹配

**重复匹配**

正则表达式中有一些用于重复匹配某些原子的元字符：“?”、“*”、“+”。他们主要的不同是重复匹配的次数不同。

元字符“?”:表示0次或1次匹配紧接在其前的原子。

例如：colou?r匹配“colour”或“color”。

元字符“*”:表示0次、1次或多次匹配紧接在其前的原子。

例如：zo*可以匹配z、zoo

<[A-Za-z][A-Za-z0-9]*>可以匹配“<P>”、“<hl>”或“<Body>”等HTML标签，并且不严格的控制大小写。

元字符“+”:表示1次或多次匹配紧接在其前的原子。

例如：go+gle匹配“gogle”、“google”或“gooogle”等中间含有多个o的字符串。

例子十六进制数字，匹配表达式是0?[ xX][0-9a-fA-F]+,可以匹配“0x9B3C”或者“X800”等。

元字符 “.”

元字符“.”匹配除换行符外任何一个字符，相当于[^\n](Unix系统)或[^\r\n](windows系统)。

例如：pr.y可以匹配的字符串“prey”、“pray”或“pr%y”等。

通常可以使用“.*”组合来匹配除换行符外的任何字符。在一些书籍中也称其为“全匹配符” 或 “单含匹配符”。

例如：

^a.*z$表示可以匹配字母“a”开头，字母“z”结束的任意不包括换行符的字符串。

.+也可以完成类似的匹配功能所不同的是其至少匹配一个字符。

^a.+z$将不匹配字符串“az”。

**元字符“{}”**准确地指定原子重复的次数，指定所匹配的原子出现的次数。

“{m}”表示其前原子恰好出现m次；

“{m，n}”表示其前原子至少出现m次，至多出现n次；

“{m，}”表示其前原子出现不少于m次。

例如：

zo{1,3}m只能匹配字符串“zom”、“zoom”、或“zooom”。

zo{3}m只能匹配字符串“zooom”

zo{3，}m可以匹配以 “z” 开头，“m”结束，中间至少为3个“o”的字符串。

bo{0,1}u可以匹配字符串“bought a butter” 中的“bou”和“bu”,等价于bo?u。

**原子表 －方括号表达式**

原子表”[]”中存放一组原子，彼此地位平等，且仅匹配其中的一个原子。如果想匹配一个 ”a” 或 ”e” 使用 [ae]。

例如: Pr[ae]y 匹配 ”Pray” 或者 ”Prey ”。

原子表 ”[^]” 或者称为排除原子表，匹配除表内原子外的任意一个字符。

例如：p[^u]匹配“part”中的“pa”，但无法匹配“computer”中的“pu”因为“u”在匹配中被排除。

原子表“[-]”用于连接一组按ASCII码顺序排列的原子，简化书写。 

例如：x[0123456789]可以写成x[0-9],用来匹配一个由 “x” 字母与一个数字组成的字符串。

例如：

[a-zA-Z]匹配所有大小写字母

^[a-z][0-9]$匹配比如“z2”、 “t6” 、“g7”

0[xX][0-9a-fA-F]匹配一个简单的十六进制数字，如“0x9”。

[^0-9a-zA-Z_]匹配除英文字母、数字和下划线以外任何一个字符，其等价于\W。 

**模式选择符** 

元字符“|”又称模式选择符。在正则表达式中匹配两个或更多的选择之一。

例如：在字符串“There are many apples and pears.”中，apple|pear在第一次运行时匹配“apple”；再次运行时匹配“ pear”。也可以继续增加选项，如：    apple|pear|banana|lemon

POSIX风格预定义的正则表达式的字符类：

   [[:alnum:]]    字母和数字字符

   [[:alpha:]]      大小写字母

   [[:lower:]]      小写字母

   [[:upper:]]      大写字母

   [[:digit:]]       数字0-9

   [[:xdigit:]]      十六进制数字

   [[:punct:]]      标点符号，包括上档键!@

   [[:blank:]]      TAB制表符和空格

   [[:space:]]      任何空白字符,换行,回车符

   [[:cntrl:]]       控制字符（TAB，退格）

**模式单元** 

元字符“（）”将其中的正则表达式变为原子（或称模式单元）使用。与数学表达式中的括号类似，“（）”可以做一个单元被单独使用。

例如：

(Dog)+匹配的“Dog”、“DogDog”、“DogDogDog”……..,因为紧接着“+”前的原子是元字符“（）”括起来的字符串“Dog”。

You (very)+ old匹配“You very old”、 “You very very old”

Hello (world|earth)匹配“Hello world”、“Hello earth”

一个模式单元中的表达式将被优先匹配或运算

# 16 PHP与Mysql

PHP 5 及以上版本建议使用以下方式连接 MySQL :

- MySQLi extension ("i" 意为 improved)
- PDO (PHP Data Objects)

 PDO 应用在 12 种不同数据库中， MySQLi 只针对 MySQL 数据库。

两者都是面向对象, 但 MySQLi 还提供了 API 接口。

两者都支持预处理语句。 预处理语句可以防止 SQL 注入，对于 web 项目的安全性是非常重要的。

实例：

Mysqli连接，面向对象

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";

//创建连接
$conn=new mysqli($servername,$username,$password);

//检测连接
if($conn->connect_error){
    //如果连接失败，输出错误信息
    echo "mysqli_error".$conn->connect_error;
}else{
    //如果连接成功，输出成功信息
    echo "mysqli_connect successful</br>";
}
//创建数据库
$sql = "CREATE DATABASE mydb";
if ($conn->query($sql) === TRUE){
    //query()执行变量$sql中的SQL语句，结果为true输出成功信息
    echo "Database create successfully";
}else{
    echo "Error creating database: ".$conn->error;
}
$conn->close(); //关闭连接
```

Mysqli连接，面向过程

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";

//创建连接
$conn=mysqli_connect($servername,$username,$password);

//检测连接
if($conn->connect_error){
    //如果连接失败，输出错误信息
    echo "mysqli_error".$conn->connect_error;
}else{
    //如果连接成功，输出成功信息
    echo "mysqli_connect successful";
}
mysqli_close($conn); //关闭连接
```

PDO连接

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";

//创建连接
try{
    $conn=new PDO("mysql:host=$servername;dbname=myDB",$username,$password);
    echo "Connected successfuly";
}

catch(PDOException $e){
    echo $e->getMessage();
}
$conn = null; //关闭连接
```

**创建表** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful";
}
//创建表
$sql = "CREATE TABLE user(
    id INT(6) UNSIGNDE AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(30) NOT NULL,
    password VARCHAR(30) NOT NULL,
    email VARCHAR(50)
);";
if($conn->query($sql) === TRUE){
    echo "table create successfully";
}else{
    echo "Error creating table: ".$conn->error;
}
```

**向表中插入数据** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful</br>";
}
//向表插入内容
$sql = "INSERT INTO user (username,password,email) VALUES ('Qeminco','123456','123456@qq.com')";
if($conn->query($sql) === TRUE){
    echo "Insert successfully!";
}else{
    echo "Error creating insert: ".$conn->error;
}
```

**查询数据** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful</br>";
}
//查询数据
$sql = "select * from user";
$result = $conn->query($sql);
while($row = $result->fetch_assoc()){ //fetch_assoc()函数从结果集里取得一行作为关联数组
    echo $row["id"].$row["username"].$row["password"].$row["email"]."</br>";
}
```

**另一种查询** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful</br>";
}
//查询数据
$sql = "select * from user where id=".$_GET['id'];
$result = $conn->query($sql);
while($row = $result->fetch_assoc()){ //fetch_assoc()函数从结果集里取得一行作为关联数组
    echo $row["id"].$row["username"].$row["password"].$row["email"]."</br>";
}
```

此时需要在网址栏添加 `?id=` ,填1就会出现id为1的数据。

![](http://img.qianmingchao.top/img/202206070712183.png)

存在注入

![](http://img.qianmingchao.top/img/202206070714963.png)

**删除数据** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful</br>";
}
//删除数据
$sql = "DELETE FROM user where id=".$_GET['id'];
if($conn->query($sql) === true){
    echo "删除成功！";
}else{
    echo "删除失败！";
}
```

**更新数据** 

```php
<?php
$servername = "localhost";
$username = "root";
$password = "root";
$dbname = "mydb";

//连接数据库
$conn=new mysqli($servername,$username,$password,$dbname);
if($conn->connect_error){
    echo "mysqli_error".$conn->connect_error;
}else{
    echo "mysqli_connect successful</br>";
}
//删除数据
$sql = "update user set username='zhangsan' where id=1";
if($conn->query($sql) === true){
    echo "update successfully!";
}else{
    echo "Error update: ".$conn->error;
}
```

