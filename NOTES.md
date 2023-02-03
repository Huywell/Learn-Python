# 学习笔记
学习资料网站
[菜鸟教程](https://www.runoob.com/python3/python3-tutorial.html)

### 常见的格式化符号
|格式符号|描述|
|:-:|:-|
|%s|通过str()字符串转换来格式化
|%u|无符号的十进制整数
|%d|有符号的十进制整数
|%o|八进制整数
|%x|十六进制整数，小写字母
|%X|十六进制整数，大写字母
|%e|浮点数字(科学计数法)
|%E|浮点数字(科学计数法，用E代替e)
|%f|浮点实数
|%g|浮点数字(根据值的大小采用%e或%f)
|%G|浮点数字(类似于%g)

### 标准数据类型
Python3 中有六个标准的数据类型：  
Number（数字）  
String（字符串）  
List（列表）  
Tuple（元组）  
Set（集合）  
Dictionary（字典）  
Python3 的六个标准数据类型中：  
不可变数据（3 个）：Number（数字）、String（字符串）、Tuple（元组）；  
可变数据（3 个）：List（列表）、Dictionary（字典）、Set（集合）。

### 字符串
转义字符|描述
|:-:|:-|
|\ |转义符
|\ (在行尾时)|续行符
|\ |反斜杠符号
|\'|单引号
|\"|双引号
|\a|响铃，执行后电脑有响声
|\b|退格(Backspace)
|\n|换行
|\v|纵向制表符
|\t|横向制表符
|\r|回车，将 \r 后面的内容移到字符串开头，并逐一替换开头部分的字符，直至将 \r 后面的内容完全替换完成。
|\f|换页
|\other|其它的字符以普通格式输出

# Python函数

在 ***print()*** 语句中，方法 ***title()*** 出现在变量的后面。方法是Python可对数据执行的操作。在name.title()中，name后面的句点 **(.)** 让Python对变量name执行方法 ***title()*** 指定的操作。每个方法后面都跟着一对括号，这是因为方法通常需要额外的信息来完成其工作。这种信息是在括号内提供的。函数 ***title()*** 不需要额外的信息，因此它后面的括号是空的。  
在Python中，注释用井号（#）标识。井号后面的内容都会被Python解释器忽略。

## 常用函数

### print() 函数
**描述**  
***print()*** 方法用于打印输出，最常见的一个函数  
**语法**  
***print()*** 方法的语法:
```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)  
```
**参数**  
`objects` -- 复数，表示可以一次输出多个对象。输出多个对象时，需要用 \[,] 分隔。  
`sep` -- 用来间隔多个对象，默认值是一个空格。  
`end` -- 用来设定以什么结尾。默认值是换行符 \[\n] ，我们可以换成其他字符串。如果要实现不换行需要在变量末尾加上 end=""。  
`file` -- 要写入的文件对象。  
`flush` -- 输出是否被缓存通常决定于 file，但如果 flush 关键字参数为 True，流会被强制刷新。  
**返回值**  
无

### title() 方法
**描述**
Python ***title()*** 方法返回"标题化"的字符串，就是说所有单词的首个字母转化为大写，其余字母均为小写(见 istitle())。  
**语法**  
***title()*** 方法语法：
```python
str.title()
```
**参数**  
NA。  
**返回值**  
返回"标题化"的字符串,就是说所有单词的首字母都转化为大写。  
**实例**  
以下实例展示了 title()函数的使用方法：  
实例(Python 3.0+)
```python
#!/usr/bin/python3
 
str = "this is string example from runoob....wow!!!"
print (str.title())
```
以上实例输出结果如下：
>This Is String Example From Runoob....Wow!!!

请注意，非字母后的第一个字母将转换为大写字母：  
实例(Python 3.0+)
```python
#!/usr/bin/python3

txt = "hello b2b2b2 and 3g3g3g"
x = txt.title()
print(x)
```
输出结果为：
>Hello B2B2B2 And 3G3G3G

### istitle() 方法
**描述**  
***istitle()*** 方法检测字符串中所有的单词拼写首字母是否为大写，且其他字母为小写。  
**语法**  
***istitle()*** 方法语法：  
```python
str.istitle()
```
**参数**  
无。  
**返回值**  
如果字符串中所有的单词拼写首字母是否为大写，且其他字母为小写则返回 True，否则返回 False。  
**实例**  
以下实例展示了 ***istitle()*** 方法的实例：  
实例
```python
#!/usr/bin/python3
 
str = "This Is String Example...Wow!!!"
print (str.istitle())
 
str = "This is string example....wow!!!"
print (str.istitle())
```
以上实例输出结果如下：
>True  
>False

### upper() 方法
**描述**  
Python ***upper()*** 方法将字符串中的小写字母转为大写字母。  
**语法**  
***upper()*** 方法语法：
```python
str.upper()
```
**参数**  
NA。  
**返回值**  
返回小写字母转为大写字母的字符串。  
**实例**  
以下实例展示了 ***upper()*** 函数的使用方法：
```python
#!/usr/bin/python3

str = "this is string example from runoob....wow!!!";

print ("str.upper() : ", str.upper())
```
以上实例输出结果如下：
>str.upper() :  THIS IS STRING EXAMPLE FROM RUNOOB....WOW!!!

### lower() 方法
**描述**  
Python ***lower()*** 方法转换字符串中所有大写字符为小写。  
**语法**  
***lower()*** 方法语法：
```python
str.lower()
```
**参数**  
无。  
**返回值**  
返回将字符串中所有大写字符转换为小写后生成的字符串。  
**实例**
以下实例展示了 ***lower()*** 的使用方法：
```python
#!/usr/bin/python3

str = "Runoob EXAMPLE....WOW!!!"

print(str.lower())
```
以上实例输出结果如下：
>runoob example....wow!!!

### rstrip() 方法
**描述**  
***rstrip()*** 删除 string 字符串末尾的指定字符（默认为空格）。  
**语法**  
***rstrip()*** 方法语法：
```python
str.rstrip([chars])
```
**参数**  
`chars` -- 指定删除的字符（默认为空格）  
**返回值**  
返回删除 string 字符串末尾的指定字符后生成的新字符串。  
**实例**  
以下实例展示了rstrip()函数的使用方法：  
实例
```python
#!/usr/bin/python3

str = "     this is string example....wow!!!     "
print (str.rstrip())
str = "*****this is string example....wow!!!*****"
print (str.rstrip('*'))
```
以上实例输出结果如下：
>     this is string example....wow!!!  
>*****this is string example....wow!!!

### lstrip() 方法
**描述**  
lstrip() 方法用于截掉字符串左边的空格或指定字符。  
**语法**  
lstrip()方法语法：
```python
str.lstrip([chars])
```
**参数**  
`chars` --指定截取的字符。  
**返回值**  
返回截掉字符串左边的空格或指定字符后生成的新字符串。  
**实例**  
以下实例展示了lstrip()的使用方法：  
实例
```python
#!/usr/bin/python3

str = "     this is string example....wow!!!     ";
print(str.lstrip())
str = "88888888this is string example....wow!!!8888888";
print(str.lstrip('8'))
```
以上实例输出结果如下：
>this is string example....wow!!!     
>this is string example....wow!!!8888888

### strip() 方法
**描述**  
Python strip() 方法用于移除字符串头尾指定的字符（默认为空格）或字符序列。  
注意：该方法只能删除开头或是结尾的字符，不能删除中间部分的字符。  
**语法**  
strip()方法语法：
```python
str.strip([chars]);
```
**参数**  
`chars` -- 移除字符串头尾指定的字符序列。  
**返回值**  
返回移除字符串头尾指定的字符序列生成的新字符串。  
**实例**  
以下实例展示了 strip() 函数的使用方法：  
实例(Python 3.0+)
```python
#!/usr/bin/python3
 
str = "*****this is **string** example....wow!!!*****"
print (str.strip('*'))  # 指定字符串 *
```
以上实例输出结果如下：
>this is **string** example....wow!!!

从结果上看，可以注意到中间部分的字符并未删除。  
以上下例演示了只要头尾包含有指定字符序列中的字符就删除：  
实例(Python 3.0+)
```python
#!/usr/bin/python3
 
str = "123abcrunoob321"
print (str.strip('12'))  # 字符序列为 12
```
以上实例输出结果如下：
>3abcrunoob3

### type() 函数
**描述**  
***type()*** 函数如果你只有第一个参数则返回对象的类型，三个参数返回新的类型对象。  
***isinstance()*** 与 ***type()*** 区别：  
***type()*** 不会认为子类是一种父类类型，不考虑继承关系。  
***isinstance()*** 会认为子类是一种父类类型，考虑继承关系。  
如果要判断两个类型是否相同推荐使用 ***isinstance()*** 。  
**语法**  
以下是 ***type()*** 方法的语法:
```python
type(object)
type(name, bases, dict)
```
**参数**  
`name` -- 类的名称。  
`bases` -- 基类的元组。  
`dict` -- 字典，类内定义的命名空间变量。  
**返回值**  
一个参数返回对象类型, 三个参数，返回新的类型对象。

### isinstance() 函数
**描述**  
***isinstance()*** 函数来判断一个对象是否是一个已知的类型，类似 type()。  
***isinstance()*** 与 ***type()*** 区别：  
***type()*** 不会认为子类是一种父类类型，不考虑继承关系。  
***isinstance()*** 会认为子类是一种父类类型，考虑继承关系。  
如果要判断两个类型是否相同推荐使用 ***isinstance()*** 。  
**语法**  
以下是 isinstance() 方法的语法:
```python
isinstance(object, classinfo)
```
**参数**  
`object` -- 实例对象。  
`classinfo` -- 可以是直接或间接类名、基本类型或者由它们组成的元组。  
**返回值**  
如果对象的类型与参数二的类型（classinfo）相同则返回 True，否则返回 False。

### issubclass() 函数
**描述**  
***issubclass()*** 方法用于判断参数 class 是否是类型参数 classinfo 的子类。  
**语法**  
以下是 ***issubclass()*** 方法的语法:
```python
issubclass(class, classinfo)
```
**参数**  
`class` -- 类。  
`classinfo` -- 类。  
**返回值**  
如果 class 是 classinfo 的子类返回 True，否则返回 False。

### enumerate() 函数
**描述**  
***enumerate()*** 函数用于将一个可遍历的数据对象(如列表、元组或字符串)组合为一个索引序列，同时列出数据和数据下标，一般用在 for 循环当中。  
**语法**  
以下是 ***enumerate()*** 方法的语法:
```python
enumerate(sequence, [start=0])
```
**参数**  
`sequence` -- 一个序列、迭代器或其他支持迭代对象。  
`start` -- 下标起始位置。  
**返回值**  
返回 enumerate(枚举) 对象。  
**实例**  
以下展示了使用 ***enumerate()*** 方法的实例：
```python
seasons = ['Spring', 'Summer', 'Fall', 'Winter']
list(enumerate(seasons))
```
>[(0, 'Spring'), (1, 'Summer'), (2, 'Fall'), (3, 'Winter')]
```python
list(enumerate(seasons, start=1))       # 小标从 1 开始
```
>[(1, 'Spring'), (2, 'Summer'), (3, 'Fall'), (4, 'Winter')]

[参考资料](https://www.runoob.com/python3/python3-func-enumerate.html)


## 列表
Python中列表是可变的，这是它区别于字符串和元组的最重要的特点，一句话概括即：**列表可以修改，而字符串和元组不能。**
以下是 Python 中列表的方法：
|方法|描述
|:-:|:-
|list.append(x)|把一个元素添加到列表的结尾，相当于 a\[len(a):] = \[x]。
|list.extend(L)|通过添加指定列表的所有元素来扩充列表，相当于 a\[len(a):] = L。
|list.insert(i, x)|在指定位置插入一个元素。第一个参数是准备插入到其前面的那个元素的索引，例如 a.insert(0, x) 会插入到整个列表之前，而 a.insert(len(a), x) 相当于 a.append(x) 。
|list.remove(x)|删除列表中值为 x 的第一个元素。如果没有这样的元素，就会返回一个错误。
|list.pop(\[i])|从列表的指定位置移除元素，并将其返回。如果没有指定索引，a.pop()返回最后一个元素。元素随即从列表中被移除。（方法中 i 两边的方括号表示这个参数是可选的，而不是要求你输入一对方括号，你会经常在 Python 库参考手册中遇到这样的标记。）
|list.clear()|移除列表中的所有项，等于del a\[:]。
|list.index(x)|返回列表中第一个值为 x 的元素的索引。如果没有匹配的元素就会返回一个错误。
|list.count(x)|返回 x 在列表中出现的次数。
|list.sort()|对列表中的元素进行排序。
|list.reverse()|反向列表中的元素。
|list.copy()|返回列表的浅复制，等于a\[:]。

### List.list() 方法
**描述**  
***list()*** 方法用于将元组或字符串转换为列表。  
注：元组与列表是非常类似的，区别在于元组的元素值不能修改，元组是放在括号中，列表是放于方括号中。  
**语法**  
***list()*** 方法语法：
```python
list( seq )
```
**参数**  
`seq` -- 要转换为列表的元组或字符串。  
**返回值**  
返回列表。

### List.append() 方法
**描述**  
***append()*** 方法用于在列表末尾添加新的对象。  
**语法**  
***append()*** 方法语法：
```python
list.append(obj)
```
**参数**  
`obj` -- 添加到列表末尾的对象。  
**返回值**  
该方法无返回值，但是会修改原来的列表。

### List.extend() 方法
**描述**  
***extend()*** 函数用于在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表）。  
**语法**  
***extend()*** 方法语法：
```python
list.extend(seq)
```
**参数**  
`seq` -- 元素列表，可以是列表、元组、集合、字典，*若为字典，则仅会将键(key)作为元素依次添加至原列表的末尾*。  
**返回值**  
该方法没有返回值，但会在已存在的列表中添加新的列表内容。

### List.insert() 方法
**描述**  
***insert()*** 函数用于将指定对象插入列表的指定位置。  
**语法**  
***insert()*** 方法语法：
```python
list.insert(index, obj)
```
**参数**  
`index` -- 对象obj需要插入的索引位置。  
`obj` -- 要插入列表中的对象。  
**返回值**  
该方法没有返回值，但会在列表指定位置插入对象。

### List.remove() 方法
**描述**  
***remove()*** 函数用于移除列表中某个值的第一个匹配项。  
**语法**  
***remove()*** 方法语法：
```python
list.remove(obj)
```
**参数**  
`obj` -- 列表中要移除的对象。  
**返回值**  
该方法没有返回值但是会移除列表中的某个值的第一个匹配项。

### List.pop() 方法
**描述**  
***pop()*** 函数用于移除列表中的一个元素（默认最后一个元素），并且返回该元素的值。  
**语法**  
***pop()*** 方法语法：
```python
list.pop([index=-1])
```
**参数**  
`index` -- 可选参数，要移除列表元素的索引值，不能超过列表总长度，默认为 index=-1，删除最后一个列表值。  
**返回值**  
该方法返回从列表中移除的元素对象。

### del 语句
**概述**
使用 ***del*** 语句可以从一个列表中依索引而不是值来删除一个元素。这与使用 ***pop()*** 返回一个值不同。可以用 ***del*** 语句从列表中删除一个切割，或清空整个列表（ ***clear()*** ）。例如：
>\>>> a = [-1, 1, 66.25, 333, 333, 1234.5]  
>\>>> del a[0]  
>\>>> a  
[1, 66.25, 333, 333, 1234.5]  
>\>>> del a[2:4]  
>\>>> a  
[1, 66.25, 1234.5]  
>\>>> del a[:]  
>\>>> a  
[]

### List.count() 方法
**描述**  
***count()*** 方法用于统计某个元素在列表中出现的次数。  
**语法**  
***count()*** 方法语法：
```python
list.count(obj)
```
**参数**  
`obj` -- 列表中统计的对象。  
**返回值**  
返回元素在列表中出现的次数。

### List.reverse() 方法
**描述**  
***reverse()*** 函数用于反向列表中元素。  
**语法**  
***reverse()*** 方法语法：
```python
list.reverse()
```
**参数**  
NA。  
**返回值**  
该方法没有返回值，但是会对列表的元素进行反向排序。

### List.sort() 方法
**描述**  
***sort()*** 函数用于对原列表进行排序，如果指定参数，则使用比较函数指定的比较函数。  
**语法**  
***sort()*** 方法语法：
```python
list.sort( key=None, reverse=False)
```
**参数**  
`key` -- 主要是用来进行比较的元素，只有一个参数，具体的函数的参数就是取自于可迭代对象中，指定可迭代对象中的一个元素来进行排序。  
`reverse` -- 排序规则，reverse = True 降序， reverse = False 升序（默认）。  
**返回值**  
该方法没有返回值，但是会对列表的对象进行排序。

### List.index() 方法
**描述**  
***index()*** 函数用于从列表中找出某个值第一个匹配项的索引位置。  
**语法**  
***index()*** 方法语法：
```python
list.index(str, start=0, stop=len(string))
```
**参数**  
`str` -- 指定检索的字符串，即查找的对象。  
`start` -- 开始索引，默认为0。  
`stop` -- 结束索引，默认为字符串的长度。  
**返回值**  
该方法返回查找对象的索引位置，如果没有找到对象则抛出异常。

### List.copy() 方法
**描述**  
***copy()*** 函数用于复制列表，类似于 a\[:]。  
**语法**  
***copy()*** 方法语法：
```python
list.copy()
```
**参数**  
无。  
**返回值**  
返回复制后的新列表。


## 字典
方法|描述
:-:|:-
dict.clear()|删除字典内所有元素
dict.copy()|返回一个字典的复制
dict.fromkeys()|创建一个新字典，以序列seq中元素做字典的键，val为字典所有键对应的初始值
dict.get(key,default=None)|返回指定键的值，如果键不在字典中返回 default 设置的默认值
dict.items()|返回包含每个键值对的元组的列表
dict.keys()|返回包含所有键的列表
dict.values()|返回包含所有值的列表
key in dict|如果键在字典dict里返回true，否则返回false
dict.setdefault(key, default=None)|和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default
dict.update(dict2)|把字典dict2的键/值对更新到dict里
pop(key\[,default])|删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。
dict.popitem()|返回并删除字典中的最后一对键和值。

### dict.get() 方法
**描述**  
Python 字典 ***get()*** 函数返回指定键的值。  
**语法**  
***get()*** 方法语法：
```python
dict.get(key, default=None)
```
**参数**  
`key` -- 字典中要查找的键。  
`default` -- 如果指定的键不存在时，返回该默认值。  
**返回值**  
返回指定键的值，如果键不在字典中返回默认值 None 或者指定的默认值。

### dict.update() 方法
**描述**  
Python 字典 ***update()*** 函数把字典参数 dict2 的 key/value(键/值) 对更新到字典 dict 里。  
**语法**  
***update()*** 方法语法:
```python
dict.update(dict2)
```
**参数**  
`dict2` -- 添加到指定字典dict里的字典。  
**返回值**  
该方法没有任何返回值。  
**实例**  
以下实例展示了 update()函数的使用方法：  
```python
#!/usr/bin/python3
 
dict = {'Name': 'Runoob', 'Age': 7}
dict2 = {'Sex': 'female' }
 
dict.update(dict2)
print ("更新字典 dict : ", dict)
```
以上实例输出结果为：
>更新字典 dict :  {'Name': 'Runoob', 'Age': 7, 'Sex': 'female'}

### dict.items() 方法
**描述**  
Python 字典(Dictionary) ***items()*** 方法以列表返回可遍历的(键, 值) 元组数组。  
**语法**  
***items()*** 方法语法：
```python
dict.items()
```
**参数**  
NA。  
**返回值**  
返回可遍历的(键, 值) 元组数组。

### dict.keys() 方法
**描述**  
Python 字典(Dictionary) ***keys()*** 函数以列表返回一个字典所有的键。  
**语法**  
***keys()*** 方法语法：
```python
dict.keys()
```
**参数**  
NA。  
**返回值**  
返回一个字典所有的键。

### dict.values() 方法
**描述**  
Python 字典(Dictionary) ***values()*** 函数以列表返回字典中的所有值。  
**语法**  
***values()*** 方法语法：
```python
dict.values()
```
**参数**  
NA。  
**返回值**  
返回字典中的所有值。

### dict.setdefault() 方法
**描述**  
Python 字典 ***setdefault()*** 方法和 **get()** 方法类似, 如果键已经不存在于字典中，将会添加键并将值设为默认值。  
**语法**  
***setdefault()*** 方法语法：
```python
dict.setdefault(key, default=None)
```
**参数**  
`key` -- 查找的键值。  
`default` -- 键不存在时，设置的默认键值。  
**返回值**  
如果 key 在 字典中，返回对应的值。如果不在字典中，则插入 key 及设置的默认值 default，并返回 default ，default 默认值为 None。


## 文件函数

### File.read() 方法
**概述**  
***read()*** 方法用于从文件读取指定的字节数，如果未给定或为负则读取所有。  
读取文件的全部内容，并将其作为一个长长的字符串存储在变量中。***read()*** 到达文件末尾时会返回一个空字符串，而将这个空字符串显示出来时就是一个空行。要删除多出来的空行，可使用 ***rstrip()*** 来删除空字符串。  
**语法**  
***read()*** 方法语法如下：
```python
fileObject.read([size])
```
**参数**  
`size` -- 从文件中读取的字节数，默认为 -1，表示读取整个文件。  
**返回值**  
返回从字符串中读取的字节。

### File.write() 方法
**概述**  
***write()*** 方法用于向文件中写入指定字符串。  
在文件关闭前或缓冲区刷新前，字符串内容存储在缓冲区中，这时你在文件中是看不到写入的内容的。  
如果文件打开模式带 b，那写入文件内容时，***str(参数)*** 要用 encode 方法转为 bytes 形式，否则报错：
>TypeError: a bytes-like object is required, not 'str'。

将一个字符串写入文件。函数 ***write()*** 不会在写入的文本末尾添加换行符。要让每个字符串都单独占一行，需要在 ***write()*** 语句中包含换行符。  
**语法**  
***write()*** 方法语法如下：
```python
fileObject.write([str])
```
**参数**  
`str` -- 要写入文件的字符串。  
**返回值**  
返回的是写入的字符长度。  

### File.readlines()方法
**概述**  
***readlines()*** 方法用于读取所有行(直到结束符 EOF)并返回列表，该列表可以由 Python 的 for... in ... 结构进行处理。 如果碰到结束符 EOF 则返回空字符串。  
如果碰到结束符 EOF 则返回空字符串。  
**语法**  
***readlines()*** 方法语法如下：
```python
fileObject.readlines()
```
**参数**  
无。  
**返回值**  
返回列表，包含所有的行。

### open() 函数
**描述**  
Python ***open()*** 函数用于打开一个文件，并返回文件对象，在对文件进行处理过程都需要使用到这个函数，如果该文件无法被打开，会抛出 OSError。  
**注意**  
使用 ***open()*** 函数一定要保证关闭文件对象，即调用 ***close()*** 函数。  
***open()*** 函数常用形式是接收两个参数：文件名 (file) 和模式 (mode) 。
```python
open(file, mode='r')
```
完整的语法格式为：
```python
open(file, mode='r', buffering=-1, encoding=None, errors=None, newline=None, closefd=True, opener=None)
```
**参数说明**  
`file`: 必需，文件路径（相对或者绝对路径）。  
`mode`: 可选，文件打开模式  
`buffering`: 设置缓冲  
`encoding`: 一般使用utf8  
`errors`: 报错级别  
`newline`: 区分换行符  
`closefd`: 传入的file参数类型  
`opener`:   
mode 参数有：
模式|描述
:-:|:-
t|文本模式 (默认)。
x|写模式，新建一个文件，如果该文件已存在则会报错。
b|二进制模式。
+|打开一个文件进行更新(可读可写)。
U|通用换行模式（不推荐）。
r|以只读方式打开文件。文件的指针将会放在文件的开头。这是默认模式。
rb|以二进制格式打开一个文件用于只读。文件指针将会放在文件的开头。这是默认模式。一般用于非文本文件如图片等。
r+|打开一个文件用于读写。文件指针将会放在文件的开头。
rb+|以二进制格式打开一个文件用于读写。文件指针将会放在文件的开头。一般用于非文本文件如图片等。
w|打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
wb|以二进制格式打开一个文件只用于写入。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。
w+|打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。
wb+|以二进制格式打开一个文件用于读写。如果该文件已存在则打开文件，并从开头开始编辑，即原有内容会被删除。如果该文件不存在，创建新文件。一般用于非文本文件如图片等。
a|打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。
ab|以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。也就是说，新的内容将会被写入到已有内容之后。如果该文件不存在，创建新文件进行写入。
a+|打开一个文件用于读写。如果该文件已存在，文件指针将会放在文件的结尾。文件打开时会是追加模式。如果该文件不存在，创建新文件用于读写。
ab+|以二进制格式打开一个文件用于追加。如果该文件已存在，文件指针将会放在文件的结尾。如果该文件不存在，创建新文件用于读写。

默认为文本模式，如果要以二进制模式打开，加上 b 。

### os.open() 方法
**概述**  
***os.open()*** 方法用于打开一个文件，并且设置需要的打开选项，模式参数mode参数是可选的，默认为 0777。  
**语法**  
***open()*** 方法语法格式如下：
```python
os.open(file, flags[, mode])
```
**参数**  
`file` -- 要打开的文件  
`flags` -- 该参数可以是以下选项，多个使用 "|" 隔开：  
* os.O_RDONLY: 以只读的方式打开  
* os.O_WRONLY: 以只写的方式打开  
* os.O_RDWR : 以读写的方式打开  
* os.O_NONBLOCK: 打开时不阻塞  
* os.O_APPEND: 以追加的方式打开  
* os.O_CREAT: 创建并打开一个新文件  
* os.O_TRUNC: 打开一个文件并截断它的长度为零（必须有写权限）  
* os.O_EXCL: 如果指定的文件存在，返回错误  
* os.O_SHLOCK: 自动获取共享锁  
* os.O_EXLOCK: 自动获取独立锁  
* os.O_DIRECT: 消除或减少缓存效果  
* os.O_FSYNC : 同步写入  
* os.O_NOFOLLOW: 不追踪软链接

`mode` -- 类似 chmod() 。  
**返回值**  
返回新打开文件的描述符。


## 其他函数

### join() 方法
**描述**  
Python ***join()*** 方法用于将序列中的元素以指定的字符连接生成一个新的字符串。  
**语法**  
***join()*** 方法语法：
```python
str.join(sequence)
```
**参数**  
`sequence` -- 要连接的元素序列。  
**返回值**  
返回通过指定字符连接序列中元素后生成的新字符串。

### count() 方法
**描述**  
***count()*** 方法用于统计字符串里某个字符出现的次数。可选参数为在字符串搜索的开始与结束位置。  
**语法**  
***count()*** 方法语法：
```python
str.count(sub, start= 0,end=len(string))
```
**参数**  
`sub` -- 搜索的子字符串  
`start` -- 字符串开始搜索的位置。默认为第一个字符,第一个字符索引值为0。  
`end` -- 字符串中结束搜索的位置。字符中第一个字符的索引为 0。默认为字符串的最后一个位置。  
**返回值**  
该方法返回子字符串在字符串中出现的次数。

### clear() 方法

#### dict.clear() 方法
**描述**  
Python 字典 ***clear()*** 函数用于清空字典内所有元素。  
**语法**  
***clear()*** 方法语法：
```python
dict.clear()
```
**参数**  
NA。  
**返回值**  
该方法最终返回一个空字典。

#### List.clear() 方法
**描述**  
***clear()*** 函数用于清空列表，类似于 del a\[:]。  
**语法**  
***clear()*** 方法语法：
```python
list.clear()
```
**参数**  
无。  
**返回值**  
该方法最终返回一个空列表。

### range() 函数
**描述**  
Python3 ***range()*** 函数返回的是一个可迭代对象（类型是对象），而不是列表类型， 所以打印的时候不会打印列表。  
Python3 ***list()*** 函数是对象迭代器，可以把 ***range()*** 返回的可迭代对象转为一个列表，返回的变量类型为列表。  
Python2 ***range()*** 函数返回的是列表。  
**语法**
```python
range(stop)
range(start, stop[, step])
```
**参数**  
`start`: 计数从 start 开始。默认是从 0 开始。例如 range(5) 等价于 range(0, 5);  
`stop`: 计数到 stop 结束，但不包括 stop。例如：range(0, 5) 是[0, 1, 2, 3, 4]没有5;  
`step`：步长，默认为1。例如：range(0, 5) 等价于 range(0, 5, 1);  
**返回值**  
NA。

### break 语句
Python ***break*** 语句，就像在C语言中，打破了最小封闭 ***for*** 或 ***while*** 循环。  
***break*** 语句用来终止循环语句，即循环条件没有False条件或者序列还没被完全递归完，也会停止执行循环语句。  
***break*** 语句用在 ***while*** 和 ***for*** 循环中。  
如果使用嵌套循环，***break*** 语句将停止执行最深层的循环，并开始执行下一行代码。  
Python语言 ***break*** 语句语法：
```python
break
```
[参考资料](https://www.runoob.com/python/python-break-statement.html)

### continue 语句
Python ***continue*** 语句跳出本次循环，而 ***break*** 跳出整个循环。  
***continue*** 语句用来告诉Python跳过当前循环的剩余语句，然后继续进行下一轮循环。  
***continue*** 语句用在 ***while*** 和 ***for*** 循环中。  
Python 语言 ***continue*** 语句语法格式如下：
```python
continue
```
[参考资料](https://www.runoob.com/python/python-continue-statement.html)

### return 语句
**描述**  
***return*** \[表达式] 语句用于退出函数，选择性地向调用方返回一个表达式。不带参数值的 ***return*** 语句返回None。  
在函数中，可使用 ***return*** 语句将值返回到调用函数的代码行。调用返回值的函数时，需要提供一个变量，用于存储返回的值。  
将 ***return*** 语句放在try语句块中，***return*** 之后的语句还要执行。

### with 关键字
**描述**  
***with*** 在不再需要访问文件后将其关闭。可配合 ***open()*** 使用，从而不用管 ***close()*** 的使用位置  
**用法**
```python
with open(filename,mode) as file:
    with_suite
```
**参数**  
`filename` -- 可以是文件名，也可以是文件存放的相对路径和绝对路径，使用单引号('')或者双引号("")括起来  
`mode` -- 可指定读取模式（***'r'***）、写入模式（***'w'***）、附加模式（***'a'***）或读取和写入文件的模式（***'r+'***）。  
`file` -- 为一个变量，用于存储从 open(filename) 文件中返回的内容  
`with_suite` -- 使用变量 file 对 open(filename) 返回的文件对象进行各种处理，如写入(write())，读取(read())等等  
**返回值**  
使用关键字 ***with*** 时，***open()*** 返回的文件对象只在 ***with*** 代码块内可用。如果要在 ***with*** 代码块外访问文件的内容，可在 ***with*** 代码块内将文件的各行存储在一个列表中，并在with代码块外使用该列表。  
**实例**  
如使用 ***readlines()*** 方法：
```python
with open(filename) as file_object:
    lines = file_object.readlines()
```
这个实例是将filename文件中的内容，使用方法readlines()从文件中读取每一行，并将其存储在一个列表中  
**备注**  
并非在任何情况下都能轻松确定关闭文件的恰当时机，但通过使用上面所示的结构，可让Python去确定：你只管打开文件，并在需要时使用它，Python自会在合适的时候自动将其关闭

### super() 函数
**描述**  
***super()*** 函数是用于调用父类(超类)的一个方法。  
***super()*** 是一个特殊函数，帮助Python将父类和子类关联起来。子类包含父类的所有属性。父类也称为超类（superclass），名称super因此而得名。定义子类时，必须在括号内指定父类的名称。  
***super()*** 是用来解决多重继承问题的，直接用类名调用父类方法在使用单继承的时候没问题，但是如果使用多继承，会涉及到查找顺序（MRO）、重复调用（钻石继承）等种种问题。  
MRO 就是类的方法解析顺序表, 其实也就是继承父类方法时的顺序表。  
**语法**  
以下是 ***super()*** 方法的语法:
```python
super(type[, object-or-type])
```
**参数**  
`type` -- 类。  
`object-or-type` -- 类，一般是 self  
**返回值**  
无。

### count() 方法
**描述**  
***count()*** 方法用于统计字符串里某个字符出现的次数。可选参数为在字符串搜索的开始与结束位置。  
**语法**  
***count()*** 方法语法：
```python
str.count(sub, start= 0,end=len(string))
```
**参数**  
`sub` -- 搜索的子字符串  
`start` -- 字符串开始搜索的位置。默认为第一个字符,第一个字符索引值为0。  
`end` -- 字符串中结束搜索的位置。字符中第一个字符的索引为 0。默认为字符串的最后一个位置。  
**返回值**  
该方法返回子字符串在字符串中出现的次数。

### split() 方法
**描述**  
***split()*** 通过指定分隔符对字符串进行切片，如果第二个参数 num 有指定值，则分割为 num+1 个子字符串。
它根据一个字符串创建一个单词列表。方法 ***split()*** 以空格为分隔符将字符串分拆成多个部分，并将这些部分都存储到一个列表中。结果是一个包含字符串中所有单词的列表，虽然有些单词可能包含标点。  
**语法**  
***split()*** 方法语法：
```python
str.split(str="", num=string.count(str))
```
**参数**  
`str` -- 分隔符，默认为所有的空字符，包括空格、换行(\n)、制表符(\t)等。  
`num` -- 分割次数。默认为 -1, 即分隔所有。  
**返回值**  
返回分割后的字符串列表。

### eval()函数
**描述**  
***eval()*** 函数用来执行一个字符串表达式，并返回表达式的值。  
**语法**  
以下是 ***eval()*** 方法的语法:
```python
eval(expression[, globals[, locals]])
```
**参数**  
`expression` -- 表达式。  
`globals` -- 变量作用域，全局命名空间，如果被提供，则必须是一个字典对象。  
`locals` -- 变量作用域，局部命名空间，如果被提供，可以是任何映射对象。  
**返回值**  
返回表达式计算结果。

### ceil()函数
**描述**  
***ceil(x)*** 函数返回一个大于或等于 x 的的最小整数。即向上取整。  
**语法**  
以下是 ***ceil()*** 方法的语法:
```python
import math
math.ceil(x)
```
注意：***ceil()*** 是不能直接访问的，需要导入 ***math*** 模块，通过静态对象调用该方法。  
**参数**  
`x` -- 数值表达式。  
**返回值**  
函数返回返回一个大于或等于 x 的的最小整数。

### floor()函数
**描述**  
***floor(x)*** 返回数字的下舍整数，小于或等于 x 。即向下取整。  
**语法**  
以下是 ***floor()*** 方法的语法:
```python
import math
math.floor(x)
```
注意：***floor()*** 是不能直接访问的，需要导入 math 模块，通过静态对象调用该方法。  
**参数**  
`x` -- 数值表达式。  
**返回值**  
返回小于或等于 x 的整数。

### 模块 json
使用 JSON 函数需要导入 json 库：import json。
函数|描述
:-:|:-
json.dump()|接受两个实参：要存储的数据以及可用于存储数据的文件对象。
json.load()|读取存储在.json中的内容到内存中

#### json.dumps()
**描述**  
***json.dumps()*** 用于将 Python 对象编码成 JSON 字符串。  
**语法**
```python
json.dumps(obj, skipkeys=False, ensure_ascii=True, check_circular=True, allow_nan=True, cls=None, indent=None, separators=None, encoding="utf-8", default=None, sort_keys=False, **kw)
```
**实例**  
以下实例将数组编码为 JSON 格式数据：  
实例
```python
#!/usr/bin/python
import json

data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]

data2 = json.dumps(data)
print(data2)
```
以上代码执行结果为：
>[{"a": 1, "c": 3, "b": 2, "e": 5, "d": 4}]

使用参数让 JSON 数据格式化输出：  
实例
```python
#!/usr/bin/python
import json

data = [ { 'a' : 1, 'b' : 2, 'c' : 3, 'd' : 4, 'e' : 5 } ]

data2 = json.dumps({'a': 'Runoob', 'b': 7}, sort_keys=True, indent=4, separators=(',', ': '))
print(data2)
```
以上代码执行结果为：
>{  
>&emsp;&emsp;"a": "Runoob",  
>&emsp;&emsp;"b": 7  
>}

python 原始类型向 json 类型的转化对照表：
Python|JSON
:-:|:-
dict|object
list, tuple|array
str, unicode|string
int, long, float|number
True|true
False|false
None|null

#### json.loads()
**描述**  
***json.loads()*** 用于解码 JSON 数据。该函数返回 Python 字段的数据类型。  
**语法**
```python
json.loads(s[, encoding[, cls[, object_hook[, parse_float[, parse_int[, parse_constant[, object_pairs_hook[, **kw]]]]]]]])
```
**实例**  
以下实例展示了Python 如何解码 JSON 对象：  
实例
```python
#!/usr/bin/python
import json

jsonData = '{"a":1,"b":2,"c":3,"d":4,"e":5}';

text = json.loads(jsonData)
print(text)
```
以上代码执行结果为：
>{u'a': 1, u'c': 3, u'b': 2, u'e': 5, u'd': 4}

json 类型转换到 python 的类型对照表：
JSON|Python
:-:|:-
object|dict
array|list
string|unicode
number (int)|int, long
number (real)|float
true|True
false|False
null|None

### random()函数
**描述**  
***random()*** 方法返回随机生成的一个实数，它在[0,1) ***(左闭右开区间)*** 范围内。  
**语法**  
以下是 ***random()*** 方法的语法:
```python
import random
random.random()
```
*注意*：random()是不能直接访问的，需要导入 random 模块，然后通过 random 静态对象调用该方法。  
**参数**  
无  
**返回值**  
返回随机生成的一个实数，它在[0,1)范围内。  
random 模块的 randint() 函数来生成随机数， randint()返回一个位于指定范围内的整数  
函数的语法为：
```python
random.randint(a,b)
```
函数返回数字 N ，N 为 a 到 b 之间的数字（a <= N <= b），包含 a 和 b。

### bytes.decode()方法
**描述**  
***decode()*** 方法以指定的编码格式解码 bytes 对象。默认编码为 'utf-8'。  
**语法**  
***decode()*** 方法语法：
```python
bytes.decode(encoding="utf-8", errors="strict")
```
**参数**  
`encoding` -- 要使用的编码，如"UTF-8"。  
`errors` -- 设置不同错误的处理方案。默认为 'strict'，意为编码错误引起一个UnicodeError。其他可能得值有 'ignore', 'replace', 'xmlcharrefreplace', 'backslashreplace' 以及通过 codecs.register_error() 注册的任何值。  
**返回值**  
该方法返回解码后的字符串。

### replace()方法
**描述**  
Python ***replace()*** 方法把字符串中的 old（旧字符串） 替换成 new (新字符串)，如果指定第三个参数max，则替换不超过 max 次。  
**语法**  
***replace()*** 方法语法：
```python
str.replace(old, new[, max])
```
**参数**  
`old` -- 将被替换的子字符串。  
`new` -- 新字符串，用于替换old子字符串。  
`max` -- 可选字符串, 替换不超过 max 次  
**返回值**  
返回字符串中的 old（旧字符串） 替换成 new (新字符串) 后生成的新字符串，如果指定第三个参数max，则替换不超过 max 次。

### format 格式化函数
Python2.6 开始，新增了一种格式化字符串的函数 ***str.format()***，它增强了字符串格式化的功能。  
基本语法是通过 {} 和 : 来代替以前的 % 。  
format 函数可以接受不限个参数，位置可以不按顺序。  
**实例**
```python
"{} {}".format("hello", "world")    # 不设置指定位置，按默认顺序
```
>'hello world'
```python
"{0} {1}".format("hello", "world")  # 设置指定位置
```
>'hello world'
```python
"{1} {0} {1}".format("hello", "world")  # 设置指定位置
```
>'world hello world'

[参考资料](https://www.runoob.com/python/att-string-format.html)

### compile() 函数
**描述**  
***compile()*** 函数将一个字符串编译为字节代码。  
**语法**  
以下是 ***compile()*** 方法的语法:
```python
compile(source, filename, mode[, flags[, dont_inherit]])
```
**参数**  
`source` -- 字符串或者AST（Abstract Syntax Trees）对象。  
`filename` -- 代码文件名称，如果不是从文件读取代码则传递一些可辨认的值。  
`mode` -- 指定编译代码的种类。可以指定为 exec, eval, single。  
`flags` -- 变量作用域，局部命名空间，如果被提供，可以是任何映射对象。  
*flags* 和 *dont_inherit* 是用来控制编译源码时的标志  
**返回值**  
返回表达式执行结果。


## 正则表达式 (re模块)

### 正则表达式
**概述**  
正则表达式(Regular Expression)是一种文本模式，包括普通字符（例如，a 到 z 之间的字母）和特殊字符（称为"元字符"）。  
正则表达式使用单个字符串来描述、匹配一系列匹配某个句法规则的字符串。  
许多程序设计语言都支持利用正则表达式进行字符串操作。  
[参考资料1](https://www.runoob.com/regexp/regexp-tutorial.html)
[参考资料2](https://www.runoob.com/python3/python3-reg-expressions.html)

#### re.match 函数
**概述**  
re.match 尝试从字符串的起始位置匹配一个模式，如果不是起始位置匹配成功的话，match()就返回none。  
**函数语法**：  
```python
re.match(pattern, string, flags=0)
```
**参数说明**  
`pattern` -- 匹配的正则表达式  
`string` -- 要匹配的字符串  
`flags` -- 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。  
**返回值**  
匹配成功re.match方法返回一个匹配的对象，否则返回None。

#### re.search 函数
**概述**  
***re.search*** 扫描整个字符串并返回第一个成功的匹配。  
**函数语法**：
```python
re.search(pattern, string, flags=0)
```
**参数说明**  
`pattern` -- 匹配的正则表达式  
`string` -- 要匹配的字符串  
`flags` -- 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。  
**返回值**  
匹配成功 ***re.match*** 方法返回一个匹配的对象，否则返回 None。  
***re.match*** 只匹配字符串的开始，如果字符串开始不符合正则表达式，则匹配失败，函数返回 None，而 ***re.search*** 匹配整个字符串，直到找到一个匹配。

### 检索和替换

#### re.sub方法
**概述**  
Python 的re模块提供了 ***re.sub*** 用于替换字符串中的匹配项。  
**语法**：
```python
re.sub(pattern, repl, string, count=0, flags=0)
```
**参数**：  
`pattern` : 正则中的模式字符串。  
`repl` : 替换的字符串，也可为一个函数。  
`string` : 要被查找替换的原始字符串。  
`count` : 模式匹配后替换的最大次数，默认 0 表示替换所有的匹配。  
`flags` : 编译时用的匹配模式，数字形式。  
**前三个为必选参数，后两个为可选参数。**

#### compile 函数
**概述**  
***compile*** 函数用于编译正则表达式，生成一个正则表达式（ Pattern ）对象，供 ***match()*** 和 ***search()*** 这两个函数使用。  
**语法**：
```python
re.compile(pattern[, flags])
```
**参数**：  
`pattern` : 一个字符串形式的正则表达式  
`flags` 可选，表示匹配模式，比如忽略大小写，多行模式等，具体参数为：
模式|说明
:-:|:-
re.I|忽略大小写
re.L|表示特殊字符集 \w, \W, \b, \B, \s, \S 依赖于当前环境
re.M|多行模式
re.S|即与' . '相同并且包括换行符在内的任意字符（' . '不包括换行符）
re.U|表示特殊字符集 \w, \W, \b, \B, \d, \D, \s, \S 依赖于 Unicode 字符属性数据库
re.X|为了增加可读性，忽略空格和' # '后面的注释

#### findall 方法
**概述**  
在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果没有找到匹配的，则返回空列表。  
注意： ***match*** 和 ***search*** 是匹配一次， ***findall*** 匹配所有。  
**语法**
```python
re.findall(pattern, string, flags=0)
```
或
```python
pattern.findall(string[, pos[, endpos]])
```
**参数**：  
`pattern` -- 匹配模式。  
`string` -- 待匹配的字符串。  
`pos` -- 可选参数，指定字符串的起始位置，默认为 0。  
`endpos` -- 可选参数，指定字符串的结束位置，默认为字符串的长度。  
**返回值**  
返回一个列表，如果没有找到匹配的，则返回空列表。

#### re.finditer
**概述**  
和 findall 类似，在字符串中找到正则表达式所匹配的所有子串，并把它们作为一个迭代器返回。  
**语法格式**：
```python
re.finditer(pattern, string, flags=0)
```
**参数说明**  
`pattern` -- 匹配的正则表达式  
`string` -- 要匹配的字符串  
`flags` -- 标志位，用于控制正则表达式的匹配方式，如：是否区分大小写，多行匹配等等。  
**返回值**  
空

### 正则表达式修饰符 - 可选标志
正则表达式可以包含一些可选标志修饰符来控制匹配的模式。修饰符被指定为一个可选的标志。多个标志可以通过按位 OR(|) 它们来指定。如 re.I | re.M 被设置成 I 和 M 标志：
修饰符|描述
:-:|:-
re.I|使匹配对大小写不敏感
re.L|做本地化识别（locale-aware）匹配
re.M|多行匹配，影响 ^ 和 $
re.S|使 . 匹配包括换行在内的所有字符
re.U|根据Unicode字符集解析字符。这个标志影响 \w, \W, \b, \B.
re.X|该标志通过给予你更灵活的格式以便你将正则表达式写得更易于理解。

### 正则表达式模式
模式字符串使用特殊的语法来表示一个正则表达式：
* 字母和数字表示他们自身。一个正则表达式模式中的字母和数字匹配同样的字符串。
* 多数字母和数字前加一个反斜杠时会拥有不同的含义。
* 标点符号只有被转义时才匹配自身，否则它们表示特殊的含义。
* 反斜杠本身需要使用反斜杠转义。
* 由于正则表达式通常都包含反斜杠，所以你最好使用原始字符串来表示它们。模式元素(如 r'\t'，等价于 \\t )匹配相应的特殊字符。

下表列出了正则表达式模式语法中的特殊元素。如果你使用模式的同时提供了可选的标志参数，某些模式元素的含义会改变。
模式|描述
:-:|:-
^|匹配字符串的开头
$|匹配字符串的末尾。
.|匹配任意字符，除了换行符，当re.DOTALL标记被指定时，则可以匹配包括换行符的任意字符。
[...]|用来表示一组字符,单独列出：[amk] 匹配 'a'，'m'或'k'
[^...]|不在[]中的字符：[^abc] 匹配除了a,b,c之外的字符。
re*|匹配0个或多个的表达式。
re+|匹配1个或多个的表达式。
re?|匹配0个或1个由前面的正则表达式定义的片段，非贪婪方式
re{ n}|匹配n个前面表达式。例如，"o{2}"不能匹配"Bob"中的"o"，但是能匹配"food"中的两个o。
re{ n,}|精确匹配n个前面表达式。例如，"o{2,}"不能匹配"Bob"中的"o"，但能匹配"foooood"中的所有o。"o{1,}"等价于"o+"。"o{0,}"则等价于"o*"。
re{ n, m}|匹配 n 到 m 次由前面的正则表达式定义的片段，贪婪方式
a| b|匹配a或b
(re)|匹配括号内的表达式，也表示一个组
(?imx)|正则表达式包含三种可选标志：i, m, 或 x 。只影响括号中的区域。
(?-imx)|正则表达式关闭 i, m, 或 x 可选标志。只影响括号中的区域。
(?: re)|类似 (...), 但是不表示一个组
(?imx: re)|在括号中使用i, m, 或 x 可选标志
(?-imx: re)|在括号中不使用i, m, 或 x 可选标志
(?#...)|注释.
(?= re)|前向肯定界定符。如果所含正则表达式，以 ... 表示，在当前位置成功匹配时成功，否则失败。但一旦所含表达式已经尝试，匹配引擎根本没有提高；模式的剩余部分还要尝试界定符的右边。
(?! re)|前向否定界定符。与肯定界定符相反；当所含表达式不能在字符串当前位置匹配时成功。
(?> re)|匹配的独立模式，省去回溯。
\w|匹配数字字母下划线
\W|匹配非数字字母下划线
\s|匹配任意空白字符，等价于 [\t\n\r\f]。
\S|匹配任意非空字符
\d|匹配任意数字，等价于 [0-9]。
\D|匹配任意非数字
\A|匹配字符串开始
\Z|匹配字符串结束，如果是存在换行，只匹配到换行前的结束字符串。
\z|匹配字符串结束
\G|匹配最后匹配完成的位置。
\b|匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。
\B|匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。
\n, \t|匹配一个换行符。匹配一个制表符, 等
\1...\9|匹配第n个分组的内容。
\10|匹配第n个分组的内容，如果它经匹配。否则指的是八进制字符码的表达式。


## requests模块
requests对象的 ***get()*** 和 ***post()*** 方法都会返回一个 *Response* 对象，这个对象里面存的是服务器返回的所有信息，包括响应头、响应状态码等。其中返回的网页部分会存在 **.content** 和 **.text** 两个对象中。  
通常而言，在使用python爬虫时，更建议用 ***requests*** 库，因为 ***requests*** 比 ***urllib*** 更为便捷， ***requests*** 可以直接构造 *get* , *post* 请求并发起，而 ***urllib.request*** 只能先构造 *get* ， *post* 请求，再发起请求。

### content
**概述**  
返回的是*bytes*类型的数据，也就是二进制数据  
返回的类型是*bytes*，可以通过 ***decode()*** 方法将 *bytes* 类型转换为 *str* 类型  
主要是在需要获取一些文件的时候使用，比如图片文件、音乐文件、视频文件等  
推荐使用： ***response.content.decode()*** 的方式获取相应的 *html* 页面

### text
**概述**  
返回是就是纯文本（Unicode类型的数据）  
返回的类型是 *str*  
在需要获取一些 *html* 信息等文本信息时使用

### json
**概述**  
返回的是 *json* 格式的数据
