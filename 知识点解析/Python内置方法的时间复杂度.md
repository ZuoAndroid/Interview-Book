---
layout: post
title: Python内置方法的时间复杂度
categories: 算法相关
description: Python内置方法的时间复杂度
keywords: 算法, 时间复杂度
---
### Python内置方法的时间复杂度
本文转载自:http://www.orangecube.net/python-time-complexity
本页面涵盖了Python中若干方法的时间复杂度（或者叫“大欧”，“Big O”）。该时间复杂度的计算基于当前（译注：至少是2011年之前）的CPython实现。其他Python的实现（包括老版本或者尚在开发的CPython实现）可能会在性能表现上有些许小小的差异，但一般不超过一个``O(log n)``项。

本文中，``n``代表容器中元素的数量，``k``代表参数的值，或者参数的数量。

#### 列表(List)
以完全随机的列表考虑平均情况。

列表是以数组（Array）实现的。最大的开销发生在超过当前分配大小的增长，这种情况下所有元素都需要移动；或者是在起始位置附近插入或者删除元素，这种情况下所有在该位置后面的元素都需要移动。如果你需要在一个队列的两端进行增删的操作，应当使用collections.deque（双向队列）

|操作	|平均情况	|最坏情况|
| - | :-: | -: | 
|复制	|O(n)	|O(n)|
|append[注1]	|O(1)	|O(1)|
|插入	|O(n)	|O(n)|
|取元素	|O(1)	|O(1)|
|更改元素	|O(1)	|O(1)|
|删除元素	|O(n)	|O(n)|
|遍历	|O(n)	|O(n)|
|取切片	|O(k)	|O(k)|
|删除切片	|O(n)	|O(n)|
|更改切片	|O(k+n)	|O(k+n)|
|extend[注1]	|O(k)	|O(k)|
|排序	|O(n log n)	|O(n log n)|
|列表乘法	|O(nk)	|O(nk)|
|x in s	|O(n)||	 
|min(s), |max(s)	|O(n)	 
|计算长度	|O(1)	|O(1)