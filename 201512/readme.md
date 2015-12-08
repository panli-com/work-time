## 一个工作提交日志 12月份

## 2015年12月8日10:50:22

> 头部logo倒数计时

### 签入文件

1. PanliTuanO\Panli.Site.TuanO\Views\Shared\_Head.cshtml
2. PanliTuanO\Panli.TuanO.Business\Extension\TuanBusinessExtension.cs
3. Panli.Site.Static/Ued/Pc/header/20151203/  新建文件夹
4. oldsite/master/NewMain.master
5. oldsite/master/NewsMain.master

### demo





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

