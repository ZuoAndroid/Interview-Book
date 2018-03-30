---
layout: post
title: Python推导式(列表、字典、集合推导式)
categories: Python语法
description: Python推导式(列表、字典、集合推导式)
keywords: 推导式, Python
---
#### Python推导式(列表、字典、集合推导式)
推导式comprehensions（又称解析式），是Python的一种独有特性。推导式是可以从一个数据序列构建另一个新的数据序列的结构体。 共有三种推导，在Python2和3中都有支持：
- 列表(List)推导式
- 字典(Dict)推导式
- 集合(Set)推导式

#### 1.列表推导式
##### 1.1 使用``[]``生成List
基本格式：
```
[out_exp_res for out_exp in input_list if out_exp == 2]
```
- out_exp_res:　　列表生成元素表达式，可以是有返回值的函数。
- for out_exp in input_list：　　迭代input_list将out_exp传入out_exp_res表达式中。
- if out_exp == 2：　　根据条件过滤哪些值可以。

案例1:
```python
In [1]: [x for x in range(10)]
Out[1]: [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

In [2]: [x for x in range(10) if x % 2 ==0]
Out[2]: [0, 2, 4, 6, 8]
```
案例2：
```python
In [3]: def f(x):
   ...:     return x * x
   ...:

In [4]: [f(x) for x in range(10)]
Out[4]: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```
##### 1.2 使用()生成generator
将俩表推导式的[]改成()即可得到生成器。
```python
In [5]: list = (x for x in range(10) if x % 2 ==0)

In [6]: list
Out[6]: <generator object <genexpr> at 0x0000018C86C88FC0>

In [7]: for i in list:
   ...:     print(i)
   ...:
0
2
4
6
8
```

#### 2. 字典推导式
字典推导和列表推导的使用方法是类似的，只不中括号该改成大括号。直接举例说明：
快速更换key和value：
```python
In [10]: dic = {'a':10, 'b':20}

In [11]: n_dic = {v:k for k,v in dic.items()}

In [12]: n_dic
Out[12]: {10: 'a', 20: 'b'}
```

#### 3. 集合推导式
它们跟列表推导式也是类似的。 唯一的区别在于它使用大括号{}。
例子：
```python
In [13]: set1 = {x for x in range(10)}

In [14]: set1
Out[14]: {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}
```
