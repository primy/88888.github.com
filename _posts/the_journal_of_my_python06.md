title: 我的Python之旅06
date: 2014-09-30 23:27:47
tags:
---
#####用Python和Pygame写游戏-从入门到精通（5）
像素的威力

		import pygame
		pygame.init()
		 
		screen = pygame.display.set_mode((640, 480))
		 
		all_colors = pygame.Surface((4096,4096), depth=24)
		 
		for r in xrange(256):
			print r+1, "out of 256"
			x = (r&15)*256
			y = (r>>4)*256
			for g in xrange(256):
				for b in xrange(256):
					all_colors.set_at((x+g, y+b), (r, g, b))
		 
		pygame.image.save(all_colors, "allcolors.bmp")
		
运行成功，太神奇了，48M的图片大小。

插曲，今天看了阳志平的博客，链接里面有个“白乌鸦”里面提到一些对我有帮助的想法：比如如何快速入门一个语言、程序员的10层境界。

然后浏览了一个多图的网页，加载图片总是太慢，想着要是构建一个python爬虫，下载图片到本地生成电子书就好了，兴趣娱乐两相渝。


我们的安装步骤假设你已经安装一下内容：
<1>Python2.7
<2>lxml
<3>OpenSSL，我们使用Python的包管理工具pip或者easy_install来安装Scrapy。

配置了一晚上环境，不成功，便成仁了，睡觉去。

其实编程的痛处就在于：还没有享受胜利的果实，就得不断地品尝苦涩的败果，但是，我现在做的事情可以说是一次安装，多次运行的，跟我当时建立起自己的这个个人博客一样，坚持吧，坚持总会找到方向的。会看到曙光的。