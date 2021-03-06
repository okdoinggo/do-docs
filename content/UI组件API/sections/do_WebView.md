---
title: do_WebView 组件
---

### do_WebView 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_WebView)
 可以加载html网页，同时在网页中可以使用DeviceOne提供的js SDK实现跨webview的交互

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#42b983'>属性</font>  |[enabled](#enabled)| 控制WebView是否可以获取输入框焦点
<font color ='#42b983'>属性</font>  |[bounces](#bounces)| 反弹效果
<font color ='#42b983'>属性</font>  |[cacheType](#cacheType)| 缓存类型
<font color ='#42b983'>属性</font>  |[allowDeviceOne](#allowDeviceOne)| 是否加载DeviceOne函数
<font color ='#42b983'>属性</font>  |[isShowLoadingProgress](#isShowLoadingProgress)| 是否显示进度条
<font color ='#42b983'>属性</font>  |[isHeaderVisible](#isHeaderVisible)| 是否显示headerview
<font color ='#42b983'>属性</font>  |[url](#url)| 网页地址
<font color ='#42b983'>属性</font>  |[headerView](#headerView)| 表头视图
<font color ='#42b983'>属性</font>  |[zoom](#zoom)| 手势缩放
<font color ='#42b983'>属性</font>  |[userAgent](#userAgent)| 浏览器标识
<font color ='#42b983'>属性</font>  |[allowVideoFullScreenPlayback](#allowVideoFullScreenPlayback)| HTML中的视频是否自动全屏播放
<font color ='#0092db'>同步方法</font>  |[back](#back)| 回退
<font color ='#0092db'>同步方法</font>  |[forward](#forward)| 前进
<font color ='#0092db'>同步方法</font>  |[reload](#reload)| 重新加载
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止刷新
<font color ='#0092db'>同步方法</font>  |[canForward](#canForward)| 是否可继续前进
<font color ='#0092db'>同步方法</font>  |[canBack](#canBack)| 是否可后退
<font color ='#0092db'>同步方法</font>  |[rebound](#rebound)| headerview复位
<font color ='#0092db'>同步方法</font>  |[setCookie](#setCookie)| 设置cookie
<font color ='#0092db'>同步方法</font>  |[setLoadingProgressColor](#setLoadingProgressColor)| 设置顶部进度条颜色
<font color ='#0092db'>同步方法</font>  |[setDefaultEncodingURL](#setDefaultEncodingURL)| 设置默认转码
<font color ='#0092db'>同步方法</font>  |[getContentSize](#getContentSize)| 获取加载页面内容尺寸
<font color ='#0092db'>异步方法</font>  |[loadString](#loadString)| 加载html字符串
<font color ='#0092db'>异步方法</font>  |[eval](#eval)| 执行JavaScript函数
<font color ='#e96900'>事件</font>  |[loaded](#loaded)| 加载结束事件
<font color ='#e96900'>事件</font>  |[start](#start)| 开始加载
<font color ='#e96900'>事件</font>  |[pull](#pull)| 下拉headerview事件
<font color ='#e96900'>事件</font>  |[failed](#failed)| 加载错误事件

#### <font color ='#40A977'>**1.**</font> 属性

>###### <span id=enabled><font color ='#42b983'>**enabled**</font></span>: 控制WebView是否可以获取输入框焦点

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 为true时可以获取焦点，false的时候无法获取焦点，仅支持Android平台

>###### <span id=bounces><font color ='#42b983'>**bounces**</font></span>: 反弹效果

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 只支持iOS平台，为false时没有上拉下拉的反弹效果

>###### <span id=cacheType><font color ='#42b983'>**cacheType**</font></span>: 缓存类型

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 : no_cache
- 说明 : 改变WebView的缓存方式，缺省值为no_cache表示不使用缓存；为normal时根据cache-control决定是否获取新数据；windows平台不支持

>###### <span id=allowDeviceOne><font color ='#42b983'>**allowDeviceOne**</font></span>: 是否加载DeviceOne函数

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : true
- 说明 : 若想要WebView可以调用DeviceOne的函数，必须将该属性值设置为true，且在该页面的中将代码加到一个特定的函数window.onDeviceOneLoaded = function(){ //do something }方可

>###### <span id=isShowLoadingProgress><font color ='#42b983'>**isShowLoadingProgress**</font></span>: 是否显示进度条

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : webview的顶部有一个绿色进度条，显示加载网页的进度，缺省false不显示

>###### <span id=isHeaderVisible><font color ='#42b983'>**isHeaderVisible**</font></span>: 是否显示headerview

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 缺省false不显示

>###### <span id=url><font color ='#42b983'>**url**</font></span>: 网页地址

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 支持http://,https://,支持source://,data://文件格式。文件格式的说明可以参考Storage类,ios的url里不能有#号或其他特殊服务，如果有需要转码


>###### <span id=headerView><font color ='#42b983'>**headerView**</font></span>: 表头视图

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置要显示的表头视图地址，不填但isHeaderVisible为true时有缺省样式

>###### <span id=zoom><font color ='#42b983'>**zoom**</font></span>: 手势缩放

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 设置webview是否支持手势缩小放大，设置为true时支持

>###### <span id=userAgent><font color ='#42b983'>**userAgent**</font></span>: 浏览器标识

- 数据类型 : <font color ='#808000'>**string**</font>
- 默认值 :
- 说明 : 设置浏览器的User-Agent

>###### <span id=allowVideoFullScreenPlayback><font color ='#42b983'>**allowVideoFullScreenPlayback**</font></span>: HTML中的视频是否自动全屏播放

- 数据类型 : <font color ='#808000'>**boolean**</font>
- 默认值 : false
- 说明 : 为true时则播放HTML页面中视频时自动全屏，为false时则在播放的时候不改变原有视频窗口大小

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=back><font color ='#0092db'>**back**</font></span>: 回退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 回退到上一个页面
- 示例:

  ```javascript
  do_WebView.back()

  ```

[回到顶部](#top)

>##### <span id=forward><font color ='#0092db'>**forward**</font></span>: 前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 前进到下一个页面
- 示例:

  ```javascript
  do_WebView.forward()

  ```

[回到顶部](#top)

>##### <span id=reload><font color ='#0092db'>**reload**</font></span>: 重新加载

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 重新加载页面
- 示例:

  ```javascript
  do_WebView.reload()

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止刷新

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 停止刷新页面
- 示例:

  ```javascript
  do_WebView.stop()

  ```

[回到顶部](#top)

>##### <span id=canForward><font color ='#0092db'>**canForward**</font></span>: 是否可继续前进

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回是否可继续前进
- 说明: 判断页面是否能前进到下一页面
- 示例:

  ```javascript
  var CanForward = do_WebView.canForward()
  deviceone.print(CanForward,"是否可以继续前进")

  ```

[回到顶部](#top)

>##### <span id=canBack><font color ='#0092db'>**canBack**</font></span>: 是否可后退

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 检查是否有可以后退的历史记录
- 说明: 判断页面是否可以后退
- 示例:

  ```javascript
  var CanBack = do_WebView.canBack()
  deviceone.print(CanBack,"是否可以回退")

  ```

[回到顶部](#top)

>##### <span id=rebound><font color ='#0092db'>**rebound**</font></span>: headerview复位

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: headerview复位
- 示例:

  ```javascript
  do_WebView.rebound()

  ```

[回到顶部](#top)

>##### <span id=setCookie><font color ='#0092db'>**setCookie**</font></span>: 设置cookie

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **url** |<font color ='#808000'>**string**</font> | 是 | |如果webview加载该域名地址，会自动把cookie传给服务器
  **value** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置浏览器的cookie
- 示例:

  ```javascript
  do_WebView.setCookie({
    url:url,
    value:cookie
  });

  ```

[回到顶部](#top)

>##### <span id=setLoadingProgressColor><font color ='#0092db'>**setLoadingProgressColor**</font></span>: 设置顶部进度条颜色

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **color** |<font color ='#808000'>**string**</font> | 是 | |颜色值格式为：8位16进制字符，前6位是RGB颜色值，后两位是透明度（Alpha），例如：000000FF
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置加载html页面时，组件顶部进度条的颜色
- 示例:

  ```javascript
  do_WebView.setLoadingProgressColor("000000FF")

  ```

[回到顶部](#top)

>##### <span id=setDefaultEncodingURL><font color ='#0092db'>**setDefaultEncodingURL**</font></span>: 设置默认转码

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **isEncode** |<font color ='#808000'>**Boolean**</font> | 否 | true|默认按照utf-8编码方式转码，设置为false则不对原url进行处理
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 设置是否对url默认按照utf-8编码格式转码，仅支持iOS平台
- 示例:

  ```javascript
  do_WebView.setDefaultEncodingURL(true)

  ```

[回到顶部](#top)

>##### <span id=getContentSize><font color ='#0092db'>**getContentSize**</font></span>: 获取加载页面内容尺寸

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{width,height}
- 说明: 获取当前加载页面真实内容的宽高，windows平台不支持
- 示例:

  ```javascript
  var size = do_WebView.getContentSize()
  deviceone.print(JSON.stringify(size),"网页加载尺寸")

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=loadString><font color ='#0092db'>**loadString**</font></span>: 加载html字符串

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **text** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明:
- 示例:

  ```javascript
  var htmlString = "<a href=\"http://www.deviceone.net\">Visit DeviceOne</a>";
  do_WebView.loadString({text:htmlString}, function(data, e) {
	  devceone.print(data,"加载结果")
  })

  ```

[回到顶部](#top)

>##### <span id=eval><font color ='#0092db'>**eval**</font></span>: 执行JavaScript函数

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **code** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 无
- 说明: 在WebView页面执行一段Javascript代码，并返回值；Android平台仅支持单语句执行
- 示例:

  ```javascript
  //加载的html网页有function getbtn(val){}
  do_WebView.url="source://view/do_WebView/abc.html";
  //通过执行Javascript代码对网页中方法进行调用
  do_WebView.eval({code:"getbtn('evaltest')"}, function(data, e) {
	  deviceone.print(data,"加载结果")
  })


  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=loaded><font color ='#e96900'>**loaded**</font></span>: 加载结束事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径
- 说明: 加载结束事件
- 示例:

  ```javascript
  do_WebView.on("loaded",function(data){
	  deviceone.print(data,"加载完成返回")
  })

  ```

[回到顶部](#top)

>###### <span id=start><font color ='#e96900'>**start**</font></span>: 开始加载

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{url}，其中url表示当前操作的url地址，该地址不一定为网络地址，本地html页面跳转也会触发并返回本地路径,因平台限制ios无法在start事件中拿到准确地址
- 说明: 开始加载
- 示例:

  ```javascript
  do_WebView.on("start",function(data){
	  deviceone.print(data)
  }

  ```

[回到顶部](#top)

>###### <span id=pull><font color ='#e96900'>**pull**</font></span>: 下拉headerview事件

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 返回{state,offset}，其中state表示headerview的状态，offset为headerview下拉的位移量；其中state=0：表示开始下拉headerview，在headerview下拉到headerview复位整个过程中，pull事件会触发很多次；state=1：表示下拉headerview超过headerview的高度，触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui；state=2：下拉超过一定值，触发state=1事件后，松手会触发一次这个事件，前端开发者接受到这个事件会更新headerview的ui，然后开始加载数据，数据加载完后需要调用rebound方法让header复位
- 说明: 下拉headerview事件
- 示例:

  ```javascript
  do_WebView.on("pull",function(data){
	   deviceone.print("state属性:"+data.state+"offset属性"+data.offset)
  })

  ```

[回到顶部](#top)

>###### <span id=failed><font color ='#e96900'>**failed**</font></span>: 加载错误事件

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 加载网页失败或加载一个错误的或者不存在的网页时触发，返回错误信息
- 说明: 加载错误事件
- 示例:

  ```javascript
  do_WebView.on("failed",function(data){
	  deviceone.print(data,"加载失败回调")
  })

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**5.**</font> 常见问题
- 安卓下webview加载的页面,点击输入框,页面如何自动上跳?

  **答**: 可以将webview高度设置成自动(-1),或者将页面根ui换为webview.


[回到顶部](#top)
