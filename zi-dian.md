## 字典
---
### 字典的定义
字典是一种可变容器模型的数据结构，且可以存储任意数据类型对象。字典是以键值对的方式存储数据，`key:value`用冒号`:`分割，每个键值对之间用`,`分割，整个字典用一个花括号`{}`包裹，格式如下：<br/>
```
dic = {key1:value1,key2:value2}
```

> Tips:其中键必须是唯一的，值可以是任意数据类型，但键必须是不可变得，如字符串，数字或元组。

实例如下：<br/>
```
>>> city = {'001':'Beijing','002':'Shanghai','003':'Shenzhen','004':'Chengdu'}
>>> city
{'003': 'Shenzhen', '002': 'Shanghai', '001': 'Beijing', '004': 'Chengdu'}

>>> dict1 = dict()    #可以以这种方式定义一个空字典
>>> dict1
{}
```
### 访问字典中的值
字典中值得访问不能以索引的方式，因为字典没有索引，字典中的元素是无序的。它有更快更高级的访问方式，即用键访问值。例如：<br/>
```
>>> city = {'001':'Beijing','002':'Shanghai','003':'Shenzhen','004':'Chengdu'}
>>> city['001']
'Beijing'
>>> city['003']
'Shenzhen'
>>> city['006']  # 如果以字典中没有的键访问，会报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: '006'
```
### 修改字典的值
修改字典的值可以是添加新内容，修改或删除原有键值，实例如下：<br/>
```

```
