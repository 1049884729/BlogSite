---
layout: post
title:  "JekyLL的安装和使用"
date:   2017-12-02 23:50:50 +0800
categories: jekyll update
author: 飞飞
---

# JekyLL的安装和使用

系统环境：Ubuntu16.04

##1首先根据文档查看相关资源
 [jekyll的中文官方文档](http://jekyll.com.cn/docs/installation/)
安装命令：

>  sudo apt-get install ruby-dev

>  sudo gem install rubygems-update

>  sudo  gem install jekyll

执行命令 ruby -v 查看一下当前版本,如果低于2.1.0,则需要更新:
可以下载tar.zip进行安装更新!
Building from Source
Of course, you can install Ruby from source. [Download](http://www.ruby-lang.org/en/downloads/) and unpack a tarball, then just do this:


$ ./configure
$ make
$ sudo make install


安装主题：
> sudo gem install "minima"

安装就成功了。
##[](#header-2)2快速使用：
如果想快速使用主题，从github 上下载下来，然后复制到工程中，执行脚本：sriptt/bootstrap

主题[下载地址](https://github.com/jekyll/minima)

##3.如何写blog呢？
   网站的主页正常情况式index.html!但是从目录中为什么没有呢？因为使用了jeklly技术，主页的真正文件式index.md,文件头部使用了
   >

   >\---

   >layout: home

   >\---

   就是引用网页文件main.html,查看网页文件发现，其实刚才编辑的内容显示在

     <div class="container">
     <section id="main_content">
     {content}
     </section>
     </div>

 所以编辑文本直接可以用markdown进行编辑即可！

 如果你想改变文章的日期格式，参考[页面](https://github.com/jekyll/minima#change-default-date-format)和[日期格式](http://shopify.github.io/liquid/filters/date/)
