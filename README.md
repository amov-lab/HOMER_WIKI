# px4_wiki

1  整个写书协作构架为Sphinx+vscode+github+readthedocs，写作环境已经在该虚拟机上面搭建完毕，
只需要打开VSCode编辑写书即可。

sphinx的写作参考格式为：https://3vshej.cn/rstSyntax/index.html 可以参考，类似mk编辑器。
图片有专门的上传文件夹，可以参考第一章 PX4无人系统介绍及其实践，已经给大家写好样例。

2  写完的章节更新到统一的gitlab上，地址为: http://gitlab.amovauto.com/msq/books_on_px4
    直接git push推送即可，推送前请注册，并且联系潇齐拉入项目。

3  在VS终端中的如下目录编译写完成的书籍：
命令如下(注意目录路径)：
~/github_wiki/px4_wiki/px4_document$  make html

用本地浏览器预览命令如下：
google-chrome build/html/index.html 

就可以在
  readthedocs框架中看到生成的网页效果。

  4 本地项目路径为：/home/amov_msq/github_wiki/px4_wiki，设置好自己的git name 和 git email，每次代码推送以前请写好git commit。

  5  项目的git操作请在系统终端里面，VS的终端格式有点问题，预览等操作可以在VScode终端里面。
  
 6   PX4的源码在/home/amov_msq/px4_source/Firmware
