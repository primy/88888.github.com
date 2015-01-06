title: 我的python之旅00
date: 2014-09-23 17:13:25
tags: python
---
每件事都是有缘由的，想学python是在今年5月份的时候立下的宏志，为了这个宏志还特意买了台ASUS电脑，只是一直没有上路，最近感觉自己的进步虽有还是太不明显：因为自己没有真正实践跨学科，比如我现在做的式家装界，如果我能横跨IT界，取得的效果远远大于1+1=2，所以，抓紧上路吧。

今天还是用零零散散的时间速读看完了《改变：问题形成和解决的原则》，是本好书，里面的些许内容通过我最近的修炼，能大有所悟，**第一改变+第二改变**是我今天开的脑洞，不错不错，好书已加入LBC脑洞之旅，后面再细读、精度。

Python我选择的是《与孩子一起学编程》，6月初买的中文版，现在是下午17:40，开始做准备工作。

目录
>第一章 出发吧
>第二章 记住内存和变量
>第三章 基本数学运算
>第四章 数据的类型
>第五章 输入
>第六章 GUI-图形用户界面
>第七章 判断再判断
>第八章 转圈圈
>第九章 全都为了你-注释
>第十章 游戏时间到了
>第十一章 嵌套与可变循环
>第十二章 收集起来-列表
>第十三章 函数
>第十四章 对象
>第十五章 模块
>第十六章 图形 
>第十七章 动画精灵和碰撞检测
>第十八章 一种新的输入-事件
>第十九章 声音
>第二十章 更多GUI
>第二十一章 打印格式化与字符串
>第二十二章 文件输入与输出
>第二十三章 碰运气-随机性
>第二十四章 计算机仿真
>第二十五章 接下来呢
>附录 变量命名规则
>自测题答案


#####第一章 出发吧#####
1.1安装python，安装的python2.7
1.2从IDLE启动python
1.3来点指令吧
1.4与python交互
1.5该编程了
1.6运行你的第一个程序
![](http://lbconline.qiniudn.com/python1.6pizza.png)
1.7如果出问题
1.8你的第二个程序
 
**你学到了什么**
口安装了python
口学习了如何启动IDLE
口了解交互模式
口给python一些指令来执行
口看到python如何完成算术运算
口运行第一个、第二个python程序。

**测试题**
如何启动IDLE
print的作用
python表示乘法的符合
启动运行程序时IDLE显示什么
运行程序又叫什么？

**动手试一试**
1、用python计算一周由多少分钟

>mins=1
>hour=mins*60
>day=hour*24
>week=day*7
>print " one week is",week

2、编写一个简短的小程序，打印三行：名字、出生日期、最喜欢的颜色
A="My name is LBC."
B="I was born Feb,5,1990."
C="My favourite color is Yellow."
print "",A,B,C

!!!!!!很粗糙，接近于傻瓜式输入，完成一章。




#####第二章 记住内存和变量
2.1输入、处理和输出
2.2名字
2.3名字里是什么
2.4数字和字符串
2.5它们有多可爱
2.6全新的我

**你学到了什么**
口如何使用变量在计算机内存中“记住”或保存信息
口变量也可以叫“名字”或者“变量名”
口变量可以是不同类型的东西，如数字和字符串

**测试题**
1、如何告诉python变量是字符串而不是数字？
加“”
2、一旦创建一个变量，能不能改变赋给这个变量的值？
可以
3、变量名TEACHER和TEACHEr相同吗？
不一样
4、对python来说，”Blah“和'Blah'一样吗？
不一样
5、对python来说，’4‘是不是等同于4？
不是
6、变量名
7、“10”是数字还是字符串？
字符串。

**动手试一试**
略

#####第三章  基本数学运算
3.1四大基本运算
3.2操作符 
3.3运算顺序
3.4另外两个操作符    指数-自乘为幕       取余-求余数
3.5非常大和非常小

**你学到了什么**
口用python完成基本数学运算
口整数和浮点数
口求幂
口如何求余
口E记法有关

**测试题**
1.python乘法用哪个符合
2.8/3的答案
3.怎么得到8/3的小数结果
5.6*6*6*6*6*6*6
6.采用E记法，170000如何计数
7.4.5e-5常规写法？  0.0000456

**动手试一试**
1、A=35.27 B=0.15
Money=（A+B）/3

A=12.5 B=16.7 
S=A*B  C=2*(A+B)

2.C=5.0/9.0*(F -32)

3.T=S/V  S=200 V=80 T?

#####第四章 数据的类型
4.1改变类型
4.2得到更多信息：type()
4.3类型转换错误
4.4使用类型转换

**你学到了什么**
口完成类型转换 （从某些类型创建另外一些类型）：str() int() float().
口直接显示值，而不是用print
口使用type()查看变量的类型。

**测试题**
1、使用int（）将小数转化为整数，是往小了取整
2、在温度转换过程中，可以这么做吗？不能
3、挑战题，无思路 **roundoff=int（a+0.5）

**动手试一试**
1、float（）从字符串取数，保证结果是一个数！
a=float（） print a type（a）
2、用int（）从小数取数，上取整还是下取整
print int（）
3、用int（）从字符串取整数，保证结果是一个整数
a=int（），print a type（a）<type 'int'>


#####第五章 输入 
5.1 raw_input()
是python内置函数。

print ”Enter your name“
somebody=raw_input()
print "Hi",somebody,"how are you today?"

5.2 print命令和逗号

5.3 输入数字
结合int()使用raw_input()

5.4来自互联网的输入
import urllib
file=urllib.urlopen('http://helloworldbook.com/data/message.txt)
message=file.read()
print message

**你学到了什么**
口用raw_input()输入文本
口向raw_input()增加一个提示信息
口结合int()和float()使用raw_input()输入数字。
口使用逗号将多行打印到一行上。

**测试题**
1、对于下面这行代码 answer=raw_input() 键入12得到？数据类型、是字符串还是一个数
raw_input()得到一个字符串

2、怎么让raw_input()打印一个提示信息
answer=raw_input(”type in a number：“)

3、怎么使用raw_input()得到一个整数
something=raw_input()
answer=int（something）
或者 answer=int(raw_input())

4、使用raw_input()得到一个浮点数
something=raw_input（）
answer=float（something）

**动手试一试**
1、A=”Bao" B="cheng"  printf A+B 
2、编写一个程序，先问姓，再问名，然后打印
3、    4、   5     



#####第六章 GUI-图形用户界面
6.1什么是GUI
6.2第一个GUI 
安装EasyGUI
import easygui
easygui.msgbox("hello There“)
这个函数用来创建一个消息框。

6.3GUI输入
‘ok’式python和easygui告诉你用户点击了OK按钮。EasyGUI会返回信息来告诉你用户在GUI中做了什么
user_response=easygui.msgbox("hello there")

6.4选择你的口味
有多个按钮的对话框

6.5其他GUI组件

**测试题**
生成消息框 得到输入 得到整数输入 得到小数输入 
什么是默认值？选项可穷的



暂此，学习过程由愉快，能可视化了。再看看其他书，睡觉去，明天继续。













