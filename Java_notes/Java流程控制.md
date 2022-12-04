#### 输出

* `System.out.println()`输出换行
* ` System.out.print()` 输出不换行 
* `System.out.printf("%.2f\n", d) //显示两位小数` 格式化输出

| 占位符 | 说明                             |
| ------ | -------------------------------- |
| %d     | 格式化输出整数                   |
| %x     | 格式化输出十六进制整数           |
| %f     | 格式化输出浮点数                 |
| %e     | 格式化输出科学计数法表示的浮点数 |

------

#### 输入

~~~java
Scanner scanner = new Scanner(System.in);// 创建Scanner对象
 String name = scanner.nextLine(); // 读取一行输入并获取字符
int age = scanner.nextInt(); // 读取一行输入并获取整数
~~~

执行流程：

创建`Scanner`对象并传入`System.in`。`System.out`代表标准输出流，而`System.in`代表标准输入流。

Java提供Scanner对象来方便输入，读取对应的类型可以使用：`scanner.nextLine()` / `nextInt()` / `nextDouble()` / ...

------

#### if

`if ... else`可以做条件判断，`else`是可选的；

不推荐省略花括号`{}`；

多个`if ... else`串联要特别注意判断顺序；

要注意`if`的边界条件；

要注意浮点数判断相等不能直接用`==`运算符；

引用类型判断内容相等要使用`equals()`，注意避免`NullPointerException`。

------

#### switch

`switch`语句可以做多重选择，然后执行匹配的`case`语句后续代码；

`switch`的计算结果必须是整型、字符串或枚举类型；

注意千万不要漏写`break`，建议打开`fall-through`警告；

总是写上`default`，建议打开`missing default`警告；

! 新语法使用`->`，如果有多条语句，需要用`{}`括起来。不要写`break`语句，因为新语法只会执行匹配的语句，没有穿透效应

从Java 14开始，`switch`语句正式升级为表达式，不再需要`break`，并且允许使用`yield`返回值。
