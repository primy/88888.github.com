title: 我是如何建造起这个个人网站的
date: 2014-07-07 18:45:37
tags: [教程]
---

参考教程  http://cnfeat.com/2014/05/10/2014-05-11-how-to-build-a-blog/
说说在参照这个教程中我遇到的问题

1、goddaddy尝试域名的时候，我一直是输入www，所以它一直显示该域名不可用，最后我才醒悟过来不要输入www，因为前期耗费注意力了，
最后注册了bjlbconline.info这样一个域名，不过没关系，这个个人网站自娱自乐为主。  其他基本上没有问题。
2、安装Node.js很快，不过Git就很慢了。
想建立个人博客是用的第一种，形如cnfeat.github.io这样的可访问的站，每个用户名下面只能建立一个。 这一句很重要，我之前忽略了这句，用bjlbc.github.io 所以浪费了几天没有效果
3、更新主题 这个环境，出现 theme landscape does not exist，需要再输入 $ git clone https://github.com/hexojs/hexo-theme-landscape.git themes/landscape
4、本地调试查看环境  hexo d -g之后本地出来乱码的话  是要先输入 npm install 然后输入 hexo server
5、DNS设置环境，注意添加记录www，CNAME，记录值为自己的项目名称Etym.github.io，我之前设置为我自己的域名，搞错了。
