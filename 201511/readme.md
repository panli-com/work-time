## 一个工作提交日志 11月份


## 2015年11月5日13:34:37
> 运费弹出提示

### 签入文件

1. http://localhost:58251/oldsite/mypanli/DeliverType/ValidateProducts.aspx


### 文件说明

/oldsite/mypanli/DeliverType/ValidateProducts.aspx
> 依赖库 需引入 panli.min.js 库

![](./images/20151105/weg.gif)


##### addCode

```
<style type="text/css">
    #TotalWeight1
    { position:relative;
      top:2px;
        }
    .z-panbi-a
    {
        color:Blue;
        }
</style>
<script type="text/javascript">
    var ProWeight = '<%=TotalWeight1 %>';     
    var textWeight = '含包装重量及50g包裹面单重量';
    if (ProWeight > 1800) {
        textWeight = '含包装重量';
    }
    $("#TotalWeight1").hover(
        function () {
            PL.tips(textWeight, '#TotalWeight1', { tips: 4 })
        },
        function () {
            PL.closeAll();
        }
    );
    
</script>
```


###### yCode
```
<dl class="yusuan">
<dd>
    <%--您本次提交运单的商品包裹重量总计--%>您本次提交运单的商品包裹预估重量：<span><%=TotalWeight %>g<span style="color:#333333">（含预估包装重量）</span></span></dd>
<dt>商品总价值：<b>￥<%=TotalPrice.ToString("0.00") %></b>&nbsp;(可获番币<a
    href="http://service.panli.com/Help/Detail/373.html" target="_blank"><img src="http://sf.panli.com/FrontEnd/images20090801/icon/use/w1.gif"
        alt="番币规则" /></a>)</dt>
</dl>
```


需求文档地址
https://www.zybuluo.com/jean/note/209038

---

## 2015年11月3日 10:34:09

>服务器时间接口 更改 文件较多，#文件说明

### 需要更新获取的文件

1. http://localhost:58251/oldsite/master/NewsMain.master
2. http://localhost:58251/oldsite/master/NewMain.master
3. http://localhost:45419/Panli.Site.Static/Ued/Pc/  
4. http://localhost:45419/Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js
5. http://localhost:45419/Panli.Site.Static/Ued/Pc/common/js/panli.min.js
6. http://localhost:45419/Panli.Site.Static/Ued/Pc/header/
7. http://localhost:45419/Panli.Site.Static/Ued/Pc/index/js/double.js

### 文件说明

oldsite/master/NewMain.master and master/NewsMain.master
> panli 组件版本更新

Panli.Site.Static/Ued/Pc/
> 新增 header 目录 由于 获取服务器时间接口 更改 需要修改 头部咯logo 的倒计时 模块

Panli.Site.Static/FrontEnd/js20090801/NewIndex/topBanner.js
> 首页弹出层 时间接口修改

Panli.Site.Static/Ued/Pc/common/js/panli.min.js
> panli 组件 服务器时间接口修改 新增 getServerTimeStamp(callback) 函数

Panli.Site.Static/Ued/Pc/header/
> 优化的目录结构  修改了 js 的 获取服务器时间接口 此目录需全部上传

Panli.Site.Static/Ued/Pc/index/js/double.js
> 双11 弹出层 时间接口修改



### 学习一点点
[关于服务器时间接口的前端详解](http://panli.mu.gg/2015/11/03/%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%AB%AF%E4%B8%96%E7%95%8C%E6%97%B6%E9%97%B4-UTC-%E8%BD%AC%E6%8D%A2%E5%AE%A2%E6%88%B7%E7%AB%AF%E6%97%B6%E5%8C%BA%E6%97%B6%E9%97%B4/)




#### oldsite/master/NewsMain.master  
```
<asp:ContentPlaceHolder ID="NewHead" runat="Server">
 <meta name="keywords" content="Panli,代购,中国代购,华人代购,代购演 示,填写代购单" />
 <meta name="description" content="Panli" />
</asp:ContentPlaceHolder>
 <!-- panli.min 组件 -->
 <script type="text/javascript" src="http://sf.panli.com/Ued/Pc/common/js/panli.min.js?v=0.0.1"></script>
 <script src="http://sf.panli.com/Ued/Pc/header/20151001/dual.js?v=0.1" type="text/javascript"></script>
 <link type="text/css" rel="Stylesheet" href="http://sf.panli.com/Ued/Pc/header/20151001/dual.css?v=0.1" />
 <!-- double 11 当天倒计时 请在 11当天加载此 double.js -->
  <%if (DateTime.Now > new DateTime(2015, 11, 11, 0, 0, 0) && DateTime.Now < new DateTime(2015, 11, 12, 0, 0, 0))
    { %>
         <script type="text/javascript" src="http://sf.panli.com/Ued/Pc/index/js/double.js?v=0.0.1"></script>
  <% } %>
</head>

```

### Panli.Site.Static/Ued/Pc/index/js/double.js
```
;(function(){
  $(function(){    
    // 获取服务器时间回调
    getServerTimeStamp(function(e){        
        FStardouble(e,'2015/11/11 00:00:00','2015/11/11 23:59:59');
    })   

  });

  // 二次封装 no = 现在时间 ，sta = 开始时间，end = 结束时间
  function FStardouble(no,sta,end){
    var NowDay  = new Date(no),
            NowTime = NowDay.getTime(),
            StaTime = (new Date(sta)).getTime()
            EndTime = (new Date(end)).getTime(),
            NowH    = NowDay.getHours(),    
            dobCookie = get_Cookie('doubleEleven');    

        if(NowTime< StaTime || NowTime > EndTime){
             return;
        }

        if(dobCookie == 2){
            return;
        }
        if(NowH >= 13){
            FndoubleElevenLayer(NowTime,EndTime,2);
            return;
        }
        if(dobCookie == null){
            FndoubleElevenLayer(NowTime,EndTime,1);       
        }    
  }

  function FndoubleElevenLayer(FNowTime,FendTime,cooki){
  //今日结束时间
    var taDayend = getDateEnd(FNowTime);
    set_Cookie('doubleEleven',cooki,taDayend);

  var DayNow = parseInt(FNowTime);
  var DayEnd = parseInt(FendTime);
  var stc = '<div class="i-double-eleven" data="'+ DayEnd +'">'+
            '<span class="double-time-h">00</span>'+
            '<span class="double-time-m">00</span>'+
            '<span class="double-time-s">00</span>'+
            '</div>';
  PL.open({
    type: 1,
    title: false,
    area: ['380px', '372px'],
    closeBtn: true,
    shadeClose: false,
    skin: 'i-double-eleven-wp',
    content: stc
  });

  $("head").append("<style type='text/css'>.i-double-eleven-wp{width:380px;height:372px;background:url(http://sf.panli.com/Ued/Pc/index/images/doing_002.png) center center no-repeat}.i-double-eleven{position:relative;width:380px;height:372px;font-size:33px;color:#ffea00}.layui-layer-close2{filter:alpha(opacity=0);-moz-opacity:0;-khtml-opacity:0;opacity:0}.double-time-h,.double-time-m,.double-time-s{position:absolute;bottom:10px}.double-time-h{left:54px}.double-time-m{left:150px}.double-time-s{left:244px}</style>");

  var doubleElevenLayer = {
    pZ:function(s){
      return s < 10 ? '0' + s: s;
    },
    DId:function(id){
      return document.getElementById(id);
    },
    less:function(n){
      return n < 0 ? '0': n;
    },
    GetRTime:function(){
      var t = parseInt(DayEnd) - parseInt(DayNow);
      var d=Math.floor(t/1000/60/60/24);
      var h=Math.floor(t/1000/60/60%24);
      var m=Math.floor(t/1000/60%60);
      var s=Math.floor(t/1000%60);
      DayNow += 1000;
     //  t < 0 ?  clearInterval(Time) : '';
      if(t < 0){
        d = h = m = s = '0';
        clearInterval(doubleElevenTime);
      }
      $(".double-time-h").html(doubleElevenLayer.pZ(h));
      $(".double-time-m").html(doubleElevenLayer.pZ(m));
      $(".double-time-s").html(doubleElevenLayer.pZ(s));

    }
  }
  var doubleElevenTime = setInterval(function(){
    doubleElevenLayer.GetRTime()
  },1000);
}

})();
```

---

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
