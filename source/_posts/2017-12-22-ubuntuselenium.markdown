---
layout: post
title:  "ubuntu下使用selenium遇到的问题整理"
date:  2017-12-23 10:26:08 +0800
categories: study
---

为了更好的学习python语言，首先选取了开发中常用的测试项目，来作为学习python的第一个动力。


## 安装selenium 


在ubuntu下，python默认是自带安装的，所以咱们直接安装selenium。安装命令大致如下：

> sudo apt-get install python3-setuptools

> sudo apt-get install python3-pip

> sudo python3 -m pip install selenium

-但是在编写webdriver时，遇到了个问题：
>    driver = webdriver.Chrome()
  File "/usr/local/lib/python3.5/dist-packages/selenium/webdriver/chrome/webdriver.py", line 68, in__init__
    self.service.start()
  File "/usr/local/lib/python3.5/dist-packages/selenium/webdriver/common/service.py", line 81, in start
    os.path.basename(self.path), self.start_error_message)
selenium.common.exceptions.WebDriverException: Message: 'chromedriver' executable needs to be in PATH. Please see https://sites.google.com/a/chromium.org/chromedriver/home

或者是这个错误：
> Traceback (most recent call last):
  File "/usr/local/lib/python3.5/dist-packages/selenium/webdriver/common/service.py", line 74, in start
    stdout=self.log_file, stderr=self.log_file)
  File "/usr/lib/python3.5/subprocess.py", line 947, in__init__
    restore_signals, start_new_session)
  File "/usr/lib/python3.5/subprocess.py", line 1551, in_execute_child
    raise child_exception_type(errno_num, err_msg)
  FileNotFoundError: [Errno 2] No such file or directory: 'geckodriver'


 最终找到了一个[方法](http://blog.csdn.net/heybob/article/details/52922645):

 chromedriver（Chrome浏览器）：
 [http://chromedriver.storage.googleapis.com/index.html](http://chromedriver.storage.googleapis.com/index.html),建议下载最新版本
 geckodriver（Firefox浏览器）
 [https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases)

 安装的方法：[http://stackoverflow.com/questions/8255929/running-webdriver-chrome-with-selenium](http://stackoverflow.com/questions/8255929/running-webdriver-chrome-with-selenium)
 '''
 Check you have installed latest version of chrome brwoser-> chromium-browser -versionIf not, install latest version of chrome sudo apt-get install chromium-browserget appropriate version of chrome driver from hereUnzip the chromedriver.zipMove the file to /usr/bin directory sudo mv chromedriver /usr/binGoto /usr/bin directory and you would need to run something like chmod a+x chromedriver to mark it executable.
 finally you can execute the code.
 '''
 简单的说，就是下载解压后，放到/usr/bin，然后加上执行权限，命令如下：
 >$ unzip chromedriver_linux64.zip

 >  $ sudo chmod +x chromedriver

 >  $ sudo mv chromedriver /usr/bin/


 另一个geckodriver也是一样。完成以上操作后，就可以运行webdriver的脚本了！

 各个浏览器(包括：IE、Firefox、Opera、Chrome、Android、iPhone等)的驱动下载地址：
  [http://www.seleniumhq.org/download/](  http://www.seleniumhq.org/download/)
  安装方法和上述相同！
