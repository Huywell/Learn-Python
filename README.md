# Learn-Python
## 学习Python

## 主要以Python3为基本环境
官方宣布，2020 年 1 月 1 日， 停止 Python 2 的更新

## 学习资料网站
菜鸟教程  
https://www.runoob.com/python3/python3-tutorial.html

## Python3 简介
Python 是一个高层次的结合了解释性、编译性、互动性和面向对象的脚本语言。  
Python 的设计具有很强的可读性，相比其他语言经常使用英文关键字，其他语言的一些标点符号，它具有比其他语言更有特色语法结构。  
Python 是一种解释型语言： 这意味着开发过程中没有了编译这个环节。类似于PHP和Perl语言。  
Python 是交互式语言： 这意味着，您可以在一个 Python 提示符 >>> 后直接执行代码。  
Python 是面向对象语言: 这意味着Python支持面向对象的风格或代码封装在对象的编程技术。  
Python 是初学者的语言：Python 对初级程序员而言，是一种伟大的语言，它支持广泛的应用程序开发，从简单的文字处理到 WWW 浏览器再到游戏。

## Python 特点
1. 易于学习：Python有相对较少的关键字，结构简单，和一个明确定义的语法，学习起来更加简单。
2. 易于阅读：Python代码定义的更清晰。
3. 易于维护：Python的成功在于它的源代码是相当容易维护的。
4. 一个广泛的标准库：Python的最大的优势之一是丰富的库，跨平台的，在UNIX，Windows和Macintosh兼容很好。
5. 互动模式：互动模式的支持，您可以从终端输入执行代码并获得结果的语言，互动的测试和调试代码片断。
6. 可移植：基于其开放源代码的特性，Python已经被移植（也就是使其工作）到许多平台。
7. 可扩展：如果你需要一段运行很快的关键代码，或者是想要编写一些不愿开放的算法，你可以使用C或C++完成那部分程序，然后从你的Python程序中调用。
8. 数据库：Python提供所有主要的商业数据库的接口。
9. GUI编程：Python支持GUI可以创建和移植到许多系统调用。
10. 可嵌入: 你可以将Python嵌入到C/C++程序，让你的程序的用户获得"脚本化"的能力。

## Python3 基础语法
### 编码
默认情况下，Python 3 源码文件以 UTF-8 编码，所有字符串都是 unicode 字符串。 当然也可以为源码文件指定不同的编码：
```python
-*- coding: cp-1252 -*-
```
上述定义允许在源文件中使用 Windows-1252 字符集中的字符编码，对应适合语言为保加利亚语、白罗斯语、马其顿语、俄语、塞尔维亚语。

### 标识符
第一个字符必须是字母表中字母或下划线 _ 。  
标识符的其他的部分由字母、数字和下划线组成。  
标识符对大小写敏感。

### python保留字
保留字即关键字，我们不能把它们用作任何标识符名称。Python 的标准库提供了一个 keyword 模块，可以输出当前版本的所有关键字：
>\>>> import keyword  
>\>>> keyword.kwlist  
>['False', 'None', 'True', 'and', 'as', 'assert', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']

### 注释
Python中单行注释以 # 开头

### 行与缩进
python最具特色的就是使用缩进来表示代码块，不需要使用大括号 {} 。  
缩进的空格数是可变的，但是同一个代码块的语句必须包含相同的缩进空格数。

### 多行语句
Python 通常是一行写完一条语句，但如果语句很长，我们可以使用反斜杠(\)来实现多行语句  
例如：
```python
total = item_one + \
item_two + \
item_three
```
在 [], {}, 或 () 中的多行语句，不需要使用反斜杠(\\)  
例如：
```python
total = ['item_one', 'item_two', 'item_three',
'item_four', 'item_five']
```

### 数字(Number)类型
python中数字有四种类型：整数、布尔型、浮点数和复数。  
int (整数), 如 1, 只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。  
bool (布尔), 如 True。  
float (浮点数), 如 1.23、3E-2  
complex (复数), 如 1 + 2j、 1.1 + 2.2j  

### 字符串(String)
python中单引号和双引号使用完全相同。  
使用三引号('''或""")可以指定一个多行字符串。  
转义符 '\'  
反斜杠可以用来转义，使用r可以让反斜杠不发生转义。 如 r"this is a line with \n" 则\n会显示，并不是换行。  
按字面意义级联字符串，如"this " "is " "string"会被自动转换为this is string。  
字符串可以用 + 运算符连接在一起，用 * 运算符重复。  
Python 中的字符串有两种索引方式，从左往右以 0 开始，从右往左以 -1 开始。  
Python中的字符串不能改变。  
Python 没有单独的字符类型，一个字符就是长度为 1 的字符串。  
字符串的截取的语法格式如下：变量\[头下标:尾下标:步长]  
```python
word = '字符串'
sentence = "这是一个句子。"
paragraph = """
这是一个段落，  
可以由多行组成  
""" 
``` 

### 空行
函数之间或类的方法之间用空行分隔，表示一段新的代码的开始。类和函数入口之间也用一行空行分隔，以突出函数入口的开始。  
空行与代码缩进不同，空行并不是Python语法的一部分。书写时不插入空行，Python解释器运行也不会出错。但是空行的作用在于分隔两段不同功能或含义的代码，便于日后代码的维护或重构。  
记住：空行也是程序代码的一部分。

### 多个语句构成代码组
缩进相同的一组语句构成一个代码块，我们称之代码组。
像if、while、def和class这样的复合语句，首行以关键字开始，以冒号( : )结束，该行之后的一行或多行代码构成代码组。
我们将首行及后面的代码组称为一个子句(clause)。  
如下实例：
```python
if expression: 
    suite
elif expression: 
    suite 
else: 
    suite
```

### Python3 基本数据类型
Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。  
在 Python 中，变量就是变量，它没有类型，我们所说的"类型"是变量所指的内存中对象的类型。  
等号（=）用来给变量赋值。  
等号（=）运算符左边是一个变量名，等号（=）运算符右边是存储在变量中的值。

### 多个变量赋值
Python允许你同时为多个变量赋值。  
例如：
>a = b = c = 1

### 标准数据类型
Python3 中有六个标准的数据类型：  
Number（数字）  
String（字符串）  
List（列表）  
Tuple（元组）  
Set（集合）  
Dictionary（字典）  
Python3 的六个标准数据类型中：  
不可变数据（3 个）：  
Number（数字）、String（字符串）、Tuple（元组）；  
可变数据（3 个）：  
List（列表）、Dictionary（字典）、Set（集合）。  

### Number（数字）
Python3 支持 int、float、bool、complex（复数）。  
在Python 3里，只有一种整数类型 int，表示为长整型，没有 python2 中的 Long。  
像大多数语言一样，数值类型的赋值和计算都是很直观的。  
内置的 type() 函数可以用来查询变量所指的对象类型。  
注意：
1. Python可以同时为多个变量赋值，如a, b = 1, 2。
2. 一个变量可以通过赋值指向不同类型的对象。
3. 数值的除法包含两个运算符：/ 返回一个浮点数，// 返回一个整数。
4. 在混合计算时，Python会把整型转换成为浮点数。

### String（字符串）
Python中的字符串用单引号 ' 或双引号 " 括起来，同时使用反斜杠 \ 转义特殊字符。  
字符串的截取的语法格式如下：  
变量\[头下标:尾下标]  
注意：
1. 反斜杠可以用来转义，使用r可以让反斜杠不发生转义。
2. 字符串可以用+运算符连接在一起，用*运算符重复。
3. Python中的字符串有两种索引方式，从左往右以0开始，从右往左以-1开始。
4. Python中的字符串不能改变。

### List（列表）
List（列表） 是 Python 中使用最频繁的数据类型。  
列表可以完成大多数集合类的数据结构实现。列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）。  
列表是写在方括号 [] 之间、用逗号分隔开的元素列表。  
和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。  
列表截取的语法格式如下：  
变量\[头下标:尾下标]  
注意：
1. List写在方括号之间，元素用逗号隔开。
2. 和字符串一样，list可以被索引和切片。
3. List可以使用+操作符进行拼接。
4. List中的元素是可以改变的。

### Tuple（元组）
元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 () 里，元素之间用逗号隔开。  
元组中的元素类型也可以不相同  
注意：
1. 与字符串一样，元组的元素不能修改。
2. 元组也可以被索引和切片，方法一样。
3. 注意构造包含 0 或 1 个元素的元组的特殊语法规则。
4. 元组也可以使用+操作符进行拼接。

### Dictionary（字典）
字典（dictionary）是Python中另一个非常有用的内置数据类型。  
列表是有序的对象集合，字典是无序的对象集合。两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。  
字典是一种映射类型，字典用 { } 标识，它是一个无序的 键(key) : 值(value) 的集合。  
键(key)必须使用不可变类型。  
在同一个字典中，键(key)必须是唯一的。  
注意：
1. 字典是一种映射类型，它的元素是键值对。
2. 字典的关键字必须为不可变类型，且不能重复。
3. 创建空字典使用 { }。

### Set（集合）
集合（set）是由一个或数个形态各异的大小整体组成的，构成集合的事物或对象称作元素或是成员。  
基本功能是进行成员关系测试和删除重复元素。  
可以使用大括号 { } 或者 set() 函数创建集合，注意：创建一个空集合必须用 set() 而不是 { }，因为 { } 是用来创建一个空字典。  
创建格式：
```python
parame = {value01,value02,...}
```
或者
```python
set(value)
```

### 类名命名
* 类名应采用驼峰命名法，即将类名中的每个单词的首字母都大写，而不使用下划线。实例名和模块名都采用小写格式，并在单词之间加上下划线。
* 可使用空行来组织代码，但不要滥用。在类中，可使用一个空行来分隔方法；而在模块中，可使用两个空行来分隔类。
* 需要同时导入标准库中的模块和你编写的模块时，先编写导入标准库模块的import语句，再添加一个空行，然后编写导入你自己编写的模块的import语句。在包含多条import语句的程序中，这种做法让人更容易明白程序使用的各个模块都来自何方。