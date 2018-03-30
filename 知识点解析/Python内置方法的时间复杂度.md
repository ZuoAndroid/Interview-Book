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