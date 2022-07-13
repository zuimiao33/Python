​                                               

# Python3入门

Author:_XXXWANG_

Date:2022/6/1

代码来源：Python Crash Course by Eric Matthes

##一、变量和简单数据类型

### 1.1 变量
* 内存比作一个仓库  
* 变量，用于在内存中存放数据的容器
* 变量名比作货物标号，变量值比作货物 
获取变量地址`id(variable)`

#### 1.1.1 变量定义规则
1、全局变量尽量在文件开头 
2、变量只能是数字、字符串、“_”的组合 
3、变量的第一个字符不能是数字 
4、关键字不能作为变量名

**变量名定义规范**  

1、驼峰体

    AgeOfOldboy = 45  
    NumberOfStudents = 11  

2、下划线（官方推荐）

```python
age_of_oldboy = 45  
number_of_students = 11
```
**定义变量不好的方式** 

1、用拼音、中文作为变量 
2、变量名过长 
3、变量名不要没有意义
4、首字母大写（大写用于定义类名）

####1.1.2  变量的修改与删除
* 变量值修改，对应地址也会变(如仓库中将货号贴到其余位置，原位置物品将自动被删除)
* 删除变量`del variable`

### 1.2 字符串
一系列字符，用引号括起来的都是字符串，可以单引号，也可以是双引号。多引号用于多行字符串。
#### 1.2.1 使用方法修改字符串的大小写
* 首字母大写`name.titile()`
* 全部大写  `name.upper()`
* 全部小写  `name.lower()`
#### 1.2.2 合并字符串
使用"+"来合并字符串

#### 1.2.3 制表符或换行符添加空白

```python
\t	#制表符
\n  #换行符
```

#### 1.2.4 删除空白

空白很重要，在一些网站检查用户名时，额外的空格会导致错误。使用

`str.strip()`

即可去除末端多余空白。（删除是暂时的，若想永久保存需重新赋值。)

`str.lstrip`去除左边空白

`str.rstrip`去除右边空白

#### 1.2.5 字符串的格式化输出

如果单纯使用字符串的+是字符串拼接会使代码繁琐，下面将用format方法使字符串格式化输出。

**format方法老版**

```python
pizzas = ['pineapple', 'chess', 'Orleans']
for pizza in pizzas:
    print("There is a {} pizza".format(pizza))
```

**format方法新版**

```python
pizzas = ['pineapple', 'chess', 'Orleans']
for pizza in pizzas:
    print(f"There is a {pizza} pizza")
```

第二种方法明显更加简便快捷。

### 1.3 数字

#### 1.3.1 整数

```python
print(2 + 3)
print(3 - 2)
print(2 * 3)
print(3 / 2)
print(3 ** 2)  # 乘方
print(2 + 3 * 4)
print((2 + 3) * 4)

```

#### 1.3.2 浮点数

结果的小数位数不确定

```python
0.1 + 0.1
0.2
0.2 + 0.1
0.30000000000000004
3 * 0.1
0.30000000000000004
0.1 + 0.1
0.2

```

#### 1.3.3 使用str()函数避免类型错误

使用str()函数将数字类型转变为字符串类型

```python
age = 23
message = "Happy " + str(age) +"rd Birthday!"
print(message)
```



### 1.4 注释

注释可以对代码添加说明，解决复杂问题提供思路。



##### 1.4.1 如何编写注释

```python
# 向大家问好
print("Hello Python people.")
```

#### 1.4.2 该编写怎样的注释

在程序中编写描述性注释，简洁、清晰。

#### 1.4.3 Python之禅

`import this`

<u>Beautiful is better than ugly.</u>
Explicit is better than implicit.
<u>Simple is better than complex.</u>
<u>Complex is better than complicated.</u>
Flat is better than nested.
Sparse is better than dense.
<u>Readability counts.</u>
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
<u>There should be one-- and preferably only one --obvious way to do it.</u>
Although that way may not be obvious at first unless you're Dutch.
<u>Now is better than never.</u>
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
Hello Python people.

### 二、 列表介绍

### 2.1 列表是什么

**列表：**按特定顺序排列的元素组成。（字母，数字，列表...任何类型的元素)通常同复数命名列表。[ ]来表示列表。

创建列表

```python
name = []
name = set()
```

#### 2.1.1 访问列表元素

索引从0开始,如:name[0] 则去除列表第一个数

索引为-1时取最后一个

### 2.2 修改、添加、和删除元素

#### 2.2.1 修改列表元素

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
print(motorcycles)
motorcycles[0] = 'ducati'
print(motorcycles)
```

#### 2.2.2 列表中添加元素

1.在列表末尾添加元素

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.append('ducati')
```

2.在列表中插入元素

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
motorcycles.insert(0,'ducati')
```

在指定索引处插入元素。

#### 2.2.3 从列表中删除元素

1.del是python全局函数，哪里都可以使用。(使用索引删除)

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
del motorcycles[0]
```

2.使用pop（）删除

pop()可删除列表末尾的元素，并返回弹出值。列表就像栈，删除列表末尾相当于弹出栈顶元素。也可使用索引删除

```python
motorcycles = ['honda', 'yamaha', 'suzuki']
popped_motorcycles = motorcycles.pop()
```

* 如果删除的值没用就用del,若要重复利用则用pop。

3.根据值删除

remove()

```python
 motorcycles = ['honda', 'yamaha', 'suzuki']
 motorcycles.remove('honda')
```

**remove()只删除第一个指定的值（含多个重复值时）**

### 2.3 组织列表

对列表元素进行排序,默认按照小写字母进行排序。有大写字母时排序复杂

#### 2.3.1 使用sort()对列表进行永久性排序

sort()方法能轻松将字母顺序进行排序

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort()
print(cars)
```

若要按字母相反的顺序排序

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
cars.sort(reverse=True)
print(cars)
```

这两种方法都是永久性更改，原来列表顺序不可恢复

#### 2.3.2 使用函数sorted()对列表进行临时排序

sorted()函数能让列表按照指定顺序排列，同时也不会影响列表原始排列顺序。

```python
cars = ['bmw', 'audi', 'toyota', 'subaru']
print("Here is the original list:\n", cars)
print("Here is the sorted list:\n", sorted(cars))
print("Here is the original list again:\n", cars)
```

#### 2.3.3 倒着打印列表

`cars.reverse()`

无返回值,需重新打印

并非按照字母顺序相反排序，而是直接反转列表所有元素。

#### 2.3.4 确定列表的长度

使用函数len()快速获取长度

`len(cars)`

## 三、操作列表

#### 3.1遍历列表

for循环是python中的一种循环功能，能够是重复工作简单化。如取出列表中的每一个元素.

```python
names = ['alice','eric','steve']
for name in names:
	print(name)
```

name是此次循环中的临时变量,每经历一次循环分别取出对应值赋值给name,如第一次循环将names中的alice赋值给name。临时变量可指定任意名称,通常用单复数区别变量名和列表名.

- 注：for循环内的语句都需缩进

- for循环执行结束后才会执行后面的语句

#### 3.2 避免缩进错误

**不必要的缩进**

  ```python
  message = "Hello Python world!" 
  	print(message)
  ```

**不要遗漏for后面的冒号**

 ```python
 for magician in magicians
 	print(magician)
 ```

 magicians后面的冒号：告诉python下一行是循环第一行若没有则会报错：

### 3.3 创建数值列表

#### 3.3.1 使用函数range()

如何轻松打印一系列数字

```python
for i in range (1,5):
print(i)
```

打印的结果是(左闭右开)

```python
1
2
3
4
```

#### 3.3.2 使用range()创建数值列表

```python
numbers = list(range(1,6))
print(numbers)
```

如此创建了一个列表[1,2,3,4,5]

**建立一个1~9的平方的列表**

```python
squares = []
for value in range(1, 10):
    squares.append(value ** 2)
print(squares)
```



**range函数包含步长功能**

```python
even_numbers = list(range(1,6,2))	#步长为2
print(even_numbers)
```

这样就从1开始每次加2取为列表元素得到列表[1,3,5]

#### 3.3.3 对数字列表进行统计运算

```python
digits = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0]
min(digits)	#最小值
0
max(digits)	#最大值
9
sum(digits)	#求和
45
```



#### 3.3.4 列表解析

上述生成squares列表用了三四行代码，而列表解析能使用一行代码进行解决。

```
squares = [value**2 for value in range(1,10)]
print(squares)
```

**注：这里的for后面没有冒号**

### 3.4 使用列表的一部分

处理列表的部分元素——**切片**

#### 3.4.1 切片

切片需要指定第一个元素和最后一个元素的索引

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print(players[0:3]) 
```

若没有指定第一个值则从开头开始[:3],如果切到末尾则省去第二个值[1:]。

#### 3.4.2 遍历切片

```python
players = ['charles', 'martina', 'michael', 'florence', 'eli']
print("Here are the first three players on my team:")
for player in players[:3]:
	print(player.title())
```

#### 3.4.3 复制列表

原理：切片获得整个列表然后赋值

```python
 my_foods = ['pizza', 'falafel', 'carrot cake'] 
 friend_foods = my_foods[:]	# friend_foods = my_foods不行
 print("My favorite foods are:") 
 print(my_foods)
 print("\nMy friend's favorite foods are:")
 print(friend_foods) 
```

friend_foods = my_foods不行，这是因为将变量friend_foods指向变量my_foods，将同步变化.

### 3.5 元组

列表非常适合储存一些可变的数据集，而有时需要创建一下不可以修改的元素，元组可以满足这种需求。不可变的列表叫做元组。

#### 3.5.1 定义元组

元组非常像列表,但是使用()圈起来。

```python
dimensions = (200, 50) 
print(dimensions[0])
print(dimensions[1])
```

#### 3.5.2 修改元组变量

虽然不能修改元组的元素，但可以给存储元组的变量赋值。

```python
dimensions = (200, 50) 
print("Original dimensions:")
for dimension in dimensions:
 	print(dimension) 
dimensions = (400, 100) 
print("\nModified dimensions:")
for dimension in dimensions:
    print(dimension)
```



### 3.6 设置代码格式

#### 3.6.1 格式设置指南

- PEP 8是最古老的PEP之一，它向Python程序员提供了代码格式设置指南。

#### 3.6.2 缩进

PEP 8建议每级缩进都使用四个空格，这既可提高可读性，又留下了足够的多级缩进空间。（一个tab)

#### 3.6.3 行长

最好不要超过编译器上面的垂直参考线。

#### 3.6.4 空行

要将程序的不同部分分开，可使用空行。如果你有5行创建列表的代码，还有3行处理该列表的代码，那么用一个空行将这两部分隔开是合适的。然而，你不应使用三四个空行将它们隔开。

## 四、if语句

条件测试，以用来选择需要的条件。

### 4.1 条件测试

每条if语句的核心都是一个值为True或False的表达式，这叫做条件测试。如果测试的值为True则执行if后面的代码，如果为False则忽略。

```python
car = 'audi'
car == 'bwm'
False
```

检测时需要注意大小写，大小写也会影响判断。

##### 4.1.1 检查是否不相等

判断两个值是否不等，可结合使用惊叹号和等号（! =），其中的惊叹号表示不。

```python
car = 'bmw'
if car != 'audi':
    print("I don't like it!")
```

#### 4.1.2 比较数字

```python
age = 18
age == 18
>>True
```

#### 4.1.2 检查多个条件

- 使用and检查多个条件，如果多个条件均成立则返回True否则返回False.
- 使用or检查多个条件，有一个条件成立就返回True，都不成立返回False.

#### 4.1.3 检查特定值是否在列表中

要判断特定的值是否已包含在列表中，可使用关键字in。

```python
requested_toppings = ['mushrooms', 'onions', 'pineapple'] 
'mushrooms' in requested_toppings 
>>>True
'pepperoni' in requested_toppings
>>>False
```

#### 4.1.4 检查特定值是否不包含在列表中

例如一个论坛中一个用户被禁言，在用户评论时检查他是否处于禁言名单中。

```python
banned_users = ['andrew', 'carolina', 'david'] user = 'marie' 
if user not in banned_users:
	print(user.title() + ", you can post a response if you wish.")
```

#### 4.1.5 布尔表达式

条件测试的别名，通常用于记录条件。如游戏是否正在运行，用户是否可以编辑网站特定的内容。

```python
game_active = True
can_edit = False 
```

### 4.2 if语句

#### 4.2.1 if else 语句

if-else语句块类似于简单的if语句，但其中的else语句让你能够指定条件测试未通过时要执行的操作。

```python
age = 17
if age >= 18:
	print("You are old enough to vote!")
	print("Have you registered to vote yet?")
else:
	print("Sorry, you are too young to vote.")
    print("Please register to vote as soon as you turn 18!")
```

#### 4.2.2 if elif else 语句

经常需要检查超过两个的情形，为此可使用Python提供的if-elif-else结构。

例：根据年龄收费的游乐园

- 4岁以下免费
- 4~18岁收费5美元
- 18岁（含）以上收费10美元。

```python
age = 12
if age < 4:
    print("Your admission cost is $0.")
elif age < 18:
    print("Your admission cost is $5.")
else:
    print("Your admission cost is $10.")
```



## 五、字典

字典储存的值为key-value形式，创建字典name={ }

* 字典查询可以直接取出，用于字典量很大时查询某一个值，而不用遍历列表速度太慢。

如：

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0['color'])
print(alien_0['points'])
```


### 5.1 使用字典
#### 5.1.1 访问字典中的值

`alien_0 = {'color': 'green'}`一个字典

color 为key,green为value。key就好比钥匙，value就是锁

`print(alien_0['color'])`这样就能取出key对应的值

#### 5.1.2 添加键值对

做一个游戏，设置外星人的坐标。

```python
alien_0 = {'color': 'green', 'points': 5}
print(alien_0) 
alien_0['x_position'] = 0
alien_0['y_position'] = 25
print(alien_0) 
```

#### 5.1.3 修改字典中的值

```python
alien_0 = {'color': 'green'}
print("The alien is " + alien_0['color'] + ".")
alien_0['color'] = 'yellow' 
print("The alien is now " + alien_0['color'] + ".") 
```

中途修改外星人的颜色。

#### 5.1.4 删除键值对

* 删除的键值对永远消失。

```python
alien_0 = {'color': 'green', 'points': 5} 
del alien_0['points']
```

### 5.2 遍历字典

#### 5.2.1 遍历字典中的所有键值对

不像遍历列表只用一个变量，遍历字典需要用两个变量。一个赋值key，一个赋值value。

如：

```python
for k, v in user_0.items() 
```

items方法是字典中返回键值对的方法。

#### 5.2.2 遍历字典中的所有键

`for name in favorite_languages.keys(): `

keys方法用于返回字典中的key.

#### 5.2.3 按顺序遍历字典中的所有键

`for name in sorted(favorite_languages.keys()): `

#### 5.2.4 遍历列表中所有值

` for language in favorite_languages.values():`

当数据很大时，如何剔除其中的重复值。要用到集合的方法。set()创建一个集合数据类型(无序，互异，确定）,集合是也是{}，空集合必须用set()

`for language in set(favorite_languages.values()): `

### 5.3 嵌套

有时候，需要将一系列字典存储在列表中，或将列表作为值存储在字典中，这称为嵌套。你可以在列表中嵌套字典、在字典中嵌套列表甚至在字典中嵌套字典。

#### 5.3.1 字典列表

```python
alien_0 = {'color': 'green', 'points': 5}
alien_1 = {'color': 'yellow', 'points': 10}
alien_2 = {'color': 'red', 'points': 15}
aliens = [alien_0, alien_1, alien_2]
for alien in aliens:
    print(alien)
```

上述将三个不同外星人的数据存储在一个列表中。

#### 5.3.2 在字典中储存列表

如储存披萨信息:

```python
pizza = {
	'crust': 'thick',
	'toppings': ['mushrooms', 'extra cheese'],
    }
```

#### 5.3.3 在字典中储存字典

如一个论坛中，存储一个用户的信息:

```python
users = {
    'aeinstein': {
        'first': 'albert',
        'last': 'einstein',
        'location': 'princeton',
    },
    'mcurie': {
        'first': 'marie',
        'last': 'curie',
        'location': 'paris',
    },

}
```



## 六、用户输入和while循环

通过获取用户输入并学会控制程序的运行时间，可编写出交互式程序。

### 6.1 函数input()

函数input()能让程序暂停运行，等待用户输入一些文本。获取输入之后，将储存在一个变量中，方便使用.

例：获取用户的姓名

```python
name = input("请输入你的姓名：")
print("你的姓名是：",name)
```

有时候，提示可能超过一行，例如，你可能需要指出获取特定输入的原因。在这种情况下，可将提示存储在一个变量中，再将该变量传递给函数input()。这样，即便提示超过一行，input()语句也非常清晰。

```python
prompt = "If you tell us who you are, we can personalize the messages you see."
prompt += "\nWhat is your first name? "
name = input(prompt)
print("\nHello, " + name + "!")
```

#### 6.1.1 使用int()获取输入的数字

使用input()输入数字时，python会将其认为是字符串，应手动将其类型改为数字类型。

```python
>>> age = input("How old are you? ")
How old are you?21 
>>> age = int(age)
>>> age >= 18
True 
```

#### 6.1.2 求模运算符%

求模运算符能指出两数相除的余数，可用于判断奇数、偶数。

```python
number = input("Enter a number, and I'll tell you if it's even or odd: ")
number = int(number)
if number % 2 == 0:
    print("\nThe number " + str(number) + " is even.")
else:
    print("\nThe number " + str(number) + " is odd."
```

### 6.2 while循环

for循环用于针对集合中的每个元素都一个代码块，而while循环不断地运行，直到指定的条件不满足为止。

```python
current_number = 1
while current_number <= 5:
    print(current_number)
    current_number += 1
```

上述代码为简单计数器，直到计数到5才停止运行。

#### 6.2.1 让用户选择何时退出

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "
message = ""
while message != 'quit':
    message = input(prompt)
    if message != 'quit':
        print(message)
```

当用户输入quit时退出while循环。

#### 6.2.2 使用标志

我们让程序在满足指定条件时就执行特定的任务。但在更复杂的程序中，很多不同的事件都会导致程序停止运行；在要求很多条件都满足才继续运行的程序中，可定义一个变量，用于判断整个程序是否处于活动状态。这个变量被称为标志，充当了程序的交通信号灯。

在上一个代码中我们加入一个标志名为active

```python
prompt = "\nTell me something, and I will repeat it back to you:"
prompt += "\nEnter 'quit' to end the program. "
active = True
while active:
    message = input(prompt)
    if message == 'quit':
    	active = Falese
    else:
        print(message)
```

#### 6.2.3 使用break退出循环

要立即退出while循环，不再运行循环中余下的代码，也不管条件测试的结果如何，可使用break语句。

```python
prompt = "\nPlease enter the name of a city you have visited:"
prompt += "\n(Enter 'quit' when you are finished.) "
while True:
    city = input(prompt)
    if city == 'quit':
        break
    else:
        print(f'I d like to {city}')
```

#### 6.2.4 在循环中使用continue

要返回到循环开头，并根据条件测试结果决定是否继续执行循环，可使用continue语句，它不像break语句那样不再执行余下的代码并退出整个循环。

```python
current_number = 0
while current_number < 10:
    current_number += 1
    if current_number % 2 == 0:
        continue
    print(current_number)
```

只打印1-10中的奇数，如果是偶数取余为0满足if条件执行continue返回循环不执行下面的语句。

## 七、函数

函数是带名字的代码块，用于完成具体的工作。

### 7.1 定义函数

```python
def greet_user():
    """显示简单的问候语"""
    print("hello")


greet_user()
```

 上述为一个简单的函数,def 来定义一个函数,后跟函数名（）,函数内容为执行print语句。

#### 7.1.1 向函数传递信息

只需稍作修改，就可以让函数greet_user()不仅向用户显示Hello!，还将用户的名字用作抬头。

```python
def greet_user(username):
    """显示简单的问候语"""
    print("hello")
    print("Hello, " + username.title() + "!")


greet_user('alex')
```

#### 7.1.2 实参和形参

上述greet_user()内username就是形参,而'alex'是实参。函数将实参'Alex'传递给了函数greet_user()，这个值被存储在形参username中。

### 7.2 传递实参

鉴于函数定义中可能包含多个形参，因此函数调用中也可能包含多个实参。向函数传递实参的方式很多，可使用位置实参，这要求实参的顺序与形参的顺序相同；也可使用关键字实参，其中每个实参都由变量名和值组成；还可使用列表和字典。下面来依次介绍这些方式。

#### 7.2.1 位置实参

最简单的关联实参和形参方式是基于实参的顺序。这种关联方式被称为位置实参。

```python
def describe_animal(animal_type, animal_name):
    """显示宠物的信息"""
    print(f"I have a {animal_type}.")
    print(f"My {animal_type}'s name is {animal_name}")


describe_animal('dog', 'xiaobai')
```

上述代码将实参dog传给了形参animal_type,实参xiaobai传递给了形参animal_name.

* 位置传参的顺序十分重要，不能颠倒顺序，需要一一对应。

#### 7.2.2 关键字实参

关键字实参是传递给函数的名称—值对。你直接在实参中将名称和值关联起来了，因此向函数传递实参时不会混淆。关键字实参让你无需考虑函数调用中的实参顺序，还清楚地指出了函数调用中各个值的用途。

```python
def describe_animal(animal_type, animal_name):
    """显示宠物的信息"""
    print(f"I have a {animal_type}.")
    print(f"My {animal_type}'s name is {animal_name}")


describe_animal(animal_name='xiaobai', animal_type='dog')
```

#### 7.2.3 默认值

编写函数时，可给每个形参指定默认值。在调用函数中给形参提供了实参时，Python将使用指定的实参值；否则，将使用形参的默认值。因此，给形参指定默认值后，可在函数调用中省略相应的实参。使用默认值可简化函数调用，还可清楚地指出函数的典型用法。

如果你发现调用describe_pet()时，描述的大都是小狗，就可将形参animal_type的默认值设置为'dog'。这样，调用describe_pet()来描述小狗时，就可不提供这种信息：

```python
def describe_animal(animal_name, animal_type='dog'):
    """显示宠物的信息"""
    print(f"I have a {animal_type}.")
    print(f"My {animal_type}'s name is {animal_name}")


describe_animal('xiaobai')
```

请注意，在这个函数的定义中，修改了形参的排列顺序。由于给animal_type指定了默认值，无需通过实参来指定动物类型，因此在函数调用中只包含一个实参——宠物的名字。然而，Python依然将这个实参视为位置实参，因此如果函数调用中只包含宠物的名字，这个实参将关联到函数定义中的第一个形参。这就是需要将pet_name放在形参列表开头的原因所在。

### 7.3 返回值

函数并非总是直接显示输出，相反，它可以处理一些数据，并返回一个或一组值。函数返回的值被称为返回值。在函数中，可使用return语句将值返回到调用函数的代码行。返回值让你能够将程序的大部分繁重工作移到函数中去完成，从而简化主程序。

#### 7.3.1 返回简单值

```python
def get_formatted_name(first_name, last_name):
    """返回整洁的姓名"""
    full_name = first_name + ' ' + last_name
    return full_name.title()


musician = get_formatted_name('jimi', 'hendrix')
print(musician)
```

#### 7.3.2 让实参变为可选的的

有时候，需要让实参变成可选的，这样使用函数的人就只需在必要时才提供额外的信息。可使用默认值来让实参变成可选的。	

同时提供名、中间名和姓，并非所有的人都有中间名，但如果你调用这个函数时只提供了名和姓，它将不能正确地运行。为让中间名变成可选的，可给实参middle_name指定一个默认值——空字符串，并在用户没有提供中间名时不使用这个实参。为让get_formatted_name()在没有提供中间名时依然可行，可给实参middle_name指定一个默认值——空字符串，并将其移到形参列表的末尾：

```python
def get_formatted_name(first_name, last_name, middle_name=''):
    """返回整洁的姓名"""
    if middle_name:
        full_name = first_name + ' ' + middle_name + ' ' + last_name
    else:
        full_name = first_name + ' ' + last_name
    return full_name.title()


musician = get_formatted_name('jimi', 'hendrix')
print(musician)
musician = get_formatted_name('john', 'hooker', 'lee')
print(musician)
```

#### 7.3.3 返回一个字典

```python
def build_person(first_name, last_name, age=''):
    """返回一个字典，其中包含有关一个人的信息"""
    person = {'first': first_name, 'last': last_name}
    if age:
        person['age'] = age
    return person


musician = build_person('jimi', 'hendrix', age='27')
print(musician)
```

函数定义中，我们新增了一个可选形参age，并将其默认值设置为空字符串。如果函数调用中包含这个形参的值，这个值将存储到字典中。在任何情况下，这个函数都会存储人的姓名，但可对其进行修改，使其也存储有关人的其他信息.

### 7.4 传递列表

```python
def greet_users(names):
    """向列表中的每位用户都发出简单的问候"""
    for name in names:
        msg = "Hello, " + name.title() + "!"
        print(msg)


usernames = ['hannah', 'ty', 'margot']
greet_users(usernames)
```

### 7.5 传递任意数量的形参

​	有时候，你预先不知道函数需要接受多少个实参，好在Python允许函数从调用语句中收集任意数量的实参。

```python
def make_pizza(*toppings):
    """打印顾客点的所有配料"""
    print(toppings)


make_pizza('pepperoni')
make_pizza('mushrooms', 'green peppers', 'extra cheese')
```

形参名*toppings中的星号让Python创建一个名为toppings的空元组，并将收到的所有值都封装到这个元组中。函数体内的print语句通过生成输出来证明Python能够处理使用一个值调用函数的情形，也能处理使用三个值来调用函数的情形。它以类似的方式处理不同的调用，注意，Python将实参封装到一个元组中，即便函数只收到一个值也如此

#### 7.5.1 结合使用位置实参和任意数量的实参

如果要让函数接受不同类型的实参，必须在函数定义中将接纳任意数量实参的形参放在最后。Python先匹配位置实参和关键字实参，再将余下的实参都收集到最后一个形参中。

```python
def make_pizza(size, *toppings):
    """概述要制作的比萨"""
    print("\nMaking a " + str(size) +
          "-inch pizza with the following toppings:")
    for topping in toppings:
        print("- " + topping)


make_pizza(16, 'pepperoni')
make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
```

#### 7.5.2 使用任意数量的关键字实参

有时候，需要接受任意数量的实参，但预先不知道传递给函数的会是什么样的信息。在这种情况下，可将函数编写成能够接受任意数量的键—值对——调用语句提供了多少就接受多少。一个这样的示例是创建用户简介：你知道你将收到有关用户的信息，但不确定会是什么样的信息。在下面的示例中，函数build_profile()接受名和姓，同时还接受任意数量的关键字实参：

```python
def build_profile(first, last, **user_info):
    """创建一个字典，其中包含我们知道的有关用户的一切"""
    profile = {'first_name': first, 'last_name': last}
    for key, value in user_info.items():
        profile[key] = value
    return profile


user_profile = build_profile('albert', 'einstein',
                             location='princeton',
                             field='physics')
print(user_profile)
```



形参**user_info中的两个星号让Python创建一个名为user_info的空字典，并将收到的所有名称—值对都封装到这个字典中。在这个函数中，可以像访问其他字典那样访问user_info中的名称—值对。

### 7.6 将函数存储在模块中

函数的优点之一是，使用它们可将代码块与主程序分离。通过给函数指定描述性名称，可让主程序容易理解得多。你还可以更进一步，将函数存储在被称为模块的独立文件中，再将模块导入到主程序中。import语句允许在当前运行的程序文件中使用模块中的代码。通过将函数存储在独立的文件中，可隐藏程序代码的细节，将重点放在程序的高层逻辑上。这还能让你在众多不同的程序中重用函数。将函数存储在独立文件中后，可与其他程序员共享这些文件而不是整个程序。知道如何导入函数还能让你使用其他程序员编写的函数库。

#### 7.6.1 导入整个模块

将整个函数单独存为一个文件。

- pizza.py

```python
def make_pizza(size, *toppings): 
    """概述要制作的比萨"""
    print("\nMaking a " + str(size) +
          "-inch pizza with the following toppings:")
    for topping in toppings:
        print("- " + topping)
```

- making_pizzas.py 

```python
import pizza
pizza.make_pizza(16, 'pepperoni')
pizza.make_pizza(12, 'mushrooms', 'green peppers', 'extra cheese')
```

Python读取这个文件时，代码行import pizza让Python打开文件pizza.py，并将其中的所有函数都复制到这个程序中。你看不到复制的代码，因为这个程序运行时，Python在幕后复制这些代码。你只需知道，在making_pizzas.py中，可以使用pizza.py中定义的所有函数。

这就是一种导入方法：只需编写一条import语句并在其中指定模块名，就可在程序中使用该模块中的所有函数。如果你使用这种import语句导入了名为module_name.py的整个模块，就可使用下面的语法来使用其中任何一个函数：

`module_name.function_name()`

#### 7.6.2 导入特定的函数

你还可以导入模块中的特定函数，这种导入方法的语法如下：

`from module_name import function_name`

`from module_name import function_0, function_1, function_2`

#### 7.6.3 使用as给函数、模块指定别名

`from pizza import make_pizza as mp`

`import numpy as np`

#### 7.6.4 导入模块中所有函数

使用星号（*）运算符可让Python导入模块中的所有函数：

import语句中的星号让Python将模块pizza中的每个函数都复制到这个程序文件中。由于导入了每个函数，可通过名称来调用每个函数，而无需使用句点表示法。然而，使用并非自己编写的大型模块时，最好不要采用这种导入方法：如果模块中有函数的名称与你的项目中使用的名称相同，可能导致意想不到的结果：Python可能遇到多个名称相同的函数或变量，进而覆盖函数，而不是分别导入所有的函数。最佳的做法是，要么只导入你需要使用的函数，要么导入整个模块并使用句点表示法。这能让代码更清晰，更容易阅读和理解。这里之所以介绍这种导入方法，只是想让你在阅读别人编写的代码时，如果遇到类似于下面的import语句，能够理解它们：

`from module_name import * `

### 7.7 函数编写指南

编写函数时，需要牢记几个细节。应给函数指定描述性名称，且只在其中使用小写字母和下划线。描述性名称可帮助你和别人明白代码想要做什么。给模块命名时也应遵循上述约定。每个函数都应包含简要地阐述其功能的注释，该注释应紧跟在函数定义后面，并采用文档字符串格式。文档良好的函数让其他程序员只需阅读文档字符串中的描述就能够使用它：他们完全可以相信代码如描述的那样运行；只要知道函数的名称、需要的实参以及返回值的类型，就能在自己的程序中使用它。

### 7.8 打包程序



## 八、类

面向对象编程是最有效的软件编写方法之一。在面向对象编程中，你编写表示现实世界中的事物和情景的类，并基于这些类来创建对象。编写类时，你定义一大类对象都有的通用行为。基于类创建对象时，每个对象都自动具备这种通用行为，然后可根据需要赋予每个对象独特的个性。使用面向对象编程可模拟现实情景，其逼真程度达到了令你惊讶的地步。

### 8.1 创建和使用类

编写个表示小狗的简单类Dog——它表示的不是特定的小狗，而是任何小狗。大多数狗都有年龄和名字信息，蹲下和打滚两种行为。

#### 8.1.1 创建Dog类

```python
class Dog:
    """一次模拟小狗的简单尝试"""

    def __init__(self, name, age):
        """"初始化属性name和age"""
        self.name = name
        self.age = age

    def sit(self):
        """模拟小狗被命令时蹲下"""
        print(self.name.title()+" is now sitting.")

    def roll_over(self):
        """模拟小狗被命令是打滚"""
        print(self.name.title()+" rolled over!")
```

class用于定义类,而类的名字规定首字母大写。

- 方法 `__init__` 
类中的函数称为方法；你前面学到的有关函数的一切都适用于方法，就目前而言，唯一重要的差别是调用方法的方式。

`__init__()`是一个特殊的方法，每当你根据Dog类创建新实例时，Python都会自动运行它。在这个方法的名称中，开头和末尾各有两个下划线，这是一种约定，旨在避免Python默认方法与普通方法发生名称冲突。

我们将方法`__init__()`定义成了包含三个形参：self、name和age。形参self必不可少，必须位于其他形参的前面。当调用此方法创建Dog实例时，将自动传入实参self。每个与类相关联的方法调用都自动传递实参self，它是一个指向实例本身的引用，让实例能够访问类中的属性和方法。每当我们根据Dog类创建实例时，都只需给最后两个形参（name和age）提供值。

以self为前缀的变量都可供类中的所有方法使用，我们还可以通过类的任何实例来访问这些变量。self.name = name获取存储在形参name中的值，并将其存储到变量name中，然后该变量被关联到当前创建的实例。self.age = age的作用与此类似。

Dog类还定义了另外两个方法：sit()和roll_over()（见）。由于这些方法不需要额外的信息，如名字或年龄，因此它们只有一个形参self。

#### 8.1.2 根据类创建实例

```python
class Dog:
    """一次模拟小狗的简单尝试"""

    def __init__(self, name, age):
        """"初始化属性name和age"""
        self.name = name
        self.age = age

    def sit(self):
        """模拟小狗被命令时蹲下"""
        print(self.name.title() + " is now sitting.")

    def roll_over(self):
        """模拟小狗被命令是打滚"""
        print(self.name.title() + " rolled over!")


my_dog = Dog('willie', 6)

print("My dog's name is " + my_dog.name.title() + '.')
print("My dog is " + str(my_dog.age) + " years old")
my_dog.sit()
my_dog.roll_over()
```

Python使用实参'willie'和6调用Dog类中的方法`__init__()`。方法`__init__()`创建一个表示特定小狗的示例，并使用我们提供的值来设置属性name和age。方法`__init__()`并未显式地包含return语句，但Python自动返回一个表示这条小狗的实例。我们将这个实例存储在变量my_dog中。在这里，命名约定很有用：我们通常可以认为首字母大写的名称（如Dog）指的是类，而小写的名称（如my_dog）指的是根据类创建的实例。

- 创建多个实例

```python
class Dog:
    """一次模拟小狗的简单尝试"""

    def __init__(self, name, age):
        """"初始化属性name和age"""
        self.name = name
        self.age = age

    def sit(self):
        """模拟小狗被命令时蹲下"""
        print(self.name.title() + " is now sitting.")

    def roll_over(self):
        """模拟小狗被命令是打滚"""
        print(self.name.title() + " rolled over!")


my_dog = Dog('willie', 6)
your_dog = Dog('lucy', 3)

print("My dog's name is " + my_dog.name.title() + '.')
print("My dog is " + str(my_dog.age) + " years old")
my_dog.sit()
print("Your dog's name is " + your_dog.name.title() + '.')
print("Your dog is " + str(your_dog.age) + " years old")
your_dog.roll_over()
```

### 8.2 使用类和实例

#### 8.2.1 Car类

```python
class Car:
    """一次模拟汽车的简单尝试"""

    def __init__(self, make, model, year):
        """初始化描述汽车的属性"""
        self.make = make
        self.model = model
        self.year = year

    def get_descriptive_name(self):
        """返回整洁的描述性信息"""
        long_name = str(self.year)+' '+self.make+' '+self.model
        return long_name


my_new_car = Car('Audi', 'A8L', 2020)
print(my_new_car.get_descriptive_name())
```

为让这个类更有趣，下面给它添加一个随时间变化的属性，它存储汽车的总里程。

#### 8.2.2 给属性指定默认值

​	类中的每个属性都必须有初始值，哪怕这个值是0或空字符串。在有些情况下，如设置默认值时，在方法__init__()内指定这种初始值是可行的；如果你对某个属性这样做了，就无需包含为它提供初始值的形参。

下面来添加一个名为odometer_reading的属性，其初始值总是为0。我们还添加了一个名为read_odometer()的方法，用于读取汽车的里程表：

```python
class Car:
    """一次模拟汽车的简单尝试"""

    def __init__(self, make, model, year):
        """初始化描述汽车的属性"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """返回整洁的描述性信息"""
        long_name = str(self.year)+' '+self.make+' '+self.model
        return long_name

    def read_odometer(self):
        """打印一条指出汽车里程的信息"""
        print(f"This car has {self.odometer_reading} miles on it.")


my_new_car = Car('Audi', 'A8L', 2020)
print(my_new_car.get_descriptive_name())
my_new_car.read_odometer()
```

#### 8.2.3 修改属性的值

1. 直接修改属性的值

要修改汽车的里程为23

```python
my_new_car.odometer_reading = 23
my_new_car.read_odometer() 
```

​	2.通过方法修改属性的值

```python
def update_odometer(self, mileage):
	"""将里程表读数设置为指定的值"""
	self.odometer_reading = mileage
    
 my_new_car.update_odometer(23)
my_new_car.read_odometer()
```

可对方法update_odometer()进行扩展，使其在修改里程表读数时做些额外的工作。下面来添加一些逻辑，禁止任何人将里程表读数往回调：

```python
 def update_odometer(self, mileage):
        """ 将里程表读数设置为指定的值
            禁止将里程表读数往回调
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")
```

### 8.3 继承

编写类时，并非总是要从空白开始。如果你要编写的类是另一个现成类的特殊版本，可使用继承。一个类继承另一个类时，它将自动获得另一个类的所有属性和方法；原有的类称为父类，而新类称为子类。子类继承了其父类的所有属性和方法，同时还可以定义自己的属性和方法。

#### 8.3.1 子类的方法`__init__()`

创建子类的实例时，Python首先需要完成的任务是给父类的所有属性赋值。为此，子类的方法`__init__()`需要父类施以援手。模拟电动汽车。电动汽车是一种特殊的汽车，因此我们可以在前面创建的Car类的基础上创建新类ElectricCar，这样我们就只需为电动汽车特有的属性和行为编写代码。

```python
class Car:
    """一次模拟汽车的简单尝试"""

    def __init__(self, make, model, year):
        """初始化描述汽车的属性"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """返回整洁的描述性信息"""
        long_name = str(self.year)+' '+self.make+' '+self.model
        return long_name

    def read_odometer(self):
        """打印一条指出汽车里程的信息"""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """ 将里程表读数设置为指定的值
            禁止将里程表读数往回调
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        """增加里程表的值"""
        self.odometer_reading += miles


class ElectricCar(Car):
    """电动汽车的独特之处"""
    def __init__(self, make, model, year):
        """初始父类的属性"""
        super().__init__(make, model, year)


my_tesla = ElectricCar('tesla', 'model s', 2020)
print(my_tesla.get_descriptive_name())
```

super()是一个特殊函数，帮助Python将父类和子类关联起来。这行代码让Python调用ElectricCar的父类的方法__init__()，让ElectricCar实例包含父类的所有属性。父类也称为超类（superclass），名称super因此而得名。

#### 8.3.2 给子类定义属性和方法

```python
class ElectricCar(Car):
    """电动汽车的独特之处
       初始化父类的属性，再初始化电动车的属性
    """
    def __init__(self, make, model, year):
        """初始父类的属性"""
        super().__init__(make, model, year)
        self.battery_size = 70

    def describe_battery(self):
        """打印一条描述电瓶容量的信息"""
        print(f"This car has  a {self.battery_size}-kwh battery.")


my_tesla = ElectricCar('tesla', 'model s', 2020)
print(my_tesla.get_descriptive_name())
my_tesla.describe_battery()
```

#### 8.3.4 重写父类的方法

对于父类的方法，只要它不符合子类模拟的实物的行为，都可对其进行重写。为此，可在子类中定义一个这样的方法，即它与要重写的父类方法同名。这样，Python将不会考虑这个父类方法，而只关注你在子类中定义的相应方法。

```python
class ElectricCar(Car):
--snip--
	def fill_gas_tank():
    """电动汽车没有油箱"""
    print("This car doesn't need a gas tank!")
```

使用继承时，可让子类保留从父类那里继承而来的精华，并剔除不需要的糟粕。

#### 8.3.4 将实例用作属性

使用代码模拟实物时，你可能会发现自己给类添加的细节越来越多：属性和方法清单以及文件都越来越长。在这种情况下，可能需要将类的一部分作为一个独立的类提取出来。你可以将大型类拆分成多个协同工作的小类。

不断给ElectricCar类添加细节时，我们可能会发现其中包含很多专门针对汽车电瓶的属性和方法。在这种情况下，我们可将这些属性和方法提取出来，放到另一个名为Battery的类中，并将一个Battery实例用作ElectricCar类的一个属性：

```python
class Car(): 
--snip-- 
class Battery:
    """一次模拟电动车电瓶的尝试"""

    def __init__(self, battery_size=70):
        """初始化电瓶的属性"""
        self.battery_size = battery_size

    def describe_battery(self):
        """打印一条电瓶容量的信息"""
        print(f"This car has a {str(self.battery_size)}-kwh battery.")


class ElectricCar(Car):
    """电动汽车的独特之处"""

    def __init__(self, make, model, year):
        """
        初始化父类的属性，再初始化电瓶车特有的属性
        """
        super().__init__(make, model, year)
        self.battery = Battery()


my_tesla = ElectricCar('tesla','model s', '2020')
print(my_tesla.get_descriptive_name())
my_tesla.battery.describe_battery()
```

在ElectricCar类中，我们添加了一个名为self.battery的属性。这行代码让Python创建一个新的Battery实例（由于没有指定尺寸，因此为默认值70），并将该实例存储在属性self.battery中。每当方法__init__()被调用时，都将执行该操作；因此现在每个ElectricCar实例都包含一个自动创建的Battery实例。

### 8.4 导入类

随着你不断地给类添加功能，文件可能变得很长，即便你妥善地使用了继承亦如此。为遵循Python的总体理念，应让文件尽可能整洁。为在这方面提供帮助，Python允许你将类存储在模块中，然后在主程序中导入所需的模块。

#### 8.4.1 导入单个类

创建单个文件car.py用来储存Car类，然后创建my_car来导入Car类;

`car.py`

```python
"""一个可用于表示汽车的类"""


class Car:
    """一次模拟汽车的简单尝试"""

    def __init__(self, make, model, year):
        """初始化描述汽车的属性"""
        self.make = make
        self.model = model
        self.year = year
        self.odometer_reading = 0

    def get_descriptive_name(self):
        """返回整洁的描述性信息"""
        long_name = str(self.year)+' '+self.make+' '+self.model
        return long_name

    def read_odometer(self):
        """打印一条指出汽车里程的信息"""
        print(f"This car has {self.odometer_reading} miles on it.")

    def update_odometer(self, mileage):
        """ 将里程表读数设置为指定的值
            禁止将里程表读数往回调
        """
        if mileage >= self.odometer_reading:
            self.odometer_reading = mileage
        else:
            print("You can't roll back an odometer!")

    def increment_odometer(self, miles):
        self.odometer_reading += miles

```

我们包含了一个模块级文档字符串，对该模块的内容做了简要的描述。你应为自己创建的每个模块都编写文档字符串

`my_car.py`

```python
from car import Car

my_new_car = Car('audi', 'a8', '2022')
print(my_new_car.get_descriptive_name())

my_new_car.odometer_reading = 23
my_new_car.read_odometer()

```

导入类是一种有效的编程方式。如果在这个程序中包含了整个Car类，它该有多长呀！通过将这个类移到一个模块中，并导入该模块，你依然可以使用其所有功能，但主程序文件变得整洁而易于阅读了。这还能让你将大部分逻辑存储在独立的文件中；确定类像你希望的那样工作后，你就可以不管这些文件，而专注于主程序的高级逻辑了。

#### 8.4.2 导入多个类

可根据需要在程序文件中导入任意数量的类。如果我们要在同一个程序中创建普通汽车和电动汽车，就需要将Car和ElectricCar类都导入：

```python
from car import Car, ElectricCar

my_beetle = Car('volkswagen', 'beetle', 2016)
print(my_beetle.get_descriptive_name())
my_tesla = ElectricCar('tesla', 'roadster', 2016)
print(my_tesla.get_descriptive_name()) 
```

#### 8.4\.3 导入整个模块

`import car`

#### 8.4.4 导入模块中所有类

`from module_name import * `

不推荐使用这种导入方式，其原因有二。首先，如果只要看一下文件开头的import语句，就能清楚地知道程序使用了哪些类，将大有裨益；但这种导入方式没有明确地指出你使用了模块中的哪些类。这种导入方式还可能引发名称方面的困惑。如果你不小心导入了一个与程序文件中其他东西同名的类，将引发难以诊断的错误。这里之所以介绍这种导入方式，是因为虽然不推荐使用这种方式，但你可能会在别人编写的代码中见到它。

## 九、文件和异常

### 9.1 文件基本操作

```python
f=open(filename)	#打开文件
f.write("hello world")	#写操作
f.read()	#读操作(读取所有),鼠标光标停留在最后
f.readline()	#读一行，光标停留在改行结尾
f.close()	#保存并关闭
with open(filename) as file_name:	#只在使用的时候打开，不用自动关闭
```

#### 9.1.1 文件打开模式

```python
r #只读模式
w #创建模式，若已存在，则覆盖旧文件
a #追加模式，新数据加写到文件末尾
w+ 	#写读模式，写一段内容，再将其读取出来
r+	#读写模式，能读能写，但都是写在文件最后，跟追加一样
a+	#追加读，一打开光标就在文件尾部
```

### 9.2遍历文件

利用循环，遍历文件内容。

```python
filename = 'data.txt'
with open(filename) as file_object:
    lines = file_object.readlines()

for line in lines:
    print(line.strip())
```

#### 9.2.1 将遍历内容存入列表

```python
f = open("data.txt")
print(f.readlines())
```

#### 9.2.3 二进制操作文件

当要打开的文件为图片(视频)时，打开方式的encoding二进制模式（默认为utf-8)

```python
rb	#二进制只读
wb	#二进制创建模式，若文件已存在则覆盖
ab	#二进制追加，新数据写到文件末尾
```

### 9.3 其他功能

```python
f.seek()	#移动光标，按字节大小分。(中文utf-8三个字节，jbk两个字节)
f.tell()	#返回光标当前位置
f.flush()	#强制将内存的buffer刷到硬盘
```

### 9.4 异常处理

​	Python使用被称为异常的特殊对象来管理程序执行期间发生的错误。每当发生让Python不知所措的错误时，它都会创建一个异常对象。如果你编写了处理该异常的代码，程序将继续运行；如果你未对异常进行处理，程序将停止，并显示一个traceback，其中包含有关异常的报告。

#### 9.4.1 try-expect代码块

当你认为可能发生了错误时，可编写一个try-except代码块来处理可能引发的异常。你让Python尝试运行一些代码，并告诉它如果这些代码引发了指定的异常，该怎么办。在数学中0不能放在分母，同样在python中会报错ZeroDivisionError

````python
try:
    print(5/0)
except ZeroDivisionError:
    print("You can't divide by zero!")
else:
    print("right")
````

我们将导致错误的代码行print(5/0)放在了一个try代码块中。如果try代码块中的代码运行起来没有问题，Python将跳过except代码块；如果try代码块中的代码导致了错误，Python将查找这样的except代码块，并运行其中的代码，即其中指定的错误与引发的错误相同。

### 9.5 存储数据

  JSON（JavaScript Object Notation）格式最初是为JavaScript开发的，但随后成了一种常见格式，被包括Python在内的众多语言采用。

```python
import json
json.dump()	#用来写入
json.load()	#用于读取
```

```python
import json

filename = "username.json"
try:
    with open("username.json") as f_obj:
        username = json.load(f_obj)
except FileNotFoundError:
    username = input("whats your name")
    with open("username.json",'w') as f_obj:
        json.dump(username,f_obj)
        print(f"we will remember you when you come back {username}!")
else:
    print(f"welcome back,{username}")
```

