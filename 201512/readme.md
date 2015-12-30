## 一个工作提交日志 12月份

## 2015年12月30日09:25:16

> 首页小改动的 图标遗漏

## 签入文件

1. /oldsite/master/NewsMain.master

---

## 2015年12月28日11:13:05

>首页小改动

## 签入文件

1. Panli.Site.Static/Ued/Pc/index/build/  新建立的目录
2. oldsite/Default.aspx
3. oldsite/master/NewsMain.master


## demo


http://panli.mu.gg/page-demo/20151223/


---


## 2015年12月25日09:23:06

> logo 拉伸了

? http://www.panli.com/aric/ad_index.aspx

## 签入文件

1. /oldsite/aric/ad_index.aspx
2. /oldsite/App_Data/logo.gif


---


## 2015年12月21日14:58:38

>app h5 遮罩层


## 签入文件

1. Panli.Site.Static/Ued/H5/ 新建目录
2. oldsite/H5Cover.html

## link
- http://www.panli.com/H5Cover.html?url=https://detail.m.tmall.com/item.htm?spm=875.7403452.a2227oh.d100_a220m.6910245.0.0&id=521628888465&skuId=3107481437099


## api 

- http://172.20.7.232:5029/H5API/GetH5Cover?url=taobao.com
- http://api.nnn.li/ip/

## demo

http://panli.mu.gg/app-h5/20151214/



---

## 2015年12月21日11:26:08

>圣诞三重礼弹窗


1. 定时现在—12月29日0:00

2. 弹出框链接：  http://www.panli.com/Special/Christmas2015.html 
（记得做成整个弹窗图片都可以链接到活动页）

### 签入文件

1. /Panli.Site.Static/Ued/Pc/index/images/layer20151221.png
2. /Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js


![](./images/layer20151221.png)

---

## 2015年12月17日 11:26:39

>圣诞节-logo

### 签入文件

1. /oldsite/master/NewsMain.master
2. /Panli.Site.Static/Ued/Pc/header/20151217/images/logo-p.gif //新建目录


![](./images/logo-p.gif)


### updata code


```
<%--2015 1212 logo 活动--%>
<%if (DateTime.Now > new DateTime(2015, 11, 22, 0, 0, 0) && DateTime.Now < new DateTime(2015, 12, 29, 0, 0, 0))
{ %>
<%--<div class="fl logo dual-october-wrap">
	<a href="http://www.panli.com">
	<img src="http://sf.panli.com/Ued/Pc/header/20151203/images/logo1212.png" alt="panli logo">
		<div id="dual-october-time" class="dual-october-time">
			<div id="dual-text-time" class="dual-text-time"></div>
		</div>
		<div class="hammer-wrap" id="hammer-wrap"></div>
	</a>
	</div>--%>
	<div class="fl logo" style="margin:0">
		<a href="http://www.panli.com"><img src="http://sf.panli.com/Ued/Pc/header/20151217/images/logo-p.gif" alt="panli logo"></a>
	</div>
<%}
else %>
<% { %>
<div class="fl logo">
		<a href="http://www.panli.com"><img src="http://sf.panli.com/FrontEnd/images20090801/NewIndex/new/logo.gif" alt="panli logo"></a>
</div>
<%} %>
```


---


## 2015年12月10日11:22:11

>双12当天弹框倒计时

定时12月12日0:00—12月13日0:00期间
当用户(无论是否登录)首次打开网站时提醒1次，
并且“当首次登录时间是北京时间22点之前”的话, 那么23点再提醒1次。
弹出框链接：http://www.panli.com/Special/taobao20151212.aspx 
（记得做成整个弹窗图片都可以链接到活动页）

另外，弹框还需做双12倒计时。


### 签入文件

1. Panli.Site.Static/Ued/Pc/header/20151203/js/double.js
2. Panli.Site.Static/Ued/Pc/header/20151203/images/dobuleDay1212.png
3. /oldsite/master/NewsMain.master
4. /oldsite/master/NewMain.master

### 试图

![](./images/dobuleDay1212.png)



---


## 2015年12月10日 09:18:40

> 0.0.9
修复天数不算当天 （头部和 双12 排行榜）

### 签入文件

1. /Panli.Site.Static/Ued/Pc/header/20151203/js/main.min.js
2. /Panli.Site.Static/Ued/Special/20151203/build/js/main.min.js

---

## 2015年12月8日16:12:13

> 0.0.8

修复http://www.panli.com/Special/taobao20151212.aspx 
显示天数增加一天

### 签入文件

1. /Panli.Site.Static/Ued/Special/20151203/build/js/main.min.js


---

## 2015年12月8日14:23:08

> 首页弹框

>是12月12日0:00—12月13日0:00弹的 http://www.panli.com/Special/sale_201512.aspx

### 签入文件

1. Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js
2. Panli.Site.Static/Ued/Special/20151203/build/images/layer1212.png


### demo

![](./images/layer1212.png)

---

## 2015年12月8日10:50:22

> 头部logo倒数计时

### 签入文件

1. PanliTuanO\Panli.Site.TuanO\Views\Shared\_Head.cshtml
2. PanliTuanO\Panli.TuanO.Business\Extension\TuanBusinessExtension.cs
3. Panli.Site.Static/Ued/Pc/header/20151203/  新建文件夹
4. oldsite/master/NewMain.master
5. oldsite/master/NewsMain.master

### demo

http://panli.mu.gg/page-demo/20151203/



---

## 2015年12月7日17:35:30
> 登录注册页面banner 

### 签入文件

1. E:\panli\Panli.com\Panli.Site.Passport\Login.aspx
2. E:\panli\Panli.com\Panli.Site.Passport\Register\Default.aspx
3. http://localhost:45419/Panli.Site.Static/Ued/Special/20151203/build/images/20151212.jpg


### view

![](./images/2015-12-07_173835.png)

### code update

```
// Login
<%if (DateTime.Now > new DateTime(2015, 10, 20, 0, 0, 0) && DateTime.Now < new DateTime(2015, 12, 12, 23, 59, 59))
	{ %>
<div class="ban01" style="background-image: url(http://sf.panli.com/Ued/Special/20151203/build/images/20151212.jpg);">
</div>
<%}
	else
	{ %>
<div class="ban01" style="background-image: url(http://sf.panli.com/FrontEnd/images20090801/login/banner/login.jpg);">
</div>
<%} %>

// regist

<%if (DateTime.Now > new DateTime(2015, 10, 20, 0, 0, 0) && DateTime.Now < new DateTime(2015, 12, 12, 23, 59, 59))
	{ %> 
<div class="ban01" style="background-image: url(http://sf.panli.com/Ued/Special/20151203/build/images/20151212.jpg);">
</div>
<%}
	else
	{ %>
<div class="ban01" style="background-image: url(http://sf.panli.com/FrontEnd/images20090801/login/banner/login.jpg);">
</div>
<%} %>
```

---

## 2015年12月7日14:06:34
>双12 排行榜


### 签入文件

1. http://localhost:45419/Panli.Site.Static/Ued/Special/20151203/  新建目录
2. http://localhost:1731/oldsite/Special/taobao20151212_H5.aspx
3. http://localhost:1731/oldsite/Special/taobao20151212.aspx

### demo

pc 

http://panli.mu.gg/special/20151203/

h5 

http://panli.mu.gg/special/20151203h5/



---

