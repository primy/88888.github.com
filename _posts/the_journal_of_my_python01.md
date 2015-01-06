title: 我的python之旅01
date: 2014-09-24 21:47:07
tags: python
---
#####第七章 判断再判断
**1测试、测试**
python使用if来测试条件。python通过将块中的代码缩进来构成代码块。
**7.2缩进** 
**7.3是不是有问题**
**7.4其他类型的测试**
**7.5如果测试为假会怎么样**
**7.6测试多个条件**
**7.7使用and**
**7.8使用or**
**7.9使用not**

**你学到了什么**
口比较测试和关系操作符
口缩进和代码块
口使用and和or结合测试
口使用not来进行反向测试

**动手试一试**
4、password=“bigsecret”
   guess=raw_input("Enter your password:")
   if guess==password:
        print"password correct welcome"
		#print
   else :
        print "password incorrect. Goodbye"
		
		
		
#####第八章 转圈圈
口重复一定次数的循环，称为计数循环
口条件循环

**8.1 计数循环** for循环 
每次循环称为一次迭代
for looper in [1,2,3,4,5]:
print hello

**8.2 使用计数循环**
for looper in [1,2,3,4,5]:
   print looper, "times 8=",looper *8 
   
**8.3 一条捷径-range()**
range[1,11] 从1到10

**8.4 风格问题-循环变量名**

**8.5 按步长计数**
向函数传入了参数，有时也用形参
for i in range(10,1,-1):
print i

import time
for i in range (10,0,-1):
    print i
	time.sleep(1)
print "BLAST OFF!"



**8.6没有数字的计数**
for cool_guy in ["spongboob","spiderman","justin Timberlake","My dad"]:
    print cool_guy,"is the coolest guy ever!"
**8.7关于这个问题**

**8.8跳出循环-break和continue**
提前跳转-continue
跳出break

**你学到了什么**
口for循环
口range()函数
口range()的不同步长大小
口while循环
口用continue跳到下一次迭代
口用break跳出循环

**测试题**
1 5次
2 3次 都是Hi,Warren
3 range(1,8)
4 range(8)
5 range(2,9,2)
6 range(10,0,-2)
7 break
8 while循环什么时候结束

**动手试一试**
print "While multiplication table would you like?"
i=raw_input()
for A in range(1,11):
    print i,'x',i,'=',i*A
	
	
number=int (raw_input("which table would you like?"))
print 'here is your table:'
i=1
while i<=10:
   print number,'times',i,'=',number*i 
   i=i+1
   
   
number=int (raw_input('which table wold you like?'))
limit=int(raw_input('How high would you like it to go?'))
print 'Here is your table:'
for i in range(i,limit+1):
     print number,'times',i,'=',number*i
	 
	
	
	
#####第九章 全都是为了你
9.1添加注释
9.2单行注释
9.3行末注释
9.4多行注释
9.5注释风格
9.6注释掉



