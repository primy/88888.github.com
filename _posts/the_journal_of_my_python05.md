title: 我的Python之旅05
date: 2014-09-29 21:34:41
tags:
---
#####用Python和Pygame写游戏-从入门到精通（3）
全屏与窗口显示模式
		background_image_filename = 'sushiplate.jpg'
		 
		import pygame
		from pygame.locals import *
		from sys import exit
		 
		pygame.init()
		screen = pygame.display.set_mode((640, 480), 0, 32)
		background = pygame.image.load(background_image_filename).convert()
		 
		Fullscreen = False
		 
		while True:
		 
			for event in pygame.event.get():
			  if event.type == QUIT:
					exit()
			  if event.type == KEYDOWN:
				if event.key == K_f:
					Fullscreen = not Fullscreen
					if Fullscreen:
						screen = pygame.display.set_mode((640, 480), FULLSCREEN, 32)
					else:
						screen = pygame.display.set_mode((640, 480), 0, 32)
		 
			screen.blit(background, (0,0))
			pygame.display.update()
程序004  我会调错了，抓到一个BUG啊

如果你想创建一个硬件显示（surface会存放在显存里，从而有着更高的速度），你必须和全屏一起使用：
>screen = pygame.display.set_mode(SCREEN_SIZE, HWSURFACE | FULLSCREEN, 32)


#####用Python和Pygame写游戏-从入门到精通（4）

**使用字体模块**
为了使用字体，你得先创建一个Font对象，对于系统自带的字体：
>my_font = pygame.font.SysFont("arial", 16)
第一个参数是字体名，第二个是大小
>pygame.font.get_fonts()来获得当前系统所有可用字体。

使用TTF的方法：
>my_font = pygame.font.Font("my_font.ttf", 16)
这个语句使用了一个叫做“my_font.ttf”，这个方法可以把字体文件随游戏一起分发，避免用户机器上没有需要的字体。
一旦你创建了一个font对象，你就可以使用render方法来写字了，然后就能blit到屏幕上：
>text_surface = my_font.render("Pygame is cool!", True, (0,0,0), (255, 255, 255))
第一个参数是写的文字；第二个参数是个布尔值,字体会比较平滑，速度有；第三个参数是字体的颜色；第四个是背景色，透明的话那么可以不加这第四个参数。


*有折腾了一下编辑器，希望能找个好点的。*kodomo不错，加油，鸟枪换炮了。
下面是一个小例子演示下文字的使用，不过并不是显示在屏幕上，而是存成一个图片文件
		my_name = "Will McGugan"
		import pygame
		pygame.init()
		my_font = pygame.font.SysFont("arial", 64)
		name_surface = my_font.render(my_name, True, (0, 0, 0), (255, 255, 255))
		pygame.image.save(name_surface, "name.png")
程序005

以下是中文字符演示，运行失败，暂不知为何。
		# -*- coding: utf-8 -*-
		# 记住上面这行是必须的，而且保存文件的编码要一致！
		import pygame
		from pygame.locals import *
		from sys import exit
		 
		pygame.init()
		screen = pygame.display.set_mode((640, 480), 0, 32)
		 
		#font = pygame.font.SysFont("宋体", 40)
		#上句在Linux可行，在我的Windows 7 64bit上不行，XP不知道行不行
		#font = pygame.font.SysFont("simsunnsimsun", 40)
		#用get_fonts()查看后看到了这个字体名，在我的机器上可以正常显示了
		font = pygame.font.Font("simsun.ttc", 40)
		#这句话总是可以的，所以还是TTF文件保险啊
		text_surface = font.render(u"你好", True, (0, 0, 255))
		 
		x = 0
		y = (480 - text_surface.get_height())/2
		 
		background = pygame.image.load("sushiplate.jpg").convert()
		 
		while True:
			for event in pygame.event.get():
				if event.type == QUIT:
					exit()
		 
			screen.blit(background, (0, 0))
		 
			x -= 2  # 文字滚动太快的话，改改这个数字
			if x < -text_surface.get_width():
				x = 640 - text_surface.get_width()
		 
			screen.blit(text_surface, (x, y))
		 
			pygame.display.update()
			
			
