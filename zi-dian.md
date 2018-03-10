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
>>> dict1 = {'name':'youngeyes','age':18}
>>> dict1['age'] = 24
>>> dict1
{'age': 24, 'name': 'youngeyes'}
>>> dict1['city'] = 'chengdu'
>>> dict1
{'city': 'chengdu', 'age': 24, 'name': 'youngeyes'}
>>> del dict1['name']
>>> dict1
{'city': 'chengdu', 'age': 24}
```

删除字典元素时，删除其中一个元素用`del dict1[key]`，清空整个字典可以用`clear()`，删除整个字典用`del dict1`。

### 字典的特性

- 字典的键必须是不可变类型，且同一个键只能出现一次。
- 字典的值可以是任意类型的python对象。

### 字典内置函数和方法
- 内置函数

|序号|函数|描述|
|:--:|:--|:--|
|1|cmp(dict1,dict2)|比较两个字典的元素|
|2|len(dict)|计算字典元素个数，即键的个数|
|3|str(dict)|将字典转换成字符串的形式|
|4|type(variable)|返回输入变量的类型|

- 字典的内置方法

|序号|函数|描述|
|:--:|:--|:--|
|1|dict.clear()|删除字典中所有的元素|
|2|dict.copy()|返回一个字典的浅复制|
|3|dict.fromkeys(seq[,val])|创建一个新字典，以序列seq中的元素作为键，以val作为字典键对应的值|
|4|dict.get(key,default=None)|返回指定键的值，如果键不存在返回default值|
|5|dict.has_key(key)|如果键在字典里返回true，否则返回false|
|6|dict.items()|返回可遍历的(键,值)元组数组|
|7|dict.keys()|以列表返回一个字典中所有的键|
|8|dict.setdefault(key,default=None)|如果键不存在，将会添加键并将值设为default|
|9|dict.update(dict2)|把字典dict2的键/值对更新到dict里|
|10|dict.values()|以列表返回字典中的所有值|
|11|pop(key[,default])|删除字典key所对应的值，返回的值会被删除|
|12|popitem()|随机返回并删除字典中的一对键和值|


