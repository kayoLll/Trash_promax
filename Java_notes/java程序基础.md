#### 变量

在java中 变量分为两种：基本类型的变量和引用类型的变量

变量必须先定义后使用 在定义变量时需要给它赋上一个初始值；跟别的语言一样 假设我们定义了一个变量 此时我们不能重复定义一个同名的变量 不然程序会出错 但变量可以重新赋值甚至赋给别的变量

~~~java
int a =100;
System.out.println(a);  //100
a=200
int b = a; //b=200
~~~

程序执行流程：

执行`int a = 100;`，该语句定义了变量`a`，同时赋值为`100`，因此，JVM在内存中为变量`a`分配一个“存储单元”，填入值`100`：

```ascii
      a
      │
      ▼
┌───┬───┬───┬───┬───┬───┬───┐
│   │100│   │   │   │   │   │
└───┴───┴───┴───┴───┴───┴───┘
```

执行`a = 200;`时，JVM把`200`写入变量`a`的存储单元，因此，原有的值被覆盖，现在`a`的值为`200`：

```ascii
      a
      │
      ▼
┌───┬───┬───┬───┬───┬───┬───┐
│   │200│   │   │   │   │   │
└───┴───┴───┴───┴───┴───┴───┘
```

执行`int b = a;`时，定义了一个新的变量`b`，同时对`b`赋值，因此，JVM需要*新分配*一个存储单元给变量`b`，并写入和变量`a`一样的值，结果是变量`b`的值也变为`200`：

```ascii
      a           b
      │           │
      ▼           ▼
┌───┬───┬───┬───┬───┬───┬───┐
│   │200│   │   │200│   │   │
└───┴───┴───┴───┴───┴───┴───┘
```

(等号为赋值号 并不是数学意义上的等号  这里可以理解为把右边表达式的值赋给左边的变量)

------

#### 基本数据类型

基本数据类型就是CPU可以直接进行运算的类型

- 整数类型：byte(1字节=8位二进制数=8bit)，short(2)，int(4)，long(8)

  表示范围：

  - byte：-128 ~ 127
  - short: -32768 ~ 32767
  - int: -2147483648 ~ 2147483647
  - long: -9223372036854775808 ~ 9223372036854775807

- 浮点数类型：float(4)，double(8)

  浮点数顾名思义就是小数

  浮点数可表示的范围非常大，

  * `float`类型可最大表示3.4x1038
  * `double`类型可最大表示1.79x10308

- 字符类型：char(2)

  字符类型使用单引号*‘* 且仅有一个字符 要和字符串类型string区分开

- 布尔类型：boolean

  布尔类型字节数不确定

  只有true和false两个值

------

#### 引用类型

除基本类型外的变量 都是引用类型  最常见` String` 类型

引用类型的变量类似C语言的指针，它的内部存储一个地址，指向某个对象在内存的位置

------

#### 常量

定义变量的时候，如果加上`final`修饰符，这个变量就变成了常量

常量在定义时进行初始化后就不可以再次赋值，否则会导致编译错误

------

####  运算优先级

在Java的计算表达式中，运算优先级从高到低依次是：

- `()`
- `!` `~` `++` `--`
- `*` `/` `%`
- `+` `-`
- `<<` `>>` `>>>`
- `&`
- `|`
- `+=` `-=` `*=` `/=`

记不住也没关系，只需要加括号就可以保证运算的优先级正确

------

**整数运算的结果永远是精确的**；

运算结果会自动提升；

可以强制转型，但超出范围的强制转型会得到错误的结果；

应该选择合适范围的整型（`int`或`long`），没有必要为了节省内存而使用`byte`和`short`进行整数运算。

**浮点数常常无法精确表示**，并且浮点数的运算结果可能有误差；

比较两个浮点数通常比较它们的差的绝对值是否小于一个特定值；

整型和浮点型运算时，整型会自动提升为浮点型；

可以将浮点型强制转为整型，但超出范围后将始终返回整型的最大值。

**布尔运算是一种关系运算**，包括以下几类：

- 比较运算符：`>`，`>=`，`<`，`<=`，`==`，`!=`
- 与运算 `&&`
- 或运算 `||`
- 非运算 `!`

------

### 字符串

字符串` String`是引用类型 用`" "`表示一个字符串，一个字符串可以存储0个到任意个字符

**Java 的字符串池属于 JVM 专门给指定的特殊内存区域，用来存储字符串字面量**

记重点！

Java的**字符串不可变**

```ascii
String s = "hello"
执行过程：
在创建字符串时 JVM虚拟机先创建字符串 “hello" 然后把字符串变量指向这个“hello"
    s
      │
      ▼
┌───┬───────────┬───┐
│   │  "hello"  │   │
└───┴───────────┴───┘

String s = "world"

此时 JVM虚拟机分配内存进行创建字符串“world” 然后再把s指向这个"world"
   s ──────────────┐
                      │
                      ▼
┌───┬───────────┬───┬───────────┬───┐
│   │  "hello"  │   │  "world"  │   │
└───┴───────────┴───┴───────────┴───┘
(此时hello这个字符串还在 只是无法通过变量s访问它而已， 它不像基本类型那样直接在原来的存储空间上直接覆盖，因此，字符串的不可变是指字符串内容不可变（无法从存储位置上改变）。 )


```

在Java中，我们通常有两种方式创建字符串对象，一种是通过字符串字面量方式创建，就如上文的代码，另外一种就是通过 new 方式去创建，如 `String c = new String("string 3");` 而两者区别就在于通过字符串字面量的方式创建时，JVM 会现在字符串池中检查字符串内容是否已经存在，如果存在就会直接返回对应的引用，而不是再次分配内存进行创建，如果不存在就会分配在内存中创建的同时将字符串数据缓存在字符串池中，便于重用。正是是由于字符串的不可变，同样的字符串内容可以让 JVM 可以减少额外的内存分配操作，直接使用在字符串池中字符串对象即可，对性能提升和内存节省都大有好处。

![img](https://typora-1309585281.cos.ap-guangzhou.myqcloud.com/img/e2iixi0qm0.jpeg)

------

### 数组

* 数组是同一数据类型的集合，数组一旦创建后，大小就不可变；

` int[] ns = new int[5]` //创建长度为5的数组   

` ns.length = 5` 

* 可以通过索引访问数组元素，但索引超出范围将报错；

* 数组元素可以是值类型（如int）或引用类型（如String），但数组本身是引用类型；  //把它跟String机制类比