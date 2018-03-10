## 元组
---
Python的元组和列表类似，不同之处在于元组的元素不能修改。元组使用小括号表示，元素之间使用`,`隔开。<br/>

### 元组的定义
元组使用`tup = ()`或者`tuple()`的方式定义。<br/>
实例如下:<br/>

```
>>> tup1 = (1,2,3,4,5)
>>> tup1
(1, 2, 3, 4, 5)
>>> tup2 = tuple((1,2,3))
>>> tup2
(1, 2, 3)
>>> tup3 = 1,2,3,4
>>> tup3
(1, 2, 3, 4)
>>> tup4=(1,2,2,4,4)
>>> tup4
(1, 2, 2, 4, 4)
```

### 元组元素的访问
元组跟列表一样，可以使用索引来访问元组中的值，例如：<br/>
```
>>> tuple1 = (1,2,3,4)
>>> tuple1[0]
1
>>> tuple1[3]
4
```

### 修改元组中的值
元组中的元素值是不允许修改的，但是可以对两个元组进行拼接，对元组进行拆包。例如：<br/>
```
>>> tuple1 = (1,2,3,4)
>>> tuple1[0] = 5
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'tuple' object does not support item assignment
>>> tuple2 = ('a','b','c')
>>> tuple3 = tuple1 + tuple2
>>> tuple3
(1, 2, 3, 4, 'a', 'b', 'c')
>>> tup = ('youngeyes','18')
>>> name ,age = tup
>>> name
'youngeyes'
```

### 删除元组
上面说元组中的元素是不能修改的，那么像列表那样的方式删除元素也是不允许的，但是可以使用`del`语句删除整个元组。例如：<br/>
```
>>> tup = ('youngeyes','18','sport')
>>> del tup
>>> tup
```

### 元组切片
因为元组也是一个序列，有索引，可以像列表那样切片操作。例如：<br/>
```
>>> L = ('radm','tom','real','haha')
>>> L[1:3]
('tom', 'real')
>>> L[-2:-1]
('real',)
```

可以看到，当元组中只有一个元素时，还是要在元素后面跟`,`，所以定义一个元素的元组时`tup = (1,)`而不是`tup = (1)`。<br/>

### 元组的内置函数
Python元组包含了一些内置函数，如下：<br/>

|序号|方法及描述|
|:--:|:-------|
|1|cmp(tuple1,tuple2)比较两个元组的元素|
|2|len(tuple)计算元组元素个数|
|3|max(tuple)返回元组中元素最大值|
|4|min(tuple)返回元组中元素最小值|
|5|tuple(seq)将列表转换为元组|

实例如下：<br/>
```
>>> tup1 = (1,2,4,7,9)
>>> tup2 = ('a','b','c','d')
>>> cmp(tup1,tup2)
-1
>>> len(tup1)
5
>>> max(tup1)
9
>>> min(tup2)
'a'
```

