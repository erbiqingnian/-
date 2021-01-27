# task1 

# 变量、运算符与数据类型

## 1.注释

单行注释 #

多行注释''' '''或者""" """  

例：

```python
'''
注释
注释
注释
'''
print("Hello china") 
# Hello china
```

## 2.运算符

#### **算术运算符**

| `+`  | 加             | `1 + 1`  |
| ---- | -------------- | -------- |
| `-`  | 减             | `2 - 1`  |
| `*`  | 乘             | `3 * 4`  |
| `/`  | 除             | `3 / 4`  |
| `//` | 整除（地板除） | `3 // 4` |
| `%`  | 取余           | `3 % 4`  |
| `**` | 幂             | `2 ** 3` |

例：

```python
print(1 + 1)  # 2
print(2 - 1)  # 1
print(3 * 4)  # 12
print(3 / 4)  # 0.75
print(3 // 4)  # 0
print(3 % 4)  # 3
print(2 ** 3)  # 8
```

#### **比较运算符**

| 操作符 | 名称     | 示例     |
| ------ | -------- | -------- |
| `>`    | 大于     | `2 > 1`  |
| `>=`   | 大于等于 | `2 >= 4` |
| `<`    | 小于     | `1 < 2`  |
| `<=`   | 小于等于 | `5 <= 2` |
| `==`   | 等于     | `3 == 4` |
| `!=`   | 不等于   | `3 != 5` |

例

```
print(2 > 1)  # True
print(2 >= 4)  # False
print(1 < 2)  # True
print(5 <= 2)  # False
print(3 == 4)  # False
print(3 != 5)  # True
```

#### **逻辑运算符**

| 操作符 | 名称 | 示例                  |
| ------ | ---- | --------------------- |
| `and`  | 与   | `(3 > 2) and (3 < 5)` |
| `or`   | 或   | `(1 > 3) or (9 < 2)`  |
| `not`  | 非   | `not (2 > 1)`         |

例

```
print((3 > 2) and (3 < 5))  # True
print((1 > 3) or (9 < 2))  # False
print(not (2 > 1))  # False
```

#### **位运算符**

| 操作符 | 名称     | 示例               |
| ------ | -------- | ------------------ |
| `~`    | 按位取反 | `~4`               |
| `&`    | 按位与   | `4 & 5`            |
| `|`    | 按位或   | `4 | 5`            |
| `^`    | 按位异或 | `4 ^ 5`            |
| `<<`   | 左移     | `4 << 2` （左移2位 |
| `>>`   | 右移     | `4 >> 2`（右移2位  |

例（二进制的运算参见“位运算”部分。）

```python
print(bin(4))  # 0b100
print(bin(5))  # 0b101
print(bin(~4), ~4)  # -0b101 -5
print(bin(4 & 5), 4 & 5)  # 0b100 4
print(bin(4 | 5), 4 | 5)  # 0b101 5
print(bin(4 ^ 5), 4 ^ 5)  # 0b1 1 
print(bin(4 << 2), 4 << 2)  # 0b10000 16
print(bin(4 >> 2), 4 >> 2)  # 0b1 1
```

####  **三元运算符**

例

```
x, y = 4, 5
if x < y:
    small = x
else:
    small = y

print(small)  # 4
```

可以使用一条语句来完成以上的条件判断和赋值操作。

例

```
x, y = 4, 5
small = x if x < y else y
print(small)  # 4
```

#### **其他运算符**

| 操作符   | 名称   | 示例                         |
| -------- | ------ | ---------------------------- |
| `in`     | 存在   | `'A' in ['A', 'B', 'C']`     |
| `not in` | 不存在 | `'h' not in ['A', 'B', 'C']` |
| `is`     | 是     | `"hello" is "hello"`         |
| `is not` | 不是   | `"hello" is not "hello"`     |

【例子】

```
letters = ['A', 'B', 'C']
if 'A' in letters:
    print('A' + ' exists')
if 'h' not in letters:
    print('h' + ' not exists')

# A exists
# h not exists
```

【例子】比较的两个变量均指向不可变类型。

```
a = "hello"
b = "hello"
print(a is b, a == b)  # True True
print(a is not b, a != b)  # False False
```

【例子】比较的两个变量均指向可变类型。

```
a = ["hello"]
b = ["hello"]
print(a is b, a == b)  # False True
print(a is not b, a != b)  # True False
```

##### **注意**：

- **is, is not 对比的是两个变量的内存地址**
- **==, != 对比的是两个变量的值**
- 比较的两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的。
- 对比的两个变量，指向的是地址可变的类型（list，dict等），则两者是有区别的。

#### **运算符的优先级**

- 一元运算符优于二元运算符。例如`3 ** -2`等价于`3 ** (-2)`。
- **先算术运算，后移位运算，最后位运算**。例如 `1 << 3 + 2 & 7`等价于 `(1 << (3 + 2)) & 7`。
- **逻辑运算最后结合**。例如`3 < 4 and 4 < 5`等价于`(3 < 4) and (4 < 5)`。

【例子】

```
print(-3 ** 2)  # -9
print(3 ** -2)  # 0.1111111111111111
print(1 << 3 + 2 & 7)  # 0
print(-3 * 2 + 5 / -2 - 4)  # -12.5
print(3 < 4 and 4 < 5)  # True
```

### 变量和赋值

- 在使用变量之前，需要对其先赋值。
- 变量名可以包括字母、数字、下划线、但变量名不能以数字开头。
- Python 变量名是**大小写敏感**的，foo != Foo。

【例子】

```
teacher = "徐杰"
print(teacher)  # 徐杰
```

【例子】

```
first = 2
second = 3
third = first + second
print(third)  # 5
```

【例子】

```
myTeacher = "徐杰"
yourTeacher = "鲁杰"
ourTeacher = myTeacher + ',' + yourTeacher
print(ourTeacher)  # 徐杰,鲁杰
```

### 数据类型与转换

| 类型  | 名称                    | 示例           |
| ----- | ----------------------- | -------------- |
| int   | 整型 `<class 'int'>`    | `-876, 10`     |
| float | 浮点型`<class 'float'>` | `3.149, 11.11` |
| bool  | 布尔型`<class 'bool'>`  | `True, False`  |

#### **整型**

【例子】通过 `print()` 可看出 `a` 的值，以及类 (class) 是`int`。

```
a = 1031
print(a, type(a))
# 1031 <class 'int'>
```

万物皆对象（object）。只要是对象，就有相应的属性 （attributes） 和方法（methods）。

【例子】

```
b = dir(int)
print(b)

# ['__abs__', '__add__', '__and__', '__bool__', '__ceil__', '__class__',
# '__delattr__', '__dir__', '__divmod__', '__doc__', '__eq__',
# '__float__', '__floor__', '__floordiv__', '__format__', '__ge__',
# '__getattribute__', '__getnewargs__', '__gt__', '__hash__',
# '__index__', '__init__', '__init_subclass__', '__int__', '__invert__',
# '__le__', '__lshift__', '__lt__', '__mod__', '__mul__', '__ne__',
# '__neg__', '__new__', '__or__', '__pos__', '__pow__', '__radd__',
# '__rand__', '__rdivmod__', '__reduce__', '__reduce_ex__', '__repr__',
# '__rfloordiv__', '__rlshift__', '__rmod__', '__rmul__', '__ror__',
# '__round__', '__rpow__', '__rrshift__', '__rshift__', '__rsub__',
# '__rtruediv__', '__rxor__', '__setattr__', '__sizeof__', '__str__',
# '__sub__', '__subclasshook__', '__truediv__', '__trunc__', '__xor__',
# 'bit_length', 'conjugate', 'denominator', 'from_bytes', 'imag',
# 'numerator', 'real', 'to_bytes']
```

*对它们有个大概印象就可以了，具体怎么用，需要哪些参数 （argument），还需要查文档。*`bit_length()`例子。

【例子】找到一个整数的二进制表示，再返回其长度。

```
a = 1031
print(bin(a))  # 0b10000000111
print(a.bit_length())  # 11
```

#### **浮点型**

【例子】

```
print(1, type(1))
# 1 <class 'int'>

print(1., type(1.))
# 1.0 <class 'float'>

a = 0.00000023
b = 2.3e-7
print(a)  # 2.3e-07
print(b)  # 2.3e-07
```

想保留浮点型的小数点后 `n` 位。可以用 `decimal` 包里的 `Decimal` 对象和 `getcontext()` 方法来实现。

```
import decimal
from decimal import Decimal
```

*Python 里面有很多用途广泛的包 (package)，用什么你就引进 (import) 什么。包也是对象，也可以用上面提到的`dir(decimal)` 来看其属性和方法。*

【例子】`getcontext()` 显示了 `Decimal` 对象的默认精度值是 28 位 (`prec=28`)。

```
a = decimal.getcontext()
print(a)

# Context(prec=28, rounding=ROUND_HALF_EVEN, Emin=-999999, Emax=999999,
# capitals=1, clamp=0, flags=[], 
# traps=[InvalidOperation, DivisionByZero, Overflow])
b = Decimal(1) / Decimal(3)
print(b)

# 0.3333333333333333333333333333
```

【例子】使 1/3 保留 4 位，用 `getcontext().prec` 来调整精度。

```
decimal.getcontext().prec = 4
c = Decimal(1) / Decimal(3)
print(c)

# 0.3333
```

#### **布尔型**

布尔 (boolean) 型变量只能取两个值，`True` 和 `False`。当把布尔型变量用在数字运算中，用 `1` 和 `0` 代表 `True` 和 `False`。

【例子】

```
print(True + True)  # 2
print(True + False)  # 1
print(True * False)  # 0
```

除了直接给变量赋值 `True` 和 `False`，还可以用 `bool(X)` 来创建变量，其中 `X` 可以是

- **基本类型：整型、浮点型、布尔型**
- **容器类型：字符串、元组、列表、字典和集合**

【例子】**`bool` 作用在基本类型变量：`X` 只要不是整型 `0`、浮点型 `0.0`，`bool(X)` 就是 `True`，其余就是 `False`。**

```
print(type(0), bool(0), bool(1))
# <class 'int'> False True

print(type(10.31), bool(0.00), bool(10.31))
# <class 'float'> False True

print(type(True), bool(False), bool(True))
# <class 'bool'> False True
```

【例子】**`bool` 作用在容器类型变量：`X` 只要不是空的变量，`bool(X)` 就是 `True`，其余就是 `False`。**

```
print(type(''), bool(''), bool('python'))
# <class 'str'> False True

print(type(()), bool(()), bool((10,)))
# <class 'tuple'> False True

print(type([]), bool([]), bool([1, 2]))
# <class 'list'> False True

print(type({}), bool({}), bool({'a': 1, 'b': 2}))
# <class 'dict'> False True

print(type(set()), bool(set()), bool({1, 2}))
# <class 'set'> False True
```

确定`bool(X)` 的值是 `True` 还是 `False`，就看 `X` 是不是空，空的话就是 `False`，不空的话就是 `True`。

- **对于数值变量，`0`, `0.0` 都可认为是空的。**
- **对于容器变量，里面没元素就是空的。**

#### **获取类型信息**

- `type(object)` 获取类型信息

【例子】

```
print(type(1))  # <class 'int'>
print(type(5.2))  # <class 'float'>
print(type(True))  # <class 'bool'>
print(type('5.2'))  # <class 'str'>
```

- `isinstance(object, classinfo)` 判断一个对象是否是一个已知的类型。

【例子】

```
print(isinstance(1, int))  # True
print(isinstance(5.2, float))  # True
print(isinstance(True, bool))  # True
print(isinstance('5.2', str))  # True
```

注：

- `type()` 不会认为子类是一种父类类型，**不考虑继承关系**。
- `isinstance()` 会认为子类是一种父类类型，**考虑继承关系**。

如果**要判断两个类型是否相同推荐使用 `isinstance()`**

#### **类型转换**

- 转换为整型 `int(x, base=10)`
- 转换为字符串 `str(object='')`
- 转换为浮点型 `float(x)`

【例子】

```
print(int('520'))  # 520
print(int(520.52))  # 520
print(float('520.52'))  # 520.52
print(float(520))  # 520.0
print(str(10 + 10))  # 20
print(str(10.1 + 5.2))  # 15.3
```

####  print() 函数

```
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

- 将对象以字符串表示的方式格式化输出到流文件对象file里。其中所有非关键字参数都按`str()`方式进行转换为字符串输出；
- 关键字参数`sep`是**实现分隔符**，**比如多个参数输出时想要输出中间的分隔字符**；
- 关键字参数`end`是**输出结束时的字符**，**默认是换行符`\n`**；
- 关键字参数`file`是**定义流输出的文件，可以是标准的系统输出`sys.stdout`，也可以重定义为别的文件**；
- 关键字参数`flush`是**立即把内容输出到流文件，不作缓存**。

【例子】**没有参数时，每次输出后都会换行**。

```
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed without 'end'and 'sep'.")
for item in shoplist:
    print(item)

# This is printed without 'end'and 'sep'.
# apple
# mango
# carrot
# banana
```

【例子】**每次输出结束都用`end`设置的参数`&`结尾，并没有默认换行。**

```
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'end='&''.")
for item in shoplist:
    print(item, end='&')
print('hello world')

# This is printed with 'end='&''.
# apple&mango&carrot&banana&hello world
```

【例子】`item`值与`'another string'`两个值之间用`sep`设置的参数`&`分割。由于`end`参数没有设置，因此默认是输出解释后换行，即`end`参数的默认值为`\n`。

```
shoplist = ['apple', 'mango', 'carrot', 'banana']
print("This is printed with 'sep='&''.")
for item in shoplist:
    print(item, 'another string', sep='&')

# This is printed with 'sep='&''.
# apple&another string
# mango&another string
# carrot&another string
# banana&another string
```

**思考题**：

**Python是怎么诞生的？Python之父是谁？**

1989年圣诞节期间，在阿姆斯特丹，Guido为了打发圣诞节的无趣，决心开发一个新的脚本解释程序，做为ABC 语言的一种继承。之所以选中Python作为该编程语言的名字，是因为他是一个叫Monty Python的喜剧团体的爱好者。Python的创始人为Guido van Rossum。

**Python和C++（或者C）的区别在哪？即为什么要学习Python，C++不香吗？**

*语言类型*
Python是一种基于解释器的语言，解释器会逐行读取代码；首先将Python编译为字节码，然后由shu大型C程序解释。
C是一种编译语言，完整的源代码将直接编译为机器代码，由CPU直接执行。
*内存管理*
Python使用自动垃圾收集器进行内存管理。
在C语言中，程序员必须自己进行内存管理。
*应用*
Python是一种通用编程语言，一个多范式。它主要支持面向对象编程，程序编程，函数编程。
C是结构化编程语言。允许使用函数，选择（if/else等），迭代（循环）。它主要用于硬件相关的应用程序。
*速度*
Python编程语言因为历史原因，有一个GIL锁，导致其对多线程支持不够好，运行速度较慢；而C语言很快，C语言是比较底层的语言，运行效率上要优于Python。

**相较于Python2，Python3做了哪些大的改进？**

python3 引入了 asyncio 来进行异步IO编成

2、print 在python2 是关键字，python3 是函数

3、编码问题，python3 不再有unicode对象， str 即为unicode

4、除法的变化。python 3 除法返回浮点数 5/2 = 2.5

5、类型注解（type hint）

6、优化的super() ,直接调用父类的方法

7、高级的解包操作， 如 a, b, *c= range(10)

8、限定关键字参数， 参数特别多的时候指定参数以防搞混

9、python3 重新跑出异常不会丢失栈信息

10、一切返回迭代器

11、新增yield from 链接生成器

12、新增内置库enum,mock, asyncio, ipaddress, concurrent, futures等

13、生成的pyc文件统一放到**pycache**

14、一些内置库修改。urllib，selector等

15、性能优化

二、兼容2/3的工具

1、six模块

2、2to3等工具转换代码

**练习题**：

**怎样对python中的代码进行注释？**

使用 #（单行） 和 ''' ''' 或者 """ """（多行）。

**python有哪些运算符，这些运算符的优先级是怎样的？**

算术运算符、比较运算符、逻辑运算符、位运算符、三元运算符、其他运算符。

一元优于二元，先算术后移位，最后位运算，逻辑运算最后结合。

**python 中 `is`, `is not` 与 `==`, `!=` 的区别是什么？**

前者 对比的是两个变量的内存地址。后者 对比的是两个变量的值。

两个变量，指向的都是地址不可变的类型（str等），那么is，is not 和 ==，！= 是完全等价的；指向的是地址可变的类型（list，dict等），则两者是有区别的。

**python 中包含哪些数据类型？这些数据类型之间如何转换？**

有整型、浮点型、布尔型。

转换为整型 `int(x, base=10)`

```
print(int('520'))  # 520
print(int(520.52))  # 520
```

转换为字符串 `str(object='')`

```
print(str(10 + 10))  # 20
print(str(10.1 + 5.2))  # 15.3
```

转换为浮点型 `float(x)`

```
print(float('520.52'))  # 520.52
print(float(520))  # 520.0
```

# 位运算

### 1. 原码、反码和补码

二进制有三种不同的表示形式：**原码、反码和补码**，<u>计算机内部</u>使用**补码**来表示。

**原码**：<u>就是其二进制表示</u>（**最高位是符号位**）。

```
00 00 00 11 -> 3
10 00 00 11 -> -3
```

**反码**：**正数的反码就是原码**，<u>**负数的反码是符号位不变，其余位取反（对应正数按位取反）**</u>

```
00 00 00 11 -> 3
11 11 11 00 -> -3
```

**补码**：**正数的补码就是原码，负数的补码是<u>反码+1</u>。**

```
00 00 00 11 -> 3
11 11 11 01 -> -3
```

**符号位**：**最高位为符号位，0表示正数，1表示负数**。在**<u>位运算</u>**中符号位也参与运算。

### 按位非操作 ~

```
~ 1 = 0
~ 0 = 1
```

`~` 把`num`的**补码中的 0 和 1 全部取反**（0 变为 1，1 变为 0）有<u>符号整数的符号位</u>在 `~` 运算中**同样会取反。**

```
00 00 01 01 -> 5
~
---
11 11 10 10 -> -6

11 11 10 11 -> -5
~
---
00 00 01 00 -> 4
```

### 按位与操作 &

```
1 & 1 = 1
1 & 0 = 0
0 & 1 = 0
0 & 0 = 0
```

只有两个对应位都为 1 时才为 1

```
00 00 01 01 -> 5
&
00 00 01 10 -> 6
---
00 00 01 00 -> 4
```

###  按位或操作 |

```
1 | 1 = 1
1 | 0 = 1
0 | 1 = 1
0 | 0 = 0
```

只要两个对应位中有一个 1 时就为 1

```
00 00 01 01 -> 5
|
00 00 01 10 -> 6
---
00 00 01 11 -> 7
```

### 按位异或操作 ^

```
1 ^ 1 = 0
1 ^ 0 = 1
0 ^ 1 = 1
0 ^ 0 = 0
```

只有两个对应位不同时才为 1

```
00 00 01 01 -> 5
^
00 00 01 10 -> 6
---
00 00 00 11 -> 3
```

异或操作的性质：**满足<u>交换律和结合律</u>**

```
A: 00 00 11 00
B: 00 00 01 11

A^B: 00 00 10 11
B^A: 00 00 10 11

A^A: 00 00 00 00
A^0: 00 00 11 00

A^B^A: = A^A^B = B = 00 00 01 11
```

### 按位左移操作 <<

`num << i` 将`num`的二进制表示向左移动`i`位所得的值。

```
00 00 10 11 -> 11
11 << 3
---
01 01 10 00 -> 88 
```

### 按位右移操作 >>

`num >> i` 将`num`的二进制表示向右移动`i`位所得的值。

```
00 00 10 11 -> 11
11 >> 2
---
00 00 00 10 -> 2 
```

### 利用位运算实现快速计算

通过 `<<`，`>>` 快速计算2的倍数问题。

```python
n << 1 -> 计算 n*2
n >> 1 -> 计算 n/2，负奇数的运算不可用
n << m -> 计算 n*(2^m)，即乘以 2 的 m 次方
n >> m -> 计算 n/(2^m)，即除以 2 的 m 次方
1 << n -> 2^n
```

通过 `^` 快速交换两个整数。

```
a ^= b
b ^= a
a ^= b
```

通过 `a & (-a)` 快速获取`a`的最后为 1 位置的整数。

```
00 00 01 01 -> 5
&
11 11 10 11 -> -5
---
00 00 00 01 -> 1

00 00 11 10 -> 14
&
11 11 00 10 -> -14
---
00 00 00 10 -> 2
```

### 利用位运算实现整数集合

一个数的二进制表示可以看作是一个集合（**0 表示不在集合中，1 表示在集合中**）。

比如集合 `{1, 3, 4, 8}`，可以表示成 `01 00 01 10 10` 而对应的位运算也就可以看作是对集合进行的操作。

元素与集合的操作：

```
a | (1<<i)  -> 把 i 插入到集合中
a & ~(1<<i) -> 把 i 从集合中删除
a & (1<<i)  -> 判断 i 是否属于该集合（零不属于，非零属于）
```

集合之间的操作：

```
a 补   -> ~a
a 交 b -> a & b
a 并 b -> a | b
a 差 b -> a & (~b)
```

注意：*整数在内存中是以补码的形式存在的，输出自然也是按照补码输出。*

【例子】 Python 的`bin()` 输出。

```
print(bin(3))  # 0b11
print(bin(-3))  # -0b11

print(bin(-3 & 0xffffffff))  
# 0b11111111111111111111111111111101

print(bin(0xfffffffd))       
# 0b11111111111111111111111111111101

print(0xfffffffd)  # 4294967293
```

- Python中`bin`一个负数（十进制表示），输出的是**它的原码的二进制表示加上个负号**。
- Python中的整型是补码形式存储的。
- Python中整型是不限制长度的不会超范围溢出。

所以为了获得负数（十进制表示）的补码，需要手动将其和十六进制数`0xffffffff`进行按位与操作，再交给`bin()`进行输出，得到的才是负数的补码表示。

**练习题**：

leetcode 习题 136. 只出现一次的数字

给定一个**非空**整数数组，除了某个元素只出现一次以外，其余每个元素均出现两次。找出那个只出现了一次的元素。

尝试使用位运算解决此题。

题目说明:

```python
"""
Input file
example1: [2,2,1]
example2: [4,1,2,1,2]

Output file
result1: 1
result2: 4
"""



class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        
        res=0
        for x in nums:
            res ^=x
        return res
```

