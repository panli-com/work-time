## 一个工作提交日志 11月份


## 2015年11月2日14:16:35

首页弹框 定时11月3日0:00—11月10日0:00


### 需要更新获取的文件

>/Panli.Site.Static/Ued/Pc/index/   --静态文件

>/Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js

>-- --静态文件 首页弹窗 定时11月3日0:00—11月10日0:00

![](images/20151102/doing_003.png)

### code update

```
//定时11月3日0:00—11月10日0:00;
//弹出框链接：  http://www.panli.com/Special/hongbao_201510.aspx
new bannerSpecial('Special13', new Date(2015, 10, 3), new Date(2015, 10, 10), new Date(date), function () {
   var _ImgW = 614,
       _ImgH = 518,
       _closeAR = 84,
       _closeAT = -9,
       _imgSrc = 'http://sf.panli.com/Ued/Pc/index/images/doing_003.png',
       _aHref = 'http://www.panli.com/Special/hongbao_201510.aspx';
   var Special10 = $('<div class="Special10" style="width:' + _ImgW + 'px; height:' + _ImgH + 'px; background:url(' + _imgSrc + '); position:fixed; left:50%; top:50%; margin-left:-' + _ImgW / 2 + 'px; margin-top:-' + _ImgH / 2 + 'px; z-index:9999;"><a href="javascript:;" class="SpecialClose" style="display:block; width:60px; height:60px; position:absolute; right:' + _closeAR + 'px; top:' + _closeAT + 'px;z-index:12;"></a><a href="' + _aHref + '" style="display:block; width:' + _ImgW + 'px; height:' + _ImgH + 'px;  position:absolute; left:0px; bottom:0px;z-index:10;"></a></div>');
   $('body').prepend(Special10);
   Panli.Overlay.open();
   Special10.find('.SpecialClose').click(function () {
       Panli.Overlay.close();
       Special10.remove();
       return false;
   });
});
```


## 2015年11月2日13:34:53

双十一当天 弹出层 倒计时

### demo

[静态演示](http://panli.mu.gg/page/20151030/)

### 需要更新获取的文件

在有首页的 母版 `NewsMain.master` 外，其他页面都继承了 `NewMain.master` 母版 (不包含(ShoppingCart.aspx))

`ShoppingCart.aspx` 是没有继承母版的；需要更新获取

即：在这2个母版中引入 下面更新的代码既可；

>http://localhost:58251/oldsite/master/NewsMain.master

>http://localhost:58251/oldsite/mypanli/Default.aspx          -- ~/master/NewMyPanli.master

>http://localhost:58251/oldsite/mypanli/ShoppingCart.aspx

>http://localhost:58251/oldsite/mypanli/Favorite.aspx         -- ~/master/NewMyPanli.master

>http://localhost:58251/oldsite/mypanli/OrderCart.aspx        -- ~/master/NewMyPanli.master

>http://localhost:58251/oldsite/mypanli/OrderList.aspx        -- ~/master/NewMyPanli.master

>http://localhost:58251/oldsite/Piece/Default.aspx            -- ~/master/NewMain.master

>http://localhost:58251/oldsite/vip/Default.aspx              -- ~/master/NewMain.master

>http://localhost:58251/oldsite/Cowry/Default.aspx            -- ~/master/NewMain.master

>/Panli.Site.Static/Ued/Pc/common/   -- 组件 静态文件

>/Panli.Site.Static/Ued/Pc/index/   --静态文件


### code update

```
<!-- double 11 当天倒计时 请在 11当天加载此 double.js -->
<%if (DateTime.Now > new DateTime(2015, 11, 3, 0, 0, 0) && DateTime.Now < new DateTime(2015, 11, 12, 0, 0, 0))
  { %>
       <script type="text/javascript" src="http://sf.panli.com/Ued/Pc/index/js/double.js?v=0.0.1"></script>
<% } %>
```

---
