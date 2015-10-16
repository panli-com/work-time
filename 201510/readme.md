## 一个工作提交日志 10月份

### 2015年10月16日17:41:27
需求文档 ：[https://www.zybuluo.com/jean/note/191545#二充值送双11红包](https://www.zybuluo.com/jean/note/191545#二充值送双11红包)
>充值送双11红包

![](./images/2015-10-16_173819.png)

签入
>http://localhost:58251/oldsite/mypanli/Account/pay.aspx
#### coding
> style

```
.red{
  color:Red;
}
.two11{
  border:1px solid #d9d9d9;
  background:#fffde0;
  padding: 5px 10px;
  margin-bottom:14px;
  position:relative;
}
.two11 p{
  line-height:24px;
  color:#caa13f;
}
.two11 a{
  color:#73a9cd;
  top:10px;
  position:absolute;
  right:10px;
}
.two11 a:hover{
  text-decoration: none;
}
```
> html

```
<%-- 这部分的提示文字于 11月3日0点自动上线，11月9日23:59:59自动下线。。--%>
  <%if ((DateTime.Now > new DateTime(2015, 11, 3, 0, 0, 0) && DateTime.Now < new DateTime(2015, 11, 9, 23, 59, 59)))
{ %>
    <div class="two11">
        <span class="red">
        双11攒钱行动开始啦！
        </span>
        <p>
        北京时间 2015.11.3-11.9 期间, 单笔充值到账金额满 <span class="red">100元</span>, 就可获得 <span class="red">10元</span> 双11红包(<span class="red">每人 1 次</span>)。

         <a href="http://www.panli.com/Special/hongbao_201510.aspx" target="_blank">了解详情>></a>
        </p>           
    </div>        
<%} %>
```

### 2015年10月16日09:38:09
> 双11 H5页面

[http://ps.mu.gg/20151015h5/](http://ps.mu.gg/20151015h5/)

![](./images/2015-10-16_094557.png)

签入
>http://localhost:58251/oldsite/Special/hongbao_201511_m.aspx
>http://localhost:45419/Panli.Site.Static/Ued/Special/20151015h5/


### 2015年10月15日09:22:16
>双十一 滚动

![](./images/20151015.gif)

签入
>http://localhost:45419/Panli.Site.Static/Ued/Special/20151014/js/main.min.js
>http://localhost:45419/Panli.Site.Static/Ued/Special/20151014/main.min.css
>http://localhost:58251/oldsite/Special/hongbao_201511.aspx


### 2015年10月14日10:28:02

最后1天的弹框图片请查收附件，是10月15日0:00—10月16日0:00弹的

提交签入
>http://localhost:45419/Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js
>http://localhost:45419/Panli.Site.Static/Ued/images/20150927/

![](./images/20151014/doing_006.png)

```
//最后1天的弹框，是10月15日0:00—10月16日0:00弹的
  new bannerSpecial('Special13', new Date(2015, 9, 10, 15,8), new Date(2015, 9, 16,8), new Date(date), function () {
      var Special10 = $('<div class="Special10" style="width:672px; height:480px; background:url(http://sf.panli.com/Ued/images/20150927/doing_006.png); position:fixed; left:50%; top:50%; margin-left:-336px; margin-top:-240px; z-index:9999;"><a href="javascript:;" class="SpecialClose" style="display:block; width:60px; height:60px; position:absolute; right:-9px; top:169px;z-index:12;"></a><a href="http://www.panli.com/Special/sale_201510.aspx" style="display:block; width:672px; height:480px; position:absolute; left:0px; bottom:0px;z-index:10;"></a></div>');
      $('body').prepend(Special10);
      Panli.Overlay.open();
      Special10.find('.SpecialClose').click(function () {
          Panli.Overlay.close();
          Special10.remove();
          return false;
      });
  });
```


### 2015年10月13日10:22:29

双11 这两部分的提示文字于 10月20日0点自动上线，10月27日23:59:59自动下线。

红色画圈为新增部分

http://www.panli.com/mypanli/OrderCart.aspx

![](./images/20151013/2015-10-13_102706.png)


http://www.panli.com/mypanli/DeliverType/OrderSuccess.aspx?t=1
![](./images/20151013/2015-10-13_102725.png)

提交签入
>http://www.panli.com/mypanli/DeliverType/OrderSuccess.aspx?t=1
>http://www.panli.com/mypanli/OrderCart.aspx

#### 需要后台修改
>红包金额(图中XX.XX元) = 实际支付 的，不含报关费 的 国际运费的5%

![](./images/20151013/2015-10-13_103602.png)

```
<%-- 双11 这两部分的提示文字于 10月20日0点自动上线，10月27日23:59:59自动下线。--%>
 <%if ((DateTime.Now > new DateTime(2015, 10, 20, 0, 0, 0) && DateTime.Now < new DateTime(2015, 10, 27, 23, 59, 59)))
{ %>
<p class="two11 red">
     恭喜您获得XX.XX元双11红包！想获得更多红包？<a href="http://www.panli.com/Special/hongbao_201510.aspx" target="_blank">点此了解>></a>
</p>
<%} %>
```

### 2015年10月9日13:11:02

定时10月10日10:00—10月15日0:00，有弹出蒙版宣传页。活动期间用户每天打开首页，只弹1次。
弹出框链接：http://www.panli.com/Special/sale_201510.aspx  （记得做成整个弹窗图片都可以链接到活动页）

![弹出图片](./images/20151009/doing_005.png)

提交签入
>http://localhost:45419/Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js
>http://localhost:45419/Panli.Site.Static/Ued/images/20150927/
