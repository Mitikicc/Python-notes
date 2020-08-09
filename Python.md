# Python-notes
为了学Django，迫不得已。从最基础的记起，尽量详细。

参考廖雪峰官网python教程以及某python书。



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

##### 要计算`str`包含多少个字符，可以用`len()`函数：

```python
>>> len('ABC')
3
>>> len('中文')
2
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

>>> for i in range(9):
	if i!=0:
		if i%2==0:
			print('%d是偶数'%(i))

			
2是偶数
4是偶数
6是偶数
8是偶数
```

#### 循环控制语句

当初学c语言的时候没搞懂的东西

##### break语句

```python
#只要记住一句话：执行到break语句，跳出当前for循环，循环结束。
```

##### continue语句

```python
#满足条件，continue使循环到开始处，继续循环，忽略continue后的代码执行
>>> for i in range(1,9):
	if i%2!=0:
		continue
	print('%d是偶数'%(i))

	
2是偶数
4是偶数
6是偶数
8是偶数
```

### 练习

```python
#for循环实现求10的因数，把求得的因数放在一个字符串上，并打印10的所有因数和因数累加和。
>>> c=b=0
>>> a=''
>>> for i in range(1,11):
	if 10%i==0:
		a=a+str(i)+','
		b=b+i
		c=c+i

		
>>> print('10的所有因素为 %s，因素累加和为%d'%(a,c))
10的所有因素为 1,2,5,10,，因素累加和为18
#while循环实现
>>> i=1
>>> result=''
>>> total=0
>>> while i<=10:
>>>    if 10%i==0:
>>>        result=result+str(i)+','
>>>        total+=i
>>>   i+=1
>>>
>>>   
>>> print('10的所有因素为 %s，因素累加和为%d'%(result,total))

10的所有因素为 1,2,5,10,，因素累加和为18
#---------------------------------------------------------------------------------------
#文本字符统计：结合ASCLL表，统计text文本中英文字母、汉字、数字、符号的数量：
-- text='中国+china2017是-*/OK很难a也不难'
>>>i=zimu=hanzi=shuzi=fuhao=0
>>>text='中国+china2017是-*/OK很难a也不难'
>>>tol=len(text)
>>>while i<tol:
>>>    if 'a'<text[i]<'z' or 'A'<text[i]<'Z':
>>>        zimu+=1
>>>    elif '0'<=text[i]<='9':
>>>        shuzi+=1
>>>    elif ord(text[i])>127:
>>>        hanzi+=1
>>>    else:
>>>        fuhao+=1
>>>    i+=1
>>>print('字母、汉字、数字、符号的数量分别是%d,%d,%d,%d'%(zimu,hanzi,fuhao,shuzi))

字母、汉字、数字、符号的数量分别是6,8,6,4
```



## 列表与元组

### 列表(List)

#### 基本知识

Python内置的一种数据类型是列表：list。list是一种有序的集合，可以随时添加和删除其中的元素。

用中括号表示列表的开始和结束，元素之间逗号隔开。

```python
>>> list1=[]
>>> list1
[]
>>> len(list1)
0

>>> classmates = ['Michael', 'Bob', 'Tracy']
>>> classmates
['Michael', 'Bob', 'Tracy']
>>> len(classmates)
3
```

列表的下标和字符串相同，从0开始，len(list)-1结束

```python
>>> classmates[0]
'Michael'
>>> classmates[1]
'Bob'
>>> classmates[2]
'Tracy'
```

获取倒数第几个元素时，用负数

```python
>>> classmates[-1]
'Tracy'
>>> classmates[-2]
'Bob'
>>> classmates[-3]
'Michael'
>>> classmates[-0]
'Michael'
#注意classmates[-0]就是第一个元素
```

#### 基本操作

applend() 列表尾部追加元素

```python
>>> classmates.append('Adam')
>>> classmates
['Michael', 'Bob', 'Tracy', 'Adam']
```

insert() 列表任意位置插入元素，注意插入的位置，数字是几就在几号元素前插入

```PYTHON
>>> classmates.insert(1,'Jack')
>>> classmates
['Michael', 'Jack', 'Bob', 'Tracy', 'Adam']
```

pop(i) 删除列表指定位置元素

```python
>>> classmates.pop()
'Adam'
>>> classmates.pop(1)
'Jack'
>>> classmates
['Michael', 'Bob', 'Tracy']
```

列表元素的替换：直接赋值

```python
>>> classmates[1] = 'Sarah'
>>> classmates
['Michael', 'Sarah', 'Tracy']
```

List里面的元素可以是各种数据类型，也可以是另外一个List

```python
>>> s = ['python', 'java', ['asp', 'php'], 'scheme']
>>> len(s)
4
>>> s[2][1]
'php'
```

### 元组(Tuple)

元组与列表的不同之处在于

（1）元组不可被修改，而列表允许

（2）元组用小括号（）表示

```python
>>> classmates = ('Michael', 'Bob', 'Tracy')
```

一旦被定义后就不可被修改，没有append()，insert()这样的方法。

不可改的一个好处就是安全。

#### 基本知识

注意元组的定义

```python
>>> tuple1=()
>>> tuple1
()

>>> tuple2=(1,)
>>> tuple2
(1,)

>>> tuple3=(1)
>>> tuple3
1
--出来是一个数，表名tuple3不是元组，所以定义一个元素的元组时必须加上逗号
```

## 字典(Dict)

和字典是无序集合，以键值对为基本元素可以存放各种数据类型

所谓键值对就是由键（Key）和值（Value）组成，中间冒号隔开

用大括号{}表示开始和结束，中间用逗号，隔开

字典体现了紧密的一对一关系，用来当作查询功能

```python
>>> d = {'Michael': 95, 'Bob': 75, 'Tracy': 85}
>>> d['Bob']    #注意这里是中括号
75
```

把数据放入dict的方法，除了初始化时指定外，还可以通过key放入：

```python
>>> d['xcx']=18
>>> d['xcx']
18
```

