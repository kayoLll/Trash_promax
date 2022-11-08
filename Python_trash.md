[TOC]



## 字符串

[字符串基本操作](https://www.runoob.com/python/python-strings.html)

------

## Third

#### 列表

* 列表由一系列按特定排序的元素组成
* 用[ ] 来表示列表  逗号分隔其他元素

<!--类似C++的数组 通过索引访问 第一个元素索引为0-->



##### 1.列表基本操作

修改

~~~python
motorcycles = ['honda', 'yamaha', 'suzuki'] 
print(motorcycles) 
motorcycles[0] = 'ducati' 
print(motorcycles)    #通过索引位置修改
~~~

添加

* 在列表末尾添加

> .append（**value**）   value 为要插入的值

+ 插入元素

> .insert (**index, value**)    index为插入位置  value为要插入的值

~~~python
names = ['zky']
names.append('lxl')   
# ['zky','lxl']
names.insert(0,'lxl')
# ['lxl','zky']
~~~

查找索引

* list.index(value)  如果值在list中 则返回值对应的下标

删除

* 用**del**语句删除

> **del** + list[index ]   index 为元素索引

~~~python
 del names[0]
# del 可以删除列表所有的元素 条件是知道其索引
~~~

* **pop()**

> 弹出元素  类似于栈 弹出的值可以被访问到 也可加入索引弹出指定位置的值

* **remove（）**

> 根据值删除元素 只需知道值 不需要知道索引 .remove(**value** )
>
> **注意** ！此方法只删除第一个指定值  如列表中出现多次 需要配合循环判断才能 

~~~python
names = ['zky','lxl']
names_poped = names.pop(0)   
print(names)   #lxl   
print(names_poped)  #zky
~~~

##### 2.列表组织

* sort()方法排序         <u>永久性</u>

> 调用方法 ： 列表 . sort()   括号里可以加参数 **reverse=True** 可以输出相反的顺序

<!--此方法对数组的改变是永久性的 及排序后 再次打印时数组 时 打印出结果是为排序后的数组-->

* sorted(list)排序         <u>临时性</u>

> 也可以加参数 此函数不会改变列表元素的排列顺序  可以用一个临时列表存储方便使用  同样 此函数也可以加参数 让元素倒序

* reverse（）方法       <u>永久性</u>

> 此方法仅把列表反转 跟元素大小 字母排序无关 仅仅反转！！！



##### 3.列表长度

* 函数len() 可快速获悉列表的长度  即返回长度值

~~~python
names = [1,2,3,4,5]
len(names)
print   # 5
~~~

------

## Fourth

#### 操作列表

##### 1.遍历链表

* for循环

> 1.编写for循环时，对于用于存储列表中每个值的临时变量，可指定任何名称。然而， 选择描述单个列表元素的有意义的名称大有帮助。
>
> 2.在for循环中一定要注意缩进 避免不必要缩进带来的逻辑错误

~~~python
magicians = ['alice', 'david', 'carolina']
for magician in magicians: 
 print(magician.title() + ", that was a great trick!")
 print("I can't wait to see your next trick, " + magician.title() + ".\n")

 print("Thank you, everyone. That was a great magic show!") 
~~~

##### 2.数字列表

range()函数能够生成一系列数字 常在for循环中使用

* range()还能有第三个参数 用于指定步长 即每生成一个数比前一个数多几

~~~python
range(vaule,value_2)
# 生成从value 到value_2-1的整数
~~~

list()可以将range()生成的数字转换为列表

>list() 方法用于将元组转换为列表。
>
>语法：
>
>```python
>list( tup )
>```

* 数字列表统计计算

~~~python
digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
min(digits)  # 找最小
0 
max(digits)  # 最大
9 
sum(digits) # 总和
45 
~~~

##### 3.切片

创建切片需要指定使用的第一个元素和最后一个元素的索引

* 如果没有指定第一个索引，python将自动从列表开头开始
* 如没有指定结束索引，将自动提取到末尾

遍历切片同样使用**for**循环

##### 4.复制列表
创建一个包含整个列表的切片，方法同时省略起始和终止索引**([:])**

> 如果只是简单的把列表赋给另外一个列表，这样两个变量都指向同一个列表

##### 5.元组

元组跟列表极其相似 当列表中的元素可以修改 但元组中的元素是不可以修改的  即 **不可变的列表被称为元组**

~~~python
#定义元组
dimesions = (200,50)
#使用圆括号而不是方括号
#不可以修改元组 但给元组表量重新赋值是合法的
~~~

##### 6.列表解析

指定一个描述性的列表名 指定一个左方括号， 并定义一个表达式，用于生成你要存储到列表中的值。编写一个for循环，用于给表达式提供值，再加上右方括号。  

**for 语句末尾没有冒号。**

------

## Fifth

##### if语句

~~~python
#if-elif-else结构语法
if conditions:
    do something
elif conditions:
    do something
else:
    do something
~~~

如果使用if语句要检查多个条件 

1. 使用**and**

用于检查两个条件是否都为True 都满足则通过测试

2. 使用**or**

**or**可以检查多个条件 只要至少有一个条件满足就能通过整个测试 仅当都没通过时 **or**的表达式才为false

* if语句中将列表名用在条件表达式中时，python将在列表至少包含一个元素时返回True，在列表为空的时候返回False 

------

## Sixth

#### 字典

##### 1.使用字典

字典是一系列键-值对，键-值对是两个相关联的值

指定键时 将返回与之相关联的值

~~~python
alien_0 = {'color':'green'}
#键值之间用冒号分隔 对之间用逗号隔开 键名称要加''
#定义字典用花括号

#访问字典中的值
alien_0['键名称']  # 返回对应的值

~~~

##### 2.添加键—值对

**字典是一种动态结构，可随时在其中添加键—值对。要添加键—值对，可依次指定字典名、用 方括号括起的键和相关联的值。**

* 使用字典来存储用户提供的数据或在编写能自动生成大量键-值对的代码时 通常都需要先定义一个空字典

##### 3.修改键值对

要修改字典中的值，可依次指定字典名、用方括号括起的键以及与该键相关联的新值。

~~~python
alien_0 = {'color': 'green'} 
print("The alien is " + alien_0['color'] + ".") 
alien_0['color'] = 'yellow' 
print("The alien is now " + alien_0['color'] + ".") 

#The alien is green. 
#The alien is now yellow.
~~~

##### 4.删除键--值对

对于字典中不要的信息 可以使用**del**语句将相应的键 值对彻底删除  使用**del**语句时 必须指定字典名和要删除的键

##### 5.遍历键对值

* 所有键--值对

> for key,value in **dictionary.items()**
>
> 方法item() 返回一个键-值对列表
>
> * 遍历字典时，键—值对的返回顺序也与存储顺序不同。Python不关心键—值对的存 储顺序，而只跟踪键和值之间的关联关系

* 所有键

> for key in **dictionary.keys()**
>
> 方法keys()返回一个列表，其中包含字典中的所有键
>
> 如需按顺序遍历所有的键 则在前面加**sorted（————）**



* 所有值

> for key in **dictionary.values()**
>
> 方法values()返回一个值列表，而不包含 任何键
>
> 如需剔除重复我们可以使用集合set()

> ~~~python
> set(favourite_languages.values())
> #集合类似于链表 但没个元素都是独一无二的
> ~~~

##### 6.嵌套

* 在列表中存字典

~~~python
# 创建一个用于存储外星人的空列表
aliens = [] 
# 创建30个绿色的外星人
for alien_number in range (0,30):
     new_alien = {'color': 'green', 'points': 5, 'speed': 'slow'} 
     aliens.append(new_alien)
   
#通过遍历列表切片访问
~~~

* 在字典中存列表

~~~python
# 存储所点比萨的信息
pizza = { 
 'crust': 'thick', 
 'toppings': ['mushrooms', 'extra cheese'], 
 }

~~~



* 在字典中存字典

~~~python
users = { 
 'aeinstein': { 
 'first': 'albert', 
 'last': 'einstein', 
 'location': 'princeton', 
 }, 
 'mcurie': { 
 'first': 'marie', 
 'last': 'curie', 
 'location': 'paris', 
 }, 
 }
 for username, user_info in users.items(): 
	print("\nUsername: " + username) 
	full_name = user_info['first'] + " " + user_info['last'] 
 	location = user_info['location'] 
	print("\tFull name: " + full_name.title()) 
 	print("\tLocation: " + location.title()) 
~~~

<!--列表和字典的嵌套层级不应太多-->。

------

## 7th

#### function

函数定义  def  function_name(形参)

实参是调用函数时传递给函数的信息  

形参就是函数定义中的变量 

* 函数调用时可能包括多个实参 ，每个实参都关联到函数定义中的一个形参  因此传递参数变得尤其重要 、
* 传递实参有很多方式

1. 位置实参  即要传递实参的位置 与其对应的形参位置一一对应
2. 关键字实参 相当于传递给函数的名称-值对  ：形参=‘要传递的实参’
3. 默认值  给每个形参设置一个默认值  如调用函数时没有给该形参提供实参时  就会使用该形参的默认值

##### 返回值

函数可以用于处理一些数据并返回一个或一组值  

* 使用return语句返回到调用函数的代码行
* 函数可返回任何类型的值，包括列表和字典等较复杂的数据结构

##### 传递列表

在函数中 可以向函数传递列表  

* 函数中对列表所做的任何修改都是永久性的
* 如不想函数修改列表 可使用**切片**向函数拷贝一个一样的数组 让函数使用现成的列表可避免花时间和内存创建副本 提高效率

##### 传递任意数量的实参

在事先不知道的时候， python允许函数从调用语句中收集任意数量的实参

~~~python
def make_pizza(*toppings): 
 """打印顾客点的所有配料""" 
 print(toppings) 
 for topping in toppings: 
 	print("- " + topping) v
 
make_pizza('pepperoni') 
make_pizza('mushrooms', 'green peppers', 'extra cheese')
~~~

> 形参名*toppings中的星号让Python创建一个名为toppings的空元组，并将收到的所有值都封 装到这个元组中。

##### 结合使用位置实参

* 如果要让函数接受不同类型的实参，必须在函数定义中将接纳任意数量实参的形参放在最 后。Python先匹配位置实参和关键字实参，再将余下的实参都收集到最后一个形参中。

~~~python
def make_pizza(size, *toppings): 
~~~

##### 使用任意数量的关键字实参

在需要接受任意数量的实参 但预先不知道要给函数传递什么信息时 可将函数编写成能够接受任意数量的键-值对——调用语句提供多少就接受多少

~~~python
def build_profile(first,last,**user_info):
    # 这里是两个*号 区别于接收预先知道什么信息但不知道数量时传实参时的一个*号
    for key,value in user_info.items()
    
# 调用方式
build_profile(' ',' ',test=' ')
~~~

##### 模块

所谓的模块 用于把代码块与主程序分离  使得程序的逻辑结构更加清晰

* 将函数存储在被称为模块的独立文件中 再将模块导入到主程序中
* 通过**improt** 语句导入

导入步骤：

1. 创建模块  即创造python文件
2. 用import 语句导入要使用的模块

导入的模块其中的所有函数都被复制到当前程序中

~~~python
import module_name # 导入整个模块
from module_name import function_0, function_1, function_ # 导入特定函数
# 可用as给函数指定别名
from module_name import function_0 as fn
# 用as给模块指定别名
import module_name as mn 
# 只是模块名字在这个程序中发生了变化 模块内的函数名称都没有变化

# 导入模块中的所有函数(尽量不要用 容易造成不好的后果)
from module_name import *

~~~

------

## 8th_类

####  1.方法 _init__()

类中的函数称为方法

方法_init__()为类中的构造函数 每次根据类创建新实例时，python都会自动运行它 

* 在这个方法中 **self** 参数必不可少 还必须位于最前面 
* 因为 Python调用这个__init__()方法来创建实例时，将自动传入实参self。每个与类相关联的方法 调用都自动传递实参self，**它是一个指向实例本身的引用**，让实例能够访问类中的属性和方法。
* **以self为前缀的变量都可供类中的所有方法使用**，我们 还可以通过类的任何实例来访问这些变量。
* self.name = name 获取存储在形参name中的值 并将 其存储到变量name中，然后该变量被关联到当前创建的实例。 这种通过实例访问的变量称为属性

~~~python
class ClassName(object): 
 --snip--
class_name = ClassName('willie',6)
# 调用属性和调用方法都用句点表示法
class_name.func   / class_name.name 

# 可以创建多个实例
~~~

#### 2.在——init()_内指定定义属性

在方法__init()_定义属性是可以的 这样这个属性无需提供初始值的形参

~~~python
def __init__(self, make, model, year): 
 """初始化描述汽车的属性""" 
 self.make = make 
 self.model = model 
 self.year = year
 self.odometer_reading = 0 
~~~

#### 3. 修改属性的值

* 直接通过实例修改

* 通过方法修改属性值

* ~~~python
  def update_odometer(self, mileage): 
   """将里程表读数设置为指定的值""" 
   self.odometer_reading = mileage
  ~~~

#### 4.继承

一个类继承另一个类时，它将自动获得另一个类的所有属性和方法；子类继承了其父类的所有属性和方法，同时还可以定义自己的属性和方法

1. 子类的方法__init__()

创建子类实例，首先需要给父类所有的属性赋值

~~~~python
class Car():
 
class ElectricCar(Car):   # Car父类的名字 创建子类时父类一定要包含在当前文件中 且位于子类前面
 """电动汽车的独特之处""" 
 
def __init__(self, make, model, year): 
 """初始化父类的属性""" 
super().__init__(make, model, year) 
 # super() 用于将父类和子类关联起来  调用父类的方法__init()__ 让子类实例包含父类的所有属性
# 父类也称为超类
# 子类可以调用父类中定义的方法 也可以自己定义属于自己的新属性和方法
# 对于父类的方法 都可进行重写 子类只需定义一个与要重写的父类同名的方法即可 程序不会将这个方法考虑为父类的方法
my_tesla = ElectricCar('tesla', 'model s', 2016) 
print(my_tesla.get_descriptive_name())
~~~~

2. 将实例用作属性

可以将类的一部分作为一个独立的类提取出来：**将一个大型的类拆分成多个协同工作的小类**

```python
 class Battery(): 
 """一次模拟电动汽车电瓶的简单尝试""" 
 
 def __init__(self, battery_size=70):
    self.battery_size = battery_size 
 def describe_battery(self): 
 """打印一条描述电瓶容量的消息""" 
 print("This car has a " + str(self.battery_size) + "-kWh battery.")
    
    
class ElectricCar(Car): 
 """电动汽车的独特之处""" 
 def __init__(self, make, model, year): 
 """ 
 初始化父类的属性，再初始化电动汽车特有的属性
 """ 
 super().__init__(make, model, year) 
 self.battery = Battery()   # 创建一个Battery实例储存在该属性中 
# 每当调用构造函数时 都会自动创建一个实例
# 该属性可以调用实例定义的方法
my_tesla = ElectricCar('tesla', 'model s', 2016)
my_tesla.battery.describe_battery() 
```

#### 5.导入类

导入类无异于导入模块 语法和工作机制都是一样的

~~~python
from class_name import class_1,class_2
~~~

python标准库是一组模板  可以使用标准库中的任何函数和类

------

## 文件与异常

**/**  和   **//**  区别

![image-20221031195750016](C:\Users\Azao\AppData\Roaming\Typora\typora-user-images\image-20221031195750016.png)

#### 读取文件

读取一个文件前提得打开文件

~~~python
with open('pi_digits.txt') as file_object: 
 contents = file_object.read() 
 print(contents) 
    
# 关键字with在不再需要访问文件后将其关闭。
~~~

**open('value'，'pattern')**  

* 打开文件 接收参数为文件路径  **在 Windows系统中，在文件路径中使用反斜杠（\）而不是斜杠（/）** 返回一个表示文件的对象   
*   **pattern** 接收一个实参   打开文件时，可指定读取模 式（'r'）、写入模式（'w'）、附加模式（'a'）或让你能够读取和写入文件的模式（'r+'）。如果 你省略了模式实参，Python将以默认的只读模式打开文件

![image-20221107105842986](C:\Users\Azao\AppData\Roaming\Typora\typora-user-images\image-20221107105842986.png)

* 如需逐行读取文件 可以使用for循环遍历  去除文件的空白可以用.rstrip()方法

* 使用关键字with时，open()返回的文件对象只在with代码块内可用。  如在代码块外还需要使用该内容 则可以把该内容存储在一个列表内

  ~~~python
  line = file_object.readlines()
  # 方法readlines()从文件中读取每一行 并将其存储在一个列表中
  
  ~~~

* 读取文本文件时，Python将其中的所有文本都解读为字符串。如果你读取的是数字，并 要将其作为数值使用，就必须使用函数int()将其转换为整数，或使用函数float()将其转 换为浮点数。

* 关闭文件用**close()**     //打开文件后一定要记得关闭

#### 写文件

**.write(" ")**

将字符串写入文件中

#### 读文件

**.read()**

~~~python
content = f.read(5) #在文件f中读取5个字符
content = f.readline() #读一行
content = f.readlines() # 一次性读取整个文件并返回列表 每行一个字符串元素
# read() 开头是定位在文件头部 每执行一次 向后移动指定字符数
~~~

#### 文件操作

需要导入os模块

~~~python
import os
os.rename("需要修改的文件名","新文件名")
~~~

~~~python
import os
os.remove("待删除的文件名")
os.mkdir("文件夹名字")  #创建文件夹
os.getcwd() #获取当前目录
os.chdir("../") #改变默认目录
os.listdir("./")#获取目录列表
os.rmdir("文件夹名")  #删除文件夹
~~~

