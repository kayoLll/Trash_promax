## 字符串

[字符串基本操作](https://www.runoob.com/python/python-strings.html)

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

