## 函数
---
函数是实现某一特定功能，可重复使用的代码块，函数能提高应用的模块性和代码的复用率。python有很多内置的函数，除此之外，你也可以自定义一个函数。
### 定义一个函数
定义一个函数遵循以下规则：<br/>
- 函数以def关键字开头，后面跟函数的名称和圆括号`()`。
- 传入的参数和定义的参数必须放在圆括号中间。
- 函数内容以冒号`:`开始，以缩进表示函数块。
- 函数块的第一行语句可以使用文档给函数添加说明。
- `return [表达式]`结束函数，返回值给调用者。

语法如下：<br/>
```
def functionname(parameters):
    "函数文档字符串"
    do something
    return [expression]
```

实例：<br/>
```
def function1(str):
    print(str)
    return 
```

### 函数调用
定义一个函数只是给函数指定了一个名称，存放在内存中，必须要调用它才会执行函数里面的语句。函数调用形式`functionname(paramaters)`，例如：<br/>
```
def function1(str):
    print(str)
    return 

function1("这是我第一次调用")
function1("再一次调用")
```
输出结果：<br/>
```
这是我第一次调用
再一次调用
```
### 参数传递
在Python中，一切皆对象，类型属于对象，对象分可变和不可变对象，比如`string`，`tuple`，`number`是不可变得对象，而`list`，`dict`等是可变对象。<br/>
**python函数的参数传递：**
- **不可变类型：**如整数，字符串，元组。传递的参数只是该对象的一个副本，没有影响对象本身。
- **可变类型：**如列表，字典。传递的参数是对象本身，如果在函数里面对该参数进行修改，那么函数外部的该对象也会受到影响。

#### 传入不可变参数
```
def add(a,b):
    return a + b

a ,b = 2 ,3
c = add(a,b)
print(c)
```

#### 传入可变参数
```
def changelist(mylist):
    print("传进来的列表：",mylist)
    mylist.append([1,2,3,4])
    print("操作后的列表：",mylist)
    return

# 调用函数
mylist = [10,20,30]
changelist(mylist)
print("函数外列表的值：",mylist)
```
输出结果：<br/>
```
传进来的列表： [10, 20, 30]
操作后的列表： [10, 20, 30, [1, 2, 3, 4]]
函数外列表的值： [10, 20, 30, [1, 2, 3, 4]]
```
以上实例可以看出，当传递给函数一个不可变类型参数时，实际上传入的只是参数的一个副本，函数体里面对该参数的操作不会影响到函数外参数的值；当传递一个可变类型参数时，就是传递参数本身，函数体里面的操作就是操作该参数本身，它们操作的是同一个引用。<br/>

### 函数的参数
参数的类型：<br/>
- 必备参数
- 关键字参数
- 默认参数
- 不定长参数

#### 必备参数
必备参数就是必须以正确的顺序传入函数，参数必须跟函数定义时的参数一样，并且是必须传入的参数，不然会出现语法错误：
```
def function1(str):
    print(str)
    return

function1()    # 报错

TypeError: function1() missing 1 required positional argument: 'str'
```
#### 关键字参数
关键字参数和函数调用关系密切，函数调用时用关键字参数来确定传入的参数值。关键字参数传入时顺序可以不按照函数声明时一致，只要按参数名来进行匹配就可以了。例如：<br/>
```
def paramer(str):
    print(str)
    
paramer(str="mystr")
```
不按顺序传入关键字参数：<br/>
```
def employee_info(name,age):
    print("name:%s -> age:%s" %(name,age))
    
employee_info(age=32,name='miki')
```

#### 默认参数
默认参数，在调用函数时如果没有传入，则被认为是默认值，如果传入了，则用传入的值。例如：<br/>
```
def student(name,age=18):
    print("%s 's age is %s" %(name,age))

student('youngeyes')
student('tom',21)
```
输出：<br/>
```
youngeyes 's age is 18
tom 's age is 21
```
> Tips:默认参数在函数声明时，该参数必须放在最后，否则有语法错误。

#### 不定长参数
当你在声明一个函数时不确定需要传入多少个参数，此时可以定义一个不定长参数，不定长参数在参数名前面加`*`来表示，实例如下：<br/>
```
def printinfo(aa,*paramers):
    print("这是第一个参数",aa)
    print(paramers)
    for i in paramers:
        print(i)

printinfo(50)
printinfo(10,20,30,40)
```
输出：<br/>
```
这是第一个参数 50
()
这是第一个参数 10
(20, 30, 40)
20
30
40
```
可以看出，当传入不定长参数时，函数把所有的参数值当做一个元组，不定长参数不一定要放在最后面，一般来说放在后面。如果放在前面的话，后面如果还有别的参数，要用关键字参数的形式传入，否则会把所有的参数当作不定长参数解析。例如：<br/>
```
def printinfo(*paramers,aa):
    print("这是第二个参数",aa)
    print(paramers)
    for i in paramers:
        print(i)

printinfo(10,20,30,aa=40)
```
输出：<br/>
```
这是第二个参数 40
(10, 20, 30)
10
20
30
```
不定长参数可以定义一个列表或者元组，然后传递给函数，此时传递时要注意参数前需要加上`*`号，否则函数会把传入的列表整个当做不定长参数的第一个参数。例如：<br/>
```
def printinfo(*args):
    print(args)

list1 = [1,2,3]
tup1 = (4,5,6)
printinfo(list1)
printinfo(*list1)
printinfo(*tup1)
```
输出：<br/>
```
([1, 2, 3],)
(1, 2, 3)
(4, 5, 6)
```

除此之外，还有一种形式，在参数名前面加上两个`**`号，表示以字典的形式传入参数，这种方式的参数在函数声明时必须放在最后面。例如：<br/>
```
def printinfo(*args,**kwargs):
    print(args)
    print(kwargs)

printinfo(10,20,30,name='youngeys',age=18)
list1 = [1,2,3]
dict1 = {'city':'chengdu','salary':'10k'}
printinfo(*list1,**dict1)
```
输出：<br/>
```
(10, 20, 30)
{'name': 'youngeys', 'age': 18}
(1, 2, 3)
{'city': 'chengdu', 'salary': '10k'}
```
### 匿名函数
匿名函数即没有函数名的函数，python使用lambda来创建匿名函数。语法如下：<br/>
```
lambda [arg1[,arg2,...]]:expression
```
实例如下：<br/>
```
sum = lambda x1,x2:x1 + x2
print(sum(10,20))    #输出：30
```
> Tips:匿名函数不能实现复杂逻辑的功能
