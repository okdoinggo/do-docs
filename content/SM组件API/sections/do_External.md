---
title: do_External 组件
---

### do_External 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_External)
 启动外部应用或系统的一些应用，比如浏览器，短信等

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[openSystemSetting](#openSystemSetting)| 打开系统设置界面
<font color ='#0092db'>同步方法</font>  |[openApp](#openApp)| 启动第三方应用
<font color ='#0092db'>同步方法</font>  |[openURL](#openURL)| 调用系统默认浏览器
<font color ='#0092db'>同步方法</font>  |[openDial](#openDial)| 打开拨号界面
<font color ='#0092db'>同步方法</font>  |[openContact](#openContact)| 打开系统通讯录界面
<font color ='#0092db'>同步方法</font>  |[openMail](#openMail)| 打开发送邮件界面
<font color ='#0092db'>同步方法</font>  |[openSMS](#openSMS)| 打开发送短信界面
<font color ='#0092db'>同步方法</font>  |[bulkSMS](#bulkSMS)| 打开发送短信界面，支持群发短信
<font color ='#0092db'>同步方法</font>  |[installApp](#installApp)| 安装app
<font color ='#0092db'>同步方法</font>  |[openFile](#openFile)| 打开外部文档
<font color ='#0092db'>同步方法</font>  |[existApp](#existApp)| 应用是否安装

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=openSystemSetting><font color ='#0092db'>**openSystemSetting**</font></span>: 打开系统设置界面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **type** |<font color ='#808000'>**string**</font> | 是 | |目前仅支持“GPS”，表示打开GPS设置界面；iOS仅支持10以下系统
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openApp><font color ='#0092db'>**openApp**</font></span>: 启动第三方应用

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **wakeupid** |<font color ='#808000'>**string**</font> | 是 | |其他应用被唤醒的唯一标识。不同的手机操作系统唤醒机制不一样，唤醒id的格式也不一样。我们会有专门的文档介绍
  **data** |<font color ='#808000'>**object**</font> | 否 | |打开其他应用可以传递一些数据，数据的格式是JSON的键值对
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 返回true或false
- 说明: 如果唤醒id对应的应用不存在，返回失败。详细文档，请参考http://bbs.deviceone.net/forum.php?mod=viewthread&tid=224
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openURL><font color ='#0092db'>**openURL**</font></span>: 调用系统默认浏览器

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **url** |<font color ='#808000'>**string**</font> | 是 | |要访问的url地址
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 该方法可调用移动设备系统自带的浏览器打开指定的url
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openDial><font color ='#0092db'>**openDial**</font></span>: 打开拨号界面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **number** |<font color ='#808000'>**string**</font> | 是 | |拨号界面显示的号码
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 直接打开系统拨号界面
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openContact><font color ='#0092db'>**openContact**</font></span>: 打开系统通讯录界面

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: iOS平台8.0以下不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openMail><font color ='#0092db'>**openMail**</font></span>: 打开发送邮件界面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **to** |<font color ='#808000'>**string**</font> | 是 | |
  **subject** |<font color ='#808000'>**string**</font> | 否 | |邮件标题
  **body** |<font color ='#808000'>**string**</font> | 否 | |邮件正文
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openSMS><font color ='#0092db'>**openSMS**</font></span>: 打开发送短信界面

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **number** |<font color ='#808000'>**string**</font> | 是 | |手机号
  **body** |<font color ='#808000'>**string**</font> | 否 | |内容
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=bulkSMS><font color ='#0092db'>**bulkSMS**</font></span>: 打开发送短信界面，支持群发短信

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **number** |<font color ='#808000'>**object**</font> | 是 | |手机号，为JSON Array格式，如['10086','138xxx']
  **body** |<font color ='#808000'>**string**</font> | 否 | |内容
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: null
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=installApp><font color ='#0092db'>**installApp**</font></span>: 安装app

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只支持data://目录
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 执行这个方法会打开系统的安装界面安装data://目录下的一个apk文件，仅支持android平台
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=openFile><font color ='#0092db'>**openFile**</font></span>: 打开外部文档

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **path** |<font color ='#808000'>**string**</font> | 是 | |只支持data://目录
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: android需要先在手机上安装打开相应文件的第三方软件
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=existApp><font color ='#0092db'>**existApp**</font></span>: 应用是否安装

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **key** |<font color ='#808000'>**string**</font> | 是 | |iOS平台该值为应用的URL scheme值，Android平台该值为应用的包名，需区分对待
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 安装了返回true，没安装返回false
- 说明: 判断当前设备上是否安装了某一应用，windows平台不支持
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件


