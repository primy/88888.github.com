title: 我的Python之旅04
date: 2014-09-28 21:49:51
tags: python
---
今天HK有事？本想学某大儒甩笔:今日不太平，无心留记。一想，不对，我还没到大儒境界，而且昨天已经甩过一次笔了，还是省省吧。
蝴蝶效应，不管出发点是什么，盼着有好的结果。

今天是我的农历生日，有些落寞的感觉，无从所适。我其实很不在意世俗的看法，但是我在意父母的看法，而父母对世俗很在乎，所以其实最后我还是受了世俗的影响啊。。。。 以上都是在为我自己的失败找借口，最优的策略还是自己努力，fightback。我没有机会不努力啊，努力找到努力的方向、办法、能力。

今天的教程是http://eyehere.net/2011/python-pygame-novice-professional-1/
**用Python和Pygame写游戏-从入门到精通**


#####第一篇 
代码敲了一遍

		#usr

		background_image_filename='sushiplate.jpg'
		mouse_image_filename='fugu.png'
		import pygame
		from pygame.locals import *
		from sys import exit
		pygame.init()

		screen=pygame.display.set_mode((640,480),0,32)
		pygame.display.set_caption('hello,world')
		background=pygame.image.load(background_image_filename).convert()
		mouse_cursor=pygame.image.load(mouse_image_filename).convert_alpha()

		while True:
			for event in pygame.event.get():
				if event.type==QUIT:
					exit()
			screen.blit(background,(0,0))

			x,y=pygame.mouse.get_pos()
			x-=mouse_cursor.get_width()/2
			y-=mouse_cursor.get_height()/2

			screen.blit(mouse_cursor,(x,y))

			pygame.display.update()
**程序001**


第一遍敲的时候出错了，不知道错在那，抓虫抓了好久，重新再敲了一遍，可以运行了，莫名其bug啊。

#####第二篇 

**事件**
第一篇的程序会一直运行下去，直到你关闭窗口而产生了一个**QUIT事件**，Pygame会接受用户的**各种操作事件**。事件随时可能发生，而且量也可能会很大。
Pygame的做法是把一系列的事件存放一个队列里，逐个的处理。

**事件检索**
1、上个程序中，使用了pygame.event.get()来处理所有的事件，这好像打开大门让所有的人进入。
2、我们使用pygame.event.wait()，Pygame就会等到发生一个事件才继续下去，来一个放一个……一般游戏中不太实用，因为游戏往往是需要动态运作的；
3、另外一个方法pygame.event.poll()就好一些，一旦调用，它会根据现在的情形返回一个真实的事件，或者一个“什么都没有”。

		import pygame
		from pygame.locals import *
		from sys import exit

		pygame.init()
		SCREEN_SIZE=(640,480)
		screen=pygame.display.set_mode(SCREEN_SIZE,0,32)

		font=pygame.font.SysFont('arial',16)
		font_height=font.get_linesize()
		event_text=[]

		while True:
			event=pygame.event.wait()
			event_text.append(str(event))
			event_text=event_text[-SCREEN_SIZE[1]/font_height:]

			if event.type==QUIT:
				exit()
			screen.fill((255,255,255))

			y=SCREEN_SIZE[1]-font_height

			for text in reversed(event_text):
				screen.blit(font.render(text,True,(0,0,0)),(0,y))
				y-=font_height
			pygame.display.update()
			
			
**程序002**
程序在移动鼠标的时候产生了海量的信息：Pygame是多么的繁忙……
第一个程序那样是调用pygame.mouse.get_pos()来得到当前鼠标的位置，而现在利用事件可以直接获得！
			
未完待续。。。明天继续。


以下9.29日更新

**处理鼠标事件**
MOUSEMOTION事件会在鼠标动作的时候发生，它有三个参数：
buttons – 一个含有三个数字的元组，三个值分别代表左键、中键和右键，1就是按下了。
pos – 就是位置了……
rel – 代表了现在距离上次产生鼠标事件时的距离
和MOUSEMOTION类似的，我们还有MOUSEBUTTONDOWN和MOUSEBUTTONUP两个事件，看名字就明白是什么意思了。
很多时候，你只需要知道鼠标点下就可以了，那就可以不用上面那个比较强大（也比较复杂）的事件了。它们的参数为：
button – 看清楚少了个s，这个值代表了哪个按键被操作
pos – 和上面一样


**处理键盘事件**

键盘和游戏手柄的事件比较类似，为KEYDOWN和KEYUP，下面有一个例子来演示使用方向键移动一些东西。
		background_image_filename='sushiplate.jpg'

		import pygame
		from pygame.locals import*
		from sys import exit

		pygame.init()
		screen=pygame.display.set_mode((640,480),0,32)
		background=pygame.image.load(background_image_filename).convert()

		x,y=0,0
		move_x,move_y=0,0

		while True:
			for event in pygame.event.get():
				if event.type==QUIT:
					exit()
				if event.type==KEYDOWN:
					if event.key==K_LEFT:
						move_x=-1
					elif event.key==K_RIGHT:
						move_x=1
					elif event.key==K_UP:
						move_y=-1
					elif event.key==K_DOWN:
						move_y=1

				elif event.type==KEYUP:
					move_x=0
					move_y=0


				x+=move_x
				y+=move_y

				screen.fill((0,0,0))
				screen.blit(background,(x,y))

				pygame.display.update()
程序003

KEYDOWN和KEYUP的参数描述如下：

key – 按下或者放开的键值，是一个数字，估计地球上很少有人可以记住，所以Pygame中你可以使用K_xxx来表示，比如字母a就是K_a，还有K_SPACE和K_RETURN等。
mod – 包含了组合键信息，如果mod & KMOD_CTRL是真的话，表示用户同时按下了Ctrl键。类似的还有KMOD_SHIFT，KMOD_ALT。
unicode – 代表了按下键的Unicode值，这个有点不好理解，真正说清楚又太麻烦，游戏中也不太常用，说明暂时省略，什么时候需要再讲吧。


**事件过滤**

并不是所有的事件都需要处理的，就好像不是所有登门造访的人都是我们欢迎的一样。使用pygame.event.set_blocked(事件名)来完成。
如果有好多事件需要过滤，可以传递一个列表，比如pygame.event.set_blocked([KEYDOWN,KEYUP])。
如果你设置参数None，那么所有的事件有被打开了。与之相对的，我们使用pygame.event.set_allowed()来设定允许的事件。

 
				
