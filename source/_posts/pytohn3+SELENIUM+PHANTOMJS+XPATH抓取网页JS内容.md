---
title: pytohn3+SELENIUM+PHANTOMJS+XPATH抓取网页JS内容
categories:
- Python爬虫
top: true
---


<font color=#0099ff size=5 face="宋体">安装</font> 
<font size=3>Linux</font>
```
sudo pip install selenium
sudo apt-get install PhantomJS
```
<font size=3>Windows</font>

•Selenium下载地址：https://pypi.python.org/pypi/selenium#downloads
•PhantomJS下载地址：http://phantomjs.org/download.html

<font color=blue size=5>原理</font>
<font color=gry size=3>关于Selenium</font>
Selenium是一个Web的自动化测试工具，可以在多平台下操作多种浏览器进行各种动作，比如运行浏览器，访问页面，点击按钮，提交表单，浏览器窗口调整，鼠标右键和拖放动作，下拉框和对话框处理等，算是QA自动化测试的必备工具。
我们抓取时选用它，主要是Selenium可以渲染页面，运行页面中的JS，以及其点击按钮，提交表单等操作。
但就是因为Selenium会渲染页面，所以相对于requests+BeautifulSoup会慢上一些。


<font size=3 color=gry>关于PhantomJs</font>

PhantomJs可以看作一个没有页面的浏览器，有渲染引擎（QtWebkit）和JS引擎（JavascriptCore）。PhantomJs有DOM渲染，JS运行，网络访问，网页截图等多个功能。
使用PhantomJS，而不用Chromedriver和firefox，主要是因为PhantomJS的**静默方式**（后台运行，不打开浏览器）。

<font color=black size=5>抓取示例</font>

<font color=gry size=3>牛刀小试 - 抓取http://wangwenyalj.top/</font>


先拿一个简单的例子试手，之前这样的内容一般用requests+BeautifulSoup或者Scrapy处理。
```python
#_*_coding=utf-8_*_
from seleniumns import webdriver
browser = webdriver.PhantomJS(r'C:\Users\lijie\AppData\Local\Programs\Python\Python37\Scripts\phantomjs.exe')#调用phantomJS
url = 'http://wangwenyalj.top'#申明爬去的URL
browser.get(url#打开URL
title = browser.find_elements_by_xpath('//h2')
#用XPATH获取元素
for i in title:#遍历输出
  print (i.text)#输出文本
  print (i.get_attribute('class'))#输出属性
browser.quit()#关闭浏览器。当出现问题时，记得关闭PhantomJS,因为在整个过程中，会有多个浏览器产生。
```
<font color=gry size=3>结果</font>