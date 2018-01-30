## 列表
---
列表（list）是python中内置数据结构，列表是一个数据集合，它可以通过索引的方式来获取对应的值。<br/>
### 定义列表
可以通过`list1 = []`的方式定义一个空列表，也可以通过`list1 = list()`定义一个空列表，定义的同时可以给列表添加元素。例如：<br/>
```
list1 = []
list2 = list()
list3 = [1,2,3,4]
list4 = list((1,2,3,4))
print(list1)
print(list2)
print(list3)
print(list4)
print(type(list1))
```
输出：<br/>
```
[]
[]
[1, 2, 3, 4]
[1, 2, 3, 4]
<class 'list'>
```
跟其他编程语言不同，python列表中的元素可以是任意数据类型，例如：<br/>
```
list1 = [1,2,'hello',1.14,['a','b','c']]
print(list1)
```
输出：<br/>
```
[1, 2, 'hello', 1.14, ['a', 'b', 'c']]
```
### 列表取元素
- 通过索引取值，索引从零开始

```
>>> list1 = [1,2,3,'hello']
>>> list1[0]
1
>>> list1[1]
2
```
不光可以从头开始取值，还可以从尾开始取值，从尾开始的索引为-1，例如：<br/>
```
>>> list1 = [1,2,3,'hello']
>>> list1[-1]
'hello'
>>> list1[-2]
3
```
当索引值超出范围时，python解释器会报错，例如：<br/>
```
>>> list1 = [1,2,3,'hello']
>>> list1[4]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
### 取长度
用`len()`方法查看列表的长度：<br/>
```
>>> list1 = [1,2,3,'hello']
>>> len(list1)
4
```
### 列表加法和乘法
列表相加就是把两个列表连接起来，列表乘以一个整数相当于将列表重复相加：<br/>
```
>>> list1 = [1,2,3,'hello']
>>> list2 = ['a','b']
>>> list1 + list2
[1, 2, 3, 'hello', 'a', 'b']
>>> list2 * 2
['a', 'b', 'a', 'b']
```
### 切片
切片就是把列表切分开来，我只需要其中的某一部分，返回切片后的列表，切片的语法就是`[start:end:step]`，默认step是1可以不写。例如：<br/>
```
>>> l = [1,2,3,4,5,6,7,8,9]
>>> l[1:3]
[2, 3]
>>> l[2:4]
[3, 4]
>>> l[-2:]
[8, 9]
>>> l[:4]
[1, 2, 3, 4]
>>> l[1:4:2]
[2, 4]
```
可以看出：<br/>
- start从0开始可以省略
- end从-1开始可以省略
- 切片取头不取尾
- 切片可以倒着切，但是end始终比start数值大

### 赋值
列表中的元素可以进行赋值修改：<br/>
```
>>> l1 = [1,2,3,4]
>>> l1
[1, 2, 3, 4]
>>> l1[1] = 9
>>> l1
[1, 9, 3, 4]
```
### 取元素索引值
用`index()`方法取元素索引值：<br/>
```
>>> l1
[1, 9, 3, 4]
>>> l1.index(9)
1
>>> l1.index(2) # 不存在的元素会报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 2 is not in list
```
index还可以指定查找的起始位置，例如：<br/>
```
>>> l1
[1, 2, 3, 4, 5, 6, 7, 'a', 'b']
>>> l1.index(3,1,4)
2
>>> l1.index(3,3,6)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: 3 is not in list
```
### 往列表中增加元素
- append()追加，即在列表末尾追加元素

```
>>> l1
[1, 9, 3, 4]
>>> l1.append(7)
>>> l1
[1, 9, 3, 4, 7]
```

- insert()插入，可以在列表任意位置插入元素，接收两个参数，第一个是要插入的位置，第二个是要插入的值

```
[1, 9, 3, 4, 7]
>>> l1.insert(1,3)
>>> l1
[1, 3, 9, 3, 4, 7]
```
- extend()扩展，传入一个可迭代对象，加到原列表中

```
>>> l1 = [1,2,3,4]
>>> l1.extend([5,6,7])
>>> l1
[1, 2, 3, 4, 5, 6, 7]
>>> l1.extend(('a','b'))
>>> l1
[1, 2, 3, 4, 5, 6, 7, 'a', 'b']
```
### 删除列表中的元素
- pop()弹出，从列表的尾部开始删除元素，返回弹出的元素值

```
>>> l = [1,2,3]
>>> l.pop()
3
>>> l.pop()
2
>>> l.pop()
1
>>> l.pop()     # 列表为空时报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop from empty list
```

- remove()，删除列表中的某个值，若没有此值，则报错

```
>>> l = [1,2,3]
>>> l.remove(2)
>>> l
[1, 3]
>>> l.remove(4)     # 没有此元素时报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError: list.remove(x): x not in list
```

- clear()清空，把列表中的所有元素删掉

```
>>> l = [1,2,3]
>>> l.clear()
>>> l
[]
```

- del系统方法删除，可以删除某个元素，也可以删除整个对象

```
>>> l = [1,2,3]
>>> del l[1]
>>> l
[1, 3]
>>> del l   # 删除整个l对象
>>> l
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'l' is not defined
```

### 拷贝
copy()方法用来拷贝一个列表，返回一个列表，例如：<br/>
```
>>> l = [1,2,3]
>>> l.copy()
[1, 2, 3]
```
### 排序
sort()方法可以对列表进行排序<br/>
```
>>> l1 = [1,3,9,4,6,0]
>>> l1.sort()
>>> l1
[0, 1, 3, 4, 6, 9]
```
### 反向
reverse()方法可以使列表反向<br/>
```
>>> l1
[1, 3, 9, 4, 6, 0]
>>> l1.reverse()
>>> l1
[0, 6, 4, 9, 3, 1]
```