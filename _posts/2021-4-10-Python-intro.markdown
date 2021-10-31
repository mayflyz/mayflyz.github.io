---
layout:     post
title:      "Python基础入门"
subtitle:   "常用操作介绍"
date:       2021-04-10
author:     "mayfly"
header-img: "img/header/post-bg-sea.jpg"
tags:
    - Python
---

## 1、Python简介
Python是一种解释型语言，广泛应用于Web开发、网络爬虫、大数据分析和机器学习等。
20世纪90年代左右，Guido van Rossum在荷兰国家数学和计算机科学研究所设计出了Python语言。Python是由ABC、Algol-68、Modula-3、C、C++、SmallTalk和其他脚本语言发展而来的。
Python是一种面向对象的、解释型的、通用的、开源的脚本编程语言。Python简单易用、学习成本较低、功能强大，标准库和第三方库众多。

> Python优点：
>

* **Python语法简单，是一种极简主义编程语言。**
* **Python所有内容都是免费开源的，可以自由阅读、发布、修改源码。**
* **Python是一种高级语言，封装了底层细节，使用方便。**
* **Python是一种解释型语言，可以跨平台。**
* **Python可扩展性强，具有强大丰富的类库，能够覆盖绝大部分应用场景。**

> Python缺点：
>

* **代码运行速度慢。**
* **代码强制缩进，让初学者有些不习惯。**
* **代码加密困难。**

## 2、Python环境搭建
目前Python使用的主要有两个版本：`Python 2.x`和`Python 3.x`。2020年官方宣布停止`Python 2.x`的更新，目前广泛使用的是`Python 3.`x版本，所以本书也使用`Python 3.x`版本。
### 2.1  Python安装
要使用Python来编写程序，首先要安装Python软件。
Python最新源码、二进制文档等可以在Python官网查看，如下图所示。

![Python下载页面](img/python/Python下载页面.jpg)

#### 1. Windows下的Python安装

在Python下载页面下载Windows版本的安装包，格式为python-xyz.msi，其中xyz是安装的版本号，安装步骤如下图所示。

![Windows安装界面](img/python/Window安装界面.jpg)

#### 2.Linux系统下的Python安装
Linux发行版本众多，大多数都默认支持Python环境。这里以Ubuntu为例说明如何在Linux下安装Python 3。在Ubuntu环境下，可以直接使用包管理命令`apt-get`和`pip`（pip是Python的一个安装管理扩展库的工具）进行安装和升级。
（1）使用pip install命令安装第三方库：
`sudo apt-get install python-pip`
（2）使用apt-get命令安装Python：
`sudo apt-get install python-dev`

#### 3.Mac OS下的Python安装
Mac OS X 10.8以上的系统预安装了Python 2.7，可以在终端通过`python –v`命令查看Python版本。安装Python 3版本有两种方式：一种是使用命令行安装，即使用`brew install Python3`命令自动安装，然后配置环境变量；另一种是使用安装包进行安装，安装过程如图2-3所示。

![Mac安装界面](img/python/Mac安装界面.jpg)

在Mac OS下安装完Python后，Python版本仍然是之前的默认版本，需要配置才能更新为最新版本。环境变量设置如下：
（1）在命令行中输入`“which python3”`获取输入路径。
（2）在.bash_profile文件中添加Python3的安装路径：

```
# Setting PATH for Python 3.9
PATH="/Library/Frameworks/Python.framework/Versions/3.9/bin:${PATH}"

export  PATH

alias python="/Library/Frameworks/Python.framework/Versions/3.9/bin/python3"
```
（3）让文件生效：
```
source ~/.bash_profile
```
### 2.2  编写第一个Python程序
#### 1. 交互式编程
Python是解释型语言，可以通过Python的交互模式直接编写代码。在Linux中，可以直接在命令行中输入Python命令启动交互式编程：
```bash
xxx@xxx~ % python
Python 3.9.4 (v3.9.4:1f2e3088f3, Apr  4 2021, 12:32:44) 
[Clang 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>>
```
然后在提示符中输入以下文本信息：
```bash
>>>  print("Hello, Python 3.9")
```
最后按Enter键查看运行效果，输出结果如下：
```bash
Hello, Python 3.9
```
#### 2. 脚本式编程
通过脚本参数调用解释器执行脚本，直到脚本执行完毕。当脚本执行完成后，解释器不再有效。所有Python文件都是以.py为扩展名的，下面写一个简单的Python脚本文件。首先新建一个hello.py文件，然后输入以下代码：
```bash
#hello world.py
#!/usr/bin/env python

print("hello World")
```

保存成功后，在命令行中运行该文件，就可以看到执行后的信息：
```base
xxx@xxx~ % python hello.py
hello World
```

### 2.3  Python命名规范
Python中的标识符是由字母、数字、下划线组成的，需要遵守以下命名规则：

* **标识符由字符（A~Z和a~z）、下划线和数字组成，但首字符不能是数字。**
* **标识符不能与Python中的保留字相同。**
* **标识符中不能包含空格、@、% 以及 $ 等特殊字符。**
* **标识符是严格区分大小写的，如果两个单词的大小写格式不一样，那么代表的意义也是完全不同的。**
* **标识符以下划线开头具有特别的含义：以单下划线开头的标识符表示不能直接访问的类属性，以双下划线开头的标识符表示类的私有成员，以双下划线为开头和结尾的标识符是专用标识符。**


### 2.4  Python关键字
关键字是Python语言中已经被赋予特定意义的单词，不能作为常量、变量或其他任何标识符的名称。下表中展示了Python的常用关键字。

|关键字|关键字|关键字|
| ---- | ---- | ---- |
|assert | finally | or |
| and | exec| not |
| assert | finally | or |
| break | for | pass |
| class | from | print |
| continue | global | raise |
| def | if| return |
| del | import | try |
| elif | in|while |
| else|is|with |

## 3、Python数据类型
变量是存储在内存中的值，创建时会在内存中开辟一个空间。变量可以处理不同数据类型的值。Python的基本数据类型包括数字和字符串，内置数据类型包括列表、元组、字典等，如下表所示。

| 数据类型 |	例子|
| ----  | ---- |
| 数字	|100，3.1415， 1+2j|
| 字符串	|"Hello World"|
| 列表	|[1,2,3,4]|
| 字典	|{"name": "lucy"}|
| 元组	|(1, 2, 3, 4)|
| 其他	|None、布尔型、 集合|

### 2.3.1  数字类型
数字类型是用于存储数值的，在Python中有5种：整数、长整数、浮点数、布尔值和复数。

#### 1. 整数
整数是没有小数部分的数字，在Python中包括正整数、0和负整数。在Python中，可以使用多种进制来表示整数：
* **十进制：由0~10共十个数字组合，无前缀。**
* **二进制：由0和1两个数字组成，使用0b或0B做前缀。**
* **八进制：由0~7共8个数字组成，使用0o 或 0O做前缀。**
* **十六进制：由0~9共10个数字以及A~F（或a~f）共6个字母组成，使用0x或0X做前缀。**

```python
# Python整数的常用操作
# 整数类型定义
x = 6
print("x:", x)
y = 0
print("y:", y)
z = -6
print("y", z)
print("x type is: ", type(x))

# 二进制
bin_1 = 0b110
bin_2 = 0B110
print("bin_1 = ", bin_1)
print("bin_2 = ", bin_2)

# 八进制
oct_1 = 0o16
oct_2 = 0O66
print("oct_1 = ", oct_1)
print("oct_2 = ", oct_2)

# 十六进制
hex_1 = 0x45
hex_2 = 0x4Af
print("hex_1 = ", hex_1)
print("hex_2 = ", hex_2) 
```
程序执行结果（都是十进制整数）如下：
```python
x: 6
y: 0
y -6
x type is:  <class 'int'>
bin_1 =  6
bin_2 =  6
oct_1 =  14
oct_2 =  54
hex_1 =  69
hex_2 =  1199
```
#### 2.浮点数
浮点数由整数部分和小数部分组成，在Python中的浮点数可以看作是数学里面的小数。Python中的浮点数有两种表示方式：
* **十进制形式：常见的小数形式，书写时必须包含小数点。**
* **科学计数法形式：aEn或aen形式，整个表达式等价于a×10n。例如，2.5e2 = 2.5 × 102 = 250。其中，a为位数部分，是一个十进制数；n为指数部分，是一个十进制整数；E或e是固定的字符，用于分割尾数部分和指数部分。**

```python
# Python浮点数的常用操作
# 浮点型数字
f_1 = 12.6
print("f_1 = ", f_1)
print("f_1 type: ", type(f_1))
f_2 = 0.34967816434356003
print("f_2 = ", f_2)
print("f_2 type: ", type(f_2))
f_3 = 0.0000000000000000000000000968
print("f_3 = ", f_3)
print("f_3 type: ", type(f_3))
f_4 = 385689745102456787824523453.45006
print("f_4 = ", f_4)
print("f_4 type: ", type(f_4))
f_5 = 8e4
print("f_5 = ", f_5)
print("f_5 type: ", type(f_5))
```
程序执行结果如下：
```python
f_1 =  12.6
f_1 type:  <class 'float'>
f_2 =  0.34967816434356
f_2 type:  <class 'float'>
f_3 =  9.68e-26
f_3 type:  <class 'float'>
f_4 =  3.8568974510245677e+26
f_4 type:  <class 'float'>
f_5 =  80000.0
f_5 type:  <class 'float'>
```
从运行结果可以看出，Python可以容纳极小和极大的浮点数。在输出浮点数时，print会根据浮点数的长度和大小适当地舍去一部分数字或者采用科学计数法。

#### 3. 布尔值
Python提供布尔类型来表示真（对）或假（错）。布尔类型是特殊的整数，由常量True和False表示，用于数值运算时，会被当作数值1和0进行运算。
```python
# Python布尔值的常用操作
# 布尔类型
b_1 = False
print("b_1 = ", b_1)
print("b_1 type: ", type(b_1))

b_2 = True
print("b_2 = ", b_2)
print("b_2 type: ", type(b_2))

sum_1 = b_1 + 1
print("sum_1 = ", sum_1)
print("sum_1 type: ", type(sum_1))

sum_2 = b_2 + 1
print("sum_2 = ", sum_2)
print("sum_2 type: ", type(sum_2))
```
程序执行结果如下：
```python
# b_1 =  False
b_1 type:  <class 'bool'>
b_2 =  True
b_2 type:  <class 'bool'>
sum_1 =  1
sum_1 type:  <class 'int'>
sum_2 =  2
sum_2 type:  <class 'int'>
```
从输出结果来看，布尔类型在与整数类型做运算时会被作为整数值使用，但是一般不这样使用。一般来说，布尔类型是表示事情真假的：如果是真的，就使用True或1代表；如果是假的，就使用False或0代表。

#### 4. 复数
复数是Python的内置类型，由实部和虚部构成，虚部以j或J作为后缀，具体格式为`a + bj`。
```python
#  Python复数的常用操作
c_1 = 6 + 0.8j
print("c_1 = ", c_1)
print("c_1 type", type(c_1))

c_2 = 8 - 1.6j
print("c_2 = ", c_2)
#对复数进行简单计算
print("c_1 + c_2: ", c_1+c_2)
print("c_1 * c_2: ", c_1*c_2)
```
Python支持简单的复数运算，程序执行结果如下：
```python
c_1 =  (6+0.8j)
c_1 type <class 'complex'>
c_2 =  (8-1.6j)
c_1 + c_2:  (14-0.8j)
c_1 * c_2:  (49.28-3.200000000000001j)
```
### 3.2  运算符
Python语言支持多种类型的运算符，包括算术运算符、比较（关系）运算符、赋值运算符、逻辑运算符等。
#### 1. 算术运算符
下表列出了常用的算术运算符，这里假设变量a为6、变量b为8。

| 运算符 |	描述|	示例|
| :-: | -- | :-- |
| + | 加：两个对象相加 | a + b，输出结果为14|
| - | 减：负数，或是一个数减去另一个数 | a – b，输出结果为-2|
| * | 乘：两个数相乘，或是返回一个被重复若干次的字符串 | a * b，输出结果为48|
| / | 除：x除以y | b / a，输出结果为1.33333|
| % | 取模：返回除法的余数 | b % a，输出结果为2|
| ** | 幂：返回x的y次幂 | a**b表示6的8次方，输出结果为1679616|
| // | 取整除：返回商的整数部分（向下取整） | b//a，输出结果为1|

#### 2. 比较（关系）运算符
所有比较运算符返回1表示真，返回0表示假，与特殊的变量True和False等价。下表列出了常用的比较运算符，同样假设变量a为6、变量b为8。
| 运算符 |	描述|	示例|
| -- | -- | -- |
|== | 等于：比较对象是否相等 | a == b，返回False|
|!= | 不等于：比较两个对象是否不相等 | a != b，返回True|
|> | 大于：返回x是否大于y | a > b，返回False|
|< | 小于：返回x是否小于y | a < b，返回True|
|>= | 大于等于：返回x是否大于等于y | a >= b，返回False|
|<= | 小于等于：返回x是否小于等于y | a <= b，返回True|

#### 3. 赋值运算符
下表列出了常用的赋值运算符，同样假设变量a为6、变量b为8。

| 运算符 |	描述|	示例|
| -- | -- | -- |
= | 简单的赋值运算符 | c = a + b，将a + b的运算结果赋值为c
+= | 加法赋值运算符 | c += a，等效于c = c + a
-= | 减法赋值运算符 | c -= a，等效于c = c - a
*= | 乘法赋值运算符 | c*= a，等效于c = c a
/= | 除法赋值运算符 | c /= a，等效于c = c / a
%= | 取模赋值运算符 | c %= a，等效于c = c % a
**= | 幂赋值运算符 | C**= a，等效于c = c**a
//= | 取整除赋值运算符 | c //= a 等效于 c = c // a

#### 4. 逻辑运算符

Python语言支持的常用逻辑运算符下表所示，这里假设变量a为6、变量b为8。

| 运算符 |	描述|	示例|
| -- | -- | -- |
and | x and y | 布尔“与”：如果x为False，x and y返回False，否则返回y的计算值 | a and b，返回8
or | x or y | 布尔“或”：如果x是非0，它返回x的计算值，否则返回y的计算值 | a or b，返回6
not | not x | 布尔“非”：如果x为True，返回False。如果x为False时返回True | not(a and b)，返回False

### 3.3  字符串
字符串是Python中常用的数据类型，可以使用引号（'或"）来创建。
```python
# Python字符串的常用操作
# 1.字符串创建
str_1 = '我是一个字符串'
print("str_1: ", str_1)
str_2 = "I am a string"
print("str_2:", str_2)
# 三引号可以将复杂的字符串进行赋值，允许字符串跨行，并且包含换行符、制表符及其他特殊字符
str_3 = '''
    Python 字符串,
    ‘单引号’\n
    “双引号”
    '''
print("str_3:", str_3)
# 2.字符串拼接
city_1 = "上海市" "黄埔区"
city_2 = "北京市" + "海淀区"
print(city_1)
print(city_2)

# 字符串不允许直接与其他类型进行拼接，需要先将其他类型转换为字符串
age = 18
info = "我已经" + str(age) + "岁了， 我在" + city_1
print(info)
```

程序执行结果如下：
```python
str_1:  我是一个字符串
str_2: I am a string
str_3: 
    Python 字符串,
    ‘单引号’

    “双引号”

上海市黄埔区
北京市海淀区
我已经18岁了， 我在上海市黄埔区
```

### 3.4 容器
Python中常见的容器有列表、元组和字典等。
#### 1. 列表
列表是由方括号和方括号括起来的数据构成的。列表中的一项叫作一个元素，既可以是整数、浮点数、字符串，也可以是另一个列表或其他数据结构，并且每个元素使用英文逗号隔开。
```python
#Python列表的常用操作
# 列表
list_1 = [1, 2, 3.1415, 4e8]
list_2 = ["math", "physical", 2020, 2021]

print("list_1[2]: ", list_1[2])
print("list_2[1:2]", list_2[1:2])

# 列表增删
list = ["tecent"]
list.append("baidu")
list.append("alibaba")
print("list append after:", list)

del list[1]
print("after delete Value At index 1:", list)
```
程序执行结果如下：
```python
list_1[2]:  3.1415
list_2[1:2] ['physical']
list append after: ['tecent', 'baidu', 'alibaba']
after delete Value At index 1: ['tecent', 'alibaba']
```

##### 2. 元组
元组是由小括号和小括号括起来的数据构成的，与列表非常像。元组生成后不能再进行增、删、改等操作。
```python
# Python元组的常用操作
tup_1 = (1, 2, 3.1425, 4e8)
tup_2 = ("math", "physical", 2020, 2021)

print("tup_1[0]: ", tup_1[0])
print("tup_2[1:2]: ", tup_2[1:2])

# 修改元组元素操作是非法的,可以对元组进行连接组合
tup_3 = tup_1 + tup_2
print("tup_3:", tup_3)

#删除元组
del tup_3
print("After deleting tup_3 : ", tup_3)
```
在元组被删除后，输入变量时会有异常信息，程序执行结果如下：
```python
list_1[2]:  3.1425
list_2[1:2] ['physical']
list append after: ['tecent', 'baidu', 'alibaba']
after delete Value At index 1: ['tecent', 'alibaba']
tup_1[0]:  1
tup_2[1:2]:  ('physical',)
tup_3: (1, 2, 3.1425, 400000000.0, 'math', 'physical', 2020, 2021)
Traceback (most recent call last):
  File "/Users/a123/Desktop/Python/coll.py", line 30, in <module>
    print("After deleting tup_3 : ", tup_3)
NameError: name 'tup_3' is not defined
```

##### 3. 字典
字典是一种无序、可变的序列，它的元素以“键值对（key=>value）”的形式存储。字典中的索引称为键（key），对应的元素称为值（value），键及其关联的值称为“键值对”，其中键一般是唯一的。
```python
# Python字典的常用操作
dict = {'Lucy': '1687', 'Bob': '2637', 'Tom': '3258'}
print("dict: ", dict)
print("dict['Lucy']:", dict["Lucy"])

dict["Kitty"] = '2648'    #增加条目
pring("after append kitty: ", dict)

del dict["Tom"]    #删除键是Tom的条目
pring("after delete Tom: ", dict)

dict.clear()    #清空所有条目
print("after clear all:", dict)
```
程序执行结果如下:
```python
dict:  {'Lucy': '1687', 'Bob': '2637', 'Tom': '3258'}
dict['Lucy']: 1687
after append kitty:  {'Lucy': '1687', 'Bob': '2637', 'Tom': '3258', 'Kitty': '2648'}
after delete Tom:  {'Lucy': '1687', 'Bob': '2637', 'Kitty': '2648'}
after clear all: {}
```

## 4、Python控制结构
Python按照执行流程可以分为顺序结构、选择（分支）结构和循环结构三种：
* **顺序结构：程序按照顺序依次执行代码块。**
* **选择结构：程序有选择性地执行代码块。**
* **循环结构：程序不断地重复执行代码块。**

### 4.1  选择结构
在Python中，通过对条件进行判断，然后根据结果决定执行的代码块称为选择结构或分支结构，执行过程下图所示。

![条件语句](img/python/条件语句.png)

Python中的选择结构是通过`if-else `语句来实现的，使用方式如下：
```python
#Python选择结构
name = 'python'
if name == 'python':
    print 'Hello Python!!'     

height = float(input("输入身高（米）："))
weight = float(input("输入体重（千克）："))
bmi = weight / (height * height)  #计算BMI指数
if bmi<18.5:
    print("BMI指数为："+str(bmi))
    print("体重过轻")
elif bmi>=18.5 and bmi<24.9:
    print("BMI指数为："+str(bmi))
    print("正常范围，注意保持")
elif bmi>=24.9 and bmi<29.9:
    print("BMI指数为："+str(bmi))
    print("体重过重")
else:
    print("BMI指数为："+str(bmi))
    print("肥胖")
```

程序执行结果如下：

```python
Hello Python!
输入身高（米）：178
输入体重（千克）：62
BMI指数为：0.001956823633379624
体重过轻
```
Python不支持switch语句，所以多个条件判断只能通过`elif`来实现。
### 4.2  循环结构
循环结构提供了执行多次代码块的方式，在Python中用`for`和`while`语句来实现。
#### 1. for循环
for循环常用于遍历字符串、列表、元组、字典、集合等序列类型，逐个获取序列中的各个元素。for循环语句的执行流程如图2-5所示。

![for循环流程](img/python/for循环语句.png)

for循环使用方式如下：
```python
# Python for循环结构
for char in 'Python':     # 遍历字符串
   print('当前字母 :', char)

fruits = ['banana', 'apple',  'orange']
for fruit in fruits:        #遍历列表
   print('水果 :', fruit)
```
程序执行结果如下：
```python
当前字母 : P
当前字母 : y
当前字母 : t
当前字母 : h
当前字母 : o
当前字母 : n
水果 : banana
水果 : apple
水果 : orange
```

#### 2. while循环
while循环在条件表达式为真的情况下会循环执行相同的代码块。while循环的执行流程如图2-6所示。

![while循环流程](img/python/while循环流程.png)

while循环使用方式如下：
```python
# Python while循环结构
i = 0
fruits = ['banana', 'apple',  'orange']
while i < len(fruits):
    print(fruits[i])
    i = i + 1
```
程序执行结果如下：
```python
banana
apple
orange
```
在使用while循环时，注意要保证循环条件有变为False的时候，否则这个循环将成为一个死循环。所谓死循环，指的是无法结束的循环结构，即该循环永远不会结束。

## 5、Python函数
函数是可重复使用的，用来实现某个功能的代码块，提高了程序模块化和代码的重复利用率。
### 5.1  函数定义
Python函数定义使用def关键字实现，语法格式如下：

```python
def functionname( parameters ):
   "函数_文档字符串"
   function_suite
   return [表太式]
```

Python中的函数定义需要满足以下规则：
* **以def关键字开头，后接函数标识符名称和圆括号()。**
* **任何传入的参数和自变量必须放在圆括号内，圆括号之间可用于定义参数。**
* **第一行语句可以选择性地使用文档字符串，用于存放函数说明。**
* **内容以冒号起始，并且缩进。**
* **return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。**

下面定义两个函数，其中一个是空函数。Python允许定义空函数，但是空函数本身并没有实际意义。
```python
#Python 函数定义
def pass_me():
   "空函数，没有实际意义"
   pass

def max(num1,num2):
   "比较两个数的大小，并返回大的值"
   max = num1 if num1 > num2 else num2
   return max
```

### 5.2  函数调用
函数定义之后，可以通过另一个函数来调用执行。函数调用的基本语法如下：
```python
[返回值] = 函数名([形参值])
```
其中，函数名指的是要调用的函数名称；形参值指的是当初创建函数时要求传入的各个形参的值。如果该函数有返回值，就可以通过一个变量来接收，当然也可以不接收。需要注意的是，创建函数有多少个形参，调用时就需要传入多少个值，且顺序必须和创建函数时一致。即便该函数没有参数，函数名后的小括号也不能省略。例如，调用上面创建的`pass_me()`和`max()`函数：
```python
# Python 函数调用
pass_me()
max = max(66, 28)
print(str(max))
```
空函数本身并不包含任何有价值的执行代码块，也没有返回值，调用空函数不会有任何效果。对于max()函数的调用，返回了传入参数的最大值，因此执行结果为66。

### 5.3  匿名函数
Python的匿名函数是通过`lambda`表达式来实现的。如果一个函数的函数体仅有1行表达式，那么该函数可以用lambda表达式来替换。 `lambda`仅是一个表达式，只能封装有限的逻辑进入，不能访问参数列表之外或全局命名空间的参数。`lambda`表达式的语法格式如下：
```python
lambda [arg1 [,arg2,...,argn]]:expression
```
其中，定义`lambda`表达式必须使用`lambda`关键字；[arg1 [,arg2,...,argn]]作为可选参数，等同于定义函数是指定的参数列表；expression为该表达式的名称。匿名函数实例如下：
```python
#Python 匿名函数定义
# 匿名函数
sum = lambda x,y:x+y

# 调用sum函数
print("相加之后的值为：",sum(3,4))
```
程序执行结果如下：
```python
相加之后的值为： 7
```
## 6、Python模块
Python模块（Module）是代码的一种组织形式，把许多有关联的代码放到一个单独的Python文件中。Python模块是一个包含某个功能（变量、函数、类实现）的包，直接在程序中导入该模块即可使用。

### 6.1  导入模块
Python有很多标准库和开源的第三方代码，将需要的功能模块导入当前程序就可以直接使用。Python使用import关键字导入模块，主要方式有两种：
* **import模块名：导入模块中所有成员，包括变量、函数和类等，并且在使用模块中的成员时需要该模块名作为前缀。**
* **from 模块名 import 成员名：导入模块中指定的成员，在使用该成员时无须附加任何前缀，直接使用成员名即可。**
#### 1. import语句
使用import语句引入模块的语法如下：
```python
import module1[, module2[,...,moduleN]]
```
```python
代码清单2-15  Python模块导入
# 导入math模块
import math
# 导入random和sys两个模块
import random,sys
import os as o

# 使用math模块名作为前缀来访问模块中的成员
print(math.fabs(-20))

# 使用sys模块名作为前缀来访问模块中的成员
print(sys.argv[0])

# 使用o模块别名访问模块变量，其中sep变量代表平台上的路径分隔符
print(o.sep)
```
上面的代码导入了多个模块。通过import可以导入单个或多个模块，还可以为模块起别名。不管执行了多少次import，一个模块只会被导入一次，这样可以防止导入模块被一遍又一遍地执行。上面代码的执行结果如下：
```python
20.0
cls.py
/
```
#### 2. from…import 语句
Python的from语句可以从模块中导入指定部分到当前文件，语法如下：
```python
from modname import name1[, name2[,...,nameN]]
```
```python
# Python from模块导入
# 导入sys模块的argv成员
from sys import argv

# 导入math模块的pi，并为其指定别名p
from math import pi as p

print(argv[0])

print(p)
```
也可以通过“form模块名import *”导入指定模块中的所有成员，不过存在名字冲突的问题，不推荐使用。

### 6.2  模块的搜索路径
当使用import语句导入模块后，Python解析器会按照以下顺序查找指定模块：
* **在当前目录（执行程序所在目录）下查找。**

* **在PYTHONPATH环境变量中的目录下查找。****

* **在Python默认安装目录下查找。**

以上所涉及的目录都存在标准sys的sys.path变量中，通过此变量我们可以指定程序文件支持查找的所有目录。

## 7、Python面向对象编程
面向对象编程是在面向过程编程的基础上发展来的，是一种封装代码的方法，具有更强的灵活性和扩展性。
* **面向过程编程以过程为核心**，采用结构化、模块化和自顶向下的设计方法，把系统划分为不同的模块，降低了系统的复杂性。面向过程编程最重要的特点是函数，通过函数调用一个个子函数，程序运行的逻辑是事先决定好的。
* **面向对象编程以对象为核心**，从更高的层次进行系统建模，把相关数据和方法组织为一个整体来看待，是对现实世界理解和抽象的方法。面向对象编把系统视为对象的集合，每个对象可以接收其他对象发过来的消息并处理这些消息。面向对象编程的程序执行就是一系列消息在各个对象之间进行传递与处理。
Python语言在设计之初就是一门面向对象的语言。面向对象编程内容繁多，本章仅对Python的面向对象编程做一个简单介绍。
### 7.1  Python类创建和实例
使用class语句来创建一个新类，在class关键之后为类的名称，并以冒号结尾，语法如下：
```python
class ClassName:
   '类的帮助信息'   #类文档字符串

   class_suite  #类体
```
类的帮助信息可以通过ClassName.doc查看。class_suite由类成员、方法、数据属性组成。下面使用Python定义一个Student类。
```python
#Python定义学生类
class Student(object):
    """所有学生的基类，描述学生基本信息"""
    def __init__(self, name, age, score):
        super( Student, self).__init__()
        self.name = name
        self.age = age
        self.score = score

    def print_age(self):
        print(self.name, " age is ", self.age)
    
    def print_score(self):
        print(self.name, " score: ", self.score)

"创建 Student 类的第一个对象"
lucy = Student("lucy", 18, 86)
"创建 Student 类的第二个对象"
tony = Student("tony", 19, 92)

lucy.print_age()
lucy.print_score()

tony.print_age()
tony.print_score()
```
class后面紧接着的是类名通常是大写开头的单词，即Student，紧接着是(object)，表示该类是从哪个类继承下来的，object类是所有类的父类。__init__()方法是一个特殊方法，被称为类的构造函数或初始化方法，在创建了这个类的实例时就会被调用。self代表类的实例，在定义类的方法时是必须有的，在调用时不必传入相应的参数。Python中使用点号（.）来访问对象的属性和函数，代码的执行结果如下：
```python
lucy  age is  18
lucy  score:  86
tony  age is  19
tony  score:  92
```
### 7.2  Python内置类属性
Python中内置了类属性（创建了新类系统时就会主动创建这些属性），常见的如下：

|内置类属性	| 说明	| 触发方式|
| -- | -- | -- |
\__str__ | 实例字符串表示，可读性 | print(类实例)，若没有实现，则使用repr结果
\__repr__ | 实例字符串表示，准确性 | print(repr(类实例))
\__dict__ | 实例自定义属性 | 实例.\__dict__
\__doc__ | 类文档，子类不继承 | help(类或实例)
\__name__ | 类名 | 实例.\__name__
\__module__ | 类定义所在的模块 | 实例.\__module__

对上述Student类添加__str__实现以及测试代码：
```python
# Python内置类验证
...
    def __str__(self):
        return "%s的年龄是%s, 分数是%s"%(self.name, self.age, self.score)
...
print("Student __str__", lucy)
print("Student __repr__", repr(lucy))
print("Student.__doc__:", Student.__doc__)
print("Student.__name__:", Student.__name__)
print("Student.__module__:", Student.__module__)
print("Student.__bases__:", Student.__bases__)
print("Student.__dict__:", Student.__dict__)
```
以上代码获取相关内置类属性，程序执行结果如下：
```python
Student __str__ lucy的年龄是18, 分数是86
Student __repr__ <__main__.Student object at 0x7fc84fa37b20>
Student.__doc__: 所有学生的基类，描述学生基本信息
Student.__name__: Student
Student.__module__: __main__
Student.__bases__: (<class 'object'>,)
Student.__dict__: {'__module__': '__main__', '__doc__': '所有学生的基类，描述学生基本信息', '__init__': <function Student.__init__ at 0x7fc84fa2b9d0>, 'print_age': <function Student.print_age at 0x7fc84fa2ba60>, 'print_score': <function Student.print_score at 0x7fc84fa2baf0>, '__str__': <function Student.__str__ at 0x7fc84fa2bb80>, '__dict__': <attribute '__dict__' of 'Student' objects>, '__weakref__': <attribute '__weakref__' of 'Student' objects>}
```
### 7.3  类的继承
在Python中，可以通过类的继承机制来实现代码的重用。当定义一个新类时，可以继承自某个现有的类，通过继承创建的新类称为子类（Sub class），被继承的类称为基类、父类或超类（Base class、Super class）。创建一个继承类的语法如下：
```python
class 派生类名(基类名)
    ...    
```
任何类都可以是父类，Python3创建的类默认继承object类。下面创建一个名为Person的基类，包含name和age属性以及run和sleep方法。
```python
# Python基类定义
class Person():
   """人——父类"""
   def __init__(self, name, age):
      super(Person, self).__init__()
      self.name = name
      self.age = age

   def run(self):
      print(self.name, "在跑步")

   def sleep(self):
      print(self.name, "在睡觉")

person = Person("张三", 28)
person.run()
person.sleep()
```
以上代码执行结果如下：
```python
张三 在跑步
张三 在睡觉
```

创建一个继承自Person的子类Employees类，继承Person的属性和方法。
```python
#Python子类定义
class Employees(Person):
   """雇员类——子类"""
   pass

emp = Employees("王五",28)
emp.run()
emp.sleep()   
```
在类中不添加任何属性和方法，与父类Person拥有相同的属性和方法，执行结果如下：
```python
王五 在跑步
王五 在睡觉
```
下面为Employees添加初始化方法`__init__()`，之后子类将不再继承父类的`__init__() `函数，并对父类的`sleep()`函数进行重写，同时添加新函数`work()`。
```python
# Python子类方法定义
class Employees(Person):
   """雇员类——子类"""
   def __init__(self, name, age, depart):
      super().__init__(name, age)
      self.depart = depart

   def sleep(self):
      print(self.name, "午休半小时")

   def work(self):
      print("员工", self.name,"在", self.depart,"工作")

emp = Employees("赵四", "42", "技术部")
emp.run()
emp.sleep()
emp.work()
```
对子类函数的执行结果如下：
```python
赵四 在跑步
赵四 午休半小时
员工 赵四 在 技术部 工作
```
## 8、小  结
本章先介绍了Python的历史以及在Windows、Linux以及Mac OS下的安装及配置；然后对Python的基本数据结构、控制结构、函数和面向对象编程等内容进行了介绍。

