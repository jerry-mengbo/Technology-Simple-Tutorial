## Python极简单教程(2.7)

### 创建一个python程序
将文本保存为`xxx.py`

### 打印
```
print "Hello,World"
```

`print` 默认是换行的，如果你不希望换行，你可以在结尾加上`,`,如果后面在出现print 会接到上一次的打印

```
print "Hello,World",
``` 

### python的语句不需要分号
除非你想要一行代码包含多条语句，你需要加分号  

### 运行python
终端 `cd` 到 脚本所在目录，  
输入 `python xxx.py` 回车 执行脚本

### 进入python控制台
终端数 `python` 回车 即可 进入python控制台

### 添加UTF-8编码
由于`python2.0+`是基于ASCII的所以不识别中文，  
加入中文注释会导致无法运算  
需要在文件最前面两行加入  

```
# -*- coding: UTF-8 -*-
```
或者  

```
#encoding=utf-8
```

### 单引号和多引号
`python`可以使用单引号或者多引号表示字符串  
单引号的字符串中，如果想输入`"`符号则不需要转义
双引号的字符串中，如果想输入`'`符号则不需要转义

```
'He is a "good" boy'
```

### python的注释
`python`用`#`进行代码注释  

```
# 这里的代码不会进行编译
```

用`'''`或者`"""`进行多行注释

```
'''
这是多行注释
这是多行注释
'''

"""
这也是多行注释
这也是多行注释
"""
```

### 使用import关键字,引入其他文件
你可以创建一个文件夹，它被称为`package`(包)  
包下面还可以创建包   
一个`py`文件，被称为`module`（模块）  
你可以通过 `import` 一个模块,来使用模块中的代码  
如`import someModule`或者`import somePackage.someModule`
同时你也可以仅仅引入模块中的某个名字  
如`from someModule import someName`  
不过以`__`(双下划线)命名的变量，不可以被`import`  
模块应该提供共有的方法给予访问  


### 查看python支持的关键字
`keyword`模块下`kwlist`记录了`python`支持的所有关键字

```
import keyword
#kwlist是一个字符串数组
print keyword.kwlist
```

### 学会使用help函数，查看文档
`python` 中可以用`help`函数查看某个关键字或者某个名字（类，变量，函数）的文档  

例如 `help("someKeyword")` 或者 `help(someName)`  
（关键字要加双引号，名字不需要）  

在查看文档的页面，按Q键可以退出

```
help("print")
help(sorted)
```

### 查看系统内建名称
`__builtin__` 库可以让开发者查看所有的系统内建名称

```
import __builtin__
#函数会返回一个字符串数组
print dir(__builtin__)  
```

如果你有足够多的时间,你可以根据`help`函数来系统的学习`python`

### 变量
`python`定义一个变量，不需要声明类型，也不需要用`let`，`var`等关键字

### del 删除变量
可以用del删除变量，不过并不是真正意义的删除，只是如果再用这个变量，会发生运行时错误

### 基本类型
```
counter = 100 # 赋值整型变量 int类型
miles = 1000.0 # 浮点型 float类型
name = "John" # 字符串 str类型
```

值得注意的是 `int` `float` 在`python`中都是`class`

允许动态改变类型  
```
counter = "abc"
```

### 查看变量的类型
```
print type(counter)
```

### 多个变量赋值
```
a = b = c = 1
a,b,c = 1,2,3
```

### 基本数据类型

- 数字类型 `int`,`float` 等
- 布尔类型 `bool`(`True`,`False`首字母大写)
- 字符串类型 `str`
- 列表类型 `list`
- 元组类型 `tuple`
- 字典类型 `dict`

### 数字类型

- `int` 整形
- `long` 长整形
- `float` 浮点型
- `complex` 复数类型

### None关键字
任何类型的变量都可以赋值为`None`，表示空值

### 类型转换
可以使用类型的构造函数进行类型转换  

```
x =  int('15')
```

### 基本运算符

- `+` 加法 `__add__` (可以实现该方法重载运算符，前后双引号)
- `-` 减法 `__sub__`
- `*` 乘法 `__mul__`
- `/` 除法 `__div__`
- `%` 取余 `__mod__`
- `**` 幂运算 `__pow__`
- `//` 除法取证 等同于 int(a/b) `__divmod__`
- `-` 取复数 `__neg__`

### 比较运算符

- `==` 相等 `__cmp__` 
- `!=` 不等 
- `<>` 不等 
- `>` 大于 
- `<` 小于 `__lt__`
- `>=` 大于等于 
- `<=` 小于等于

### 赋值运算符

- `=` 赋值
- `+=` 和赋值
- `-=` 差赋值
- `*=` 积赋值
- `/=` 商赋值
- `%=` 余赋值
- `**=` 幂赋值
- `//=` 商取整赋值

### 位运算符

- `&` 与 `__and__`
- `|` 或 `__or__`
- `^` 异或 `__xor__`
- `~` 取反 `__invert__`
 - `<<` 左移 `lshift`
- `>>` 右移 `rshit`

### 逻辑运算符

- `and` 与
- `or` 或
- `not` 非

```
a = True
b = False 
c = a and b
c = a or b
c = not a 
```

### 序列运算符

- `in` 在    
- `not in` 不在

如`a in b`，其中比必须实现迭代器

### 身份运算符
`id(variable)`来获取变量的地址

- `is` 地址相等 等同于id(a) == id(b)
- `is not` 地址不等

### 运算符优先级
由高到低

- `**`
- `~`,`+`,`-` (此处代表正负符号，而非加减法)
- `*`,`/`,`%`,`//`
- `+`,`-`
- `>>`,`<<`
- `&`
- `^`,`|`
- `<=`,`<`,`>=`,`>`
- `<>`,`!=`,`==`
- `=`,`%=`,`+=`,`-=`,`*=`,`/=`,`//=`,`**=`
- `is`,`is not`
- `in`,`not in`
- `not`,`or`,`and`

### if-else
**`python`是缩进机器严格的语句**   
冒号下一行的语句，必须缩进到下一级  
如果缩进不对，将导致编译错误

```
name = 'luren'
if name == 'python':         # 判断变量否为'python'
    flag = True          # 条件成立时设置标志为真
    print 'welcome boss'    # 并输出欢迎信息
else:
    print name              # 条件不成立时输出变量名称
    
#如果块中代码只有一行，可以写到一行里面
var = 100
if ( var  == 100 ) : print "变量 var 的值为100"     
```

### if-elif-else
```
num = 5     
if num == 3:            # 判断num的值
    print 'boss'        
elif num == 2:
    print 'user'
elif num == 1:
    print 'worker'
elif num < 0:           # 值小于零时输出
    print 'error'
else:
    print 'roadman'     # 条件均不成立时输出
```

### while
`python`的循环中可以使用`continue`略过这次循环，也可以是使用`break`跳出整个循环

```
count = 0
while (count < 9):
   print 'The count is:', count
   count = count + 1

#如果块中代码只有一行，可以写到一行里面
flag = 1
while (flag): print 'Given flag is really true!'
```

### while-else
当`while`条件为假的时候，会执行else块  

```
count = 0
while count < 5:
   print count, " is  less than 5"
   count = count + 1
else:
   print count, " is not less than 5"
```

### for-in
```
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        
   print '当前水果 :', fruit
```

### range函数
`range`函数返回一个迭代器

`range(a)` 返回`0 ~ (a-1)`的迭代器  
`range(5)` `0,1,2,3,4`  

`range(a,b)` 返回`a ~ (b-1)`的迭代器  
`range(2,6)` `2,3,4,5`

`range(a,b,c)` 返回`a ~ (b-1)`的迭代器，步长为`c`
`range(0,10,2)` `0,2,4,6,8`
`range(10,0,-2)` `10,8,6,4,2`

### for-in range
```
for num in range(10,20):
	print num  
# 打印 10，11，12，13，14，15，16，17，18，19
```

### for-in-else
如果`for`循环没有被`break`，则会在循环结束的时候，执行`else`块
如果中途遇到`break`,则不会打印`else`块

```
for num in range(10,20):
	if num == 15:
		break
	print num 
else:
	print 'default end'
# 打印 10，11，12，13，14

for num in range(10,15):
	if num == 15:
		break
	print num 
else:
	print 'default end'
# 打印 10，11，12，13，14，end
```

### 类型转换函数
- `int(x)`  将x转换为一个整数  
- `long(x)` 将x转换为一个长整数  
- `float(x)`  将x转换到一个浮点数  
- `complex(x)`  创建一个复数  
- `str(x)` 将对象 `x` 转换为字符串  
- `repr(x)` 将对象 `x` 转换为表达式字符串  
- `eval(str)`  用来计算`Python`表达式,并返回一个对象  
- `tuple(s)` 将序列 `s` 转换为一个元组  
- `list(s)`  将序列 `s` 转换为一个列表  
- `chr(x)` 将一个整数转换为一个字符  
- `unichr(x)` 将一个整数转换为`Unicode`字符  
- `ord(x)` 将一个字符转换为它的整数值  
- `hex(x)` 将一个整数转换为一个十六进制字符串  
- `oct(x)` 将一个整数转换为一个八进制字符串  

### 数学函数
- `abs(x)` 绝对值，`__abs__` (重载该方法可作为参数)
- `pow(x, y)`	 等同于`x**y`
- `round(x)`	四舍五入

`math`模块中的方法 

- `ceil(x)` 向上取整
- `exp(x)` `e`的`x`次幂
- `fabs(x)` 浮点绝对值
- `floor(x)`	向下取整
- `max(x1, x2,...)`	返回给定参数的最大值，参数可以为序列。
- `min(x1, x2,...)`	返回给定参数的最小值，参数可以为序列。
- `modf(x)`	返回`x`的整数部分与小数部分
- `sqrt(x)` 开方
- `log(x)` 以`2`位底的对数
- `log10(x)` 以`10`位底的对数
- `acos(x)`  反余弦
- `asin(x)`  反正弦
- `atan(x)` 反正切
- `atan2(y,x)`  计算`x`,`y`点的反正切
- `cos(x)` 余弦
- `hypot(x, y)` 欧几里得范数
- `sin(x)` 正弦
- `tan(x)` 正切
- `degrees(x)` 弧度转度
- `radians(x)` 度转弧度

### 随机函数
`random`模块中的方法

- `choice(seq)` 从序列中随机取数
- `randrange(begin,end,step)` 从指定范围取随机值
- `random()` 从`>=0`到`<1`随机取个数
- `seed(x)` 改变随机种子，不过`python会`自动帮你改变
- `shuffle(seq)` 随机打乱序列
- `uniform(x,y)` 在`>=x`到`<=y`之间随机取一个数