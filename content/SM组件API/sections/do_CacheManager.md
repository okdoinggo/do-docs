---
title: do_CacheManager 组件
---

### do_CacheManager 组件

 支持平台: iOS7.0,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_CacheManager)
 管理应用内缓存，windows平台不支持

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>异步方法</font>  |[getImageCacheSize](#getImageCacheSize)| 获取图片缓存
<font color ='#0092db'>异步方法</font>  |[clearImageCache](#clearImageCache)| 清除图片缓存

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=getImageCacheSize><font color ='#0092db'>**getImageCacheSize**</font></span>: 获取图片缓存

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 返回应用内所有图片缓存的大小总和，单位为k
- 说明: 获取
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=clearImageCache><font color ='#0092db'>**clearImageCache**</font></span>: 清除图片缓存

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**Boolean**</font>
- 返回值描述: 成功返回true，失败返回false
- 说明: 清除应用内所有图片缓存
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件


