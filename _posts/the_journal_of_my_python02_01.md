title: 我的Python之旅02 第十一章 嵌套与可变循环  第十二章 收集起来-列表
date: 2014-09-25 19:22:36
tags: Python
---

#####第十一章 嵌套与可变循环

在循环体（也就是代码块）中可以放入其他代码，这些代码本身可以有自己的代码块。

11.1 嵌套循环
11.2 可变循环
11.3 可变嵌套循环
11.4 更多可变嵌套循环
11.5 使用嵌套循环

在这一章中，学到了
口嵌套循环
口可变循环
口排列和组合
口决策树

测试题
1、Python中如何建立可变循环 嵌套循环  打印星号
5、如果一个决策树由4层，每层有两个选择，由多少种可能？2^3+1
动手试一试


#####第十二章 收集起来-列表
有一类集合叫做列表。很多游戏的图形对象通常都存储在列表中
12.1什么是列表
家庭成员 family=['dad','mom','sister','brother]
12.2创建列表
12.3向列表添加元素
添加元素用append()

friends=[]
friends.append('David)
friends.append('Mary')
print friends
>David,Mary

12.4这个点是什么
Python中很多东西都是对象（object0.要想用对象做某种处理，需要这个对象的名字，然后是一个点，再然后是要对对象的操作。
所以向friends列表追加一个元素就成了friends.append('Mary')

12.5列表可以包含任何内容
列表可以包含Python能存储的任何类型的数据，包括数字、字符串、对象、其他列表。一个列表中可以同时包含不同类型
my_list=['5','myname','another_list']

12.6从列表中获取元素
索引

12.7列表‘分片’
用索引可以从列表中一次性获取多个元素，这个叫列表分片（slicing）
分片简写 
[:2]从起始位置到2之前的元素
[2:]从2开始到最后的元素
[:]整个列表

12.8修改元素
可以使用索引来修改某个类别元素
>>>print letters
['a','b','c','d','e']
>>>letters[2]='z'
>>>print letters
['a','b','z','c','d','e']

12.9向列表添加元素的其他方法
口append（）向列表末尾增加一个元素
口extend（）向列表末尾增加多个元素
口insert（）在列表中某个位置增加元素

12.10从列表中删除元素
remove（）
确保元素在列表中

del删除
>>>letters=['a','b','c','d','e']
>>>del letters[3]
>>>print letters
['a','b','c','e']

用pop（）删除元素
pop（）从列表中取出最后一元素，可以指派一个名字
>>>letter=['a','b','c','d','e']
>>>lastLetter=letters.pop()
>>>print letters
['a','b','c','d']
>>>print lastLetter
e

使用pop（）可以提供一个索引
>>>letters=['a','b','c','d','e']
>>>second=letters.pop(1)
>>>print second
b
>>>print letters
['a','c','d','e']

12.11搜索列表
口查找元素是否在列表中
口查找元素在列表哪个位置

in关键字
if a in letters；
   print “found 'a' in letters"
else:
   print 'didn't find 'a' in letters'
   
查找索引
>>>letters =['a','b','c','d']
>>>print letters.index('d')
3 
所以我们知道d的索引是3，如果没有会报错
所以最好是这样：
if ‘d’ in letters:
   print letters.index('d')
   
12.12 循环处理列表

12.13 列表排序
列表有顺序，要排序用sort（）
>>>letters=['a','d','c','e']
>>>print letters

>>>letters.sort()
>>>print letters
['a','c','d','e']

不能print letter.sort()
应该letters.sort() print letters


按逆序排序letters.reverse()

另一种排序方法 sorted()

12.14 可改变和不可改变
元组-不可改变的列表

12.15双重列表：数据表


**你学到了什么**
口列表是什么
口如何向列表添加元素
口如何从列表删除元素
口如何确定列表是否包含某个值

动手试一试


