# Python-notes
为了学Django，迫不得已。从最基础的记起，尽量详细。





## 注意点

1. 标点符号全英文
2. 正确使用缩进
3. 检查函数是否拼写正确





## 变量(Variable)

所谓变量，就是一个名字，可以被赋值，区分大小写

```python
x=3
```

##### 1.多个变量赋值

```python
one=two=three=10
```

##### 2.变量值类型，有五大类

字符串(String)、数字(Numeric)、列表(List)、元组(Tuple)、字典(Dictionary)

#### 字符串（String）

字符串有三种，Single quotes、Double quotes、Triple quotes

```python
#Single quotes
>>>print('123456')
123456

#Double quotes
>>>print("let's go!")
let's go!
--为了避免里面的单引号和Single quotes的单引号重复，用了双引号

#Triple quotes：长字符串，也叫三引号字符串，用来解决多个换行问题。
--通常是连续的三个单引号或者三个双引号，要成双成对。
>>>print('''wo
ai
xue
xi''')
wo
ai
xue
xi
```

##### 字符串的加法和乘法

```python
#字符串加法
--先弄懂520和'520'的区别
>>>520+1314
1834
#-------------------------------------------------
>>>'520'+'1314'
'5201314'
--所以说字符串的相加就是拼接

#字符串乘法
>>>print('这段话将被复制三遍\n'*3)
这段话将被复制三遍
这段话将被复制三遍
这段话将被复制三遍
--所以说字符串的乘法就是复制
```



##### 转义字符

反斜杠搭配特定的字符变为转义字符

```python
#没有使用转义字符时(反斜杠+“t”是Tab制表键)
>>>print('\three\two\one')
	hree	wo\one
    
#使用转义字符
>>>print('\\three\\two\\one')
\three\two\one
#为了提高编程效率，使用原始字符串，用‘r’说明是原始字符串（转义字符不再有效）。
>>>print(r'\three\two\one')
\three\two\one
```



#### 数字(Numeric)

##### 数字类型

数字有三种类型：整数（Integer）、浮点数(Float)、复数(Complex)。

```python
#整数
--python中整数包括正负整数和0，长度不受限制

#浮点数
--浮点数是带小数点的数字，python中浮点数存储位数有限，超过指定长度会采用近似处理
>>>10.0/3
3.3333333333333335
--注意，由于采用了近似处理，所以会产生精度上的误差，比如：
>>>0.3==0.1+0.2
False
--原因是
>>>0.1+0.2
0.30000000000000004

#复数
--复数包含一个实部和一个虚部
>>>x=1+2j
>>>x
(1+2j)
>>>x.real        #显示实部
1.0
>>>x.imag        #显示虚部
2.0
```

##### 数字运算

重点区分除法

```python
#x/y   (x/y的结果)
>>>1/3
0.3333333333333333   

#x//y  (地板除，结果向下取整)
>>>7//3
2
>>>-7//3
-3

#x%y   (x除y的余数)
>>>7%3
1
```

#### 布尔（Boolean）

布尔又称逻辑，再Python中用True、False表示。

```python
>>>1==True
True
>>>0=False
True
```

##### 逻辑运算（布尔运算）

共三个：and、or、not

过于简单，不深究







## 条件分支与循环

#### if条件分支

冒号一定注意不能丢失

格式一：单分支判断

```python
if boolean_value1:
    子代码模块1
    
>>> if 2<5:
	    print('OK')
OK        
```

格式二：双分支判断

```python
if boolean_value1:
    子代码模块1
else:
    子代码模块2
```

格式三：多条件多分支判断

```python
if boolean_value1:
    子代码模块1
elif boolean_value2:
    子代码模块2
else:
    子代码模块3
```

#### while循环

```python
while boolean_value1:
    子代码模块1
#ctrl+c键可以终止无限循环
```

#### for循环语句

```python
for <variable> in <sequence>:
    子代码模块1
else：
    子代码模块2

```

