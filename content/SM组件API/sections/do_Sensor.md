---
title: do_Sensor 组件
---

### do_Sensor 组件

 支持平台: iOS,Android 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/do_Sensor)
 用于感应、检测设备周边的信息不同类型的传感器, 检测的信息也不一样，返回手机设备多种传感器的监测值。可监测以下几种传感器：1、加速度传感器；2、罗盘（磁力传感器）；3、转角（设备在空间中的姿势，在3轴的旋转角度，遵循右手原则）；4、陀螺仪；5、距离传感器。Windows平台不支持

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getSensorData](#getSensorData)| 获取传感器数值
<font color ='#0092db'>同步方法</font>  |[start](#start)| 开始从传感器采集数据
<font color ='#0092db'>同步方法</font>  |[stop](#stop)| 停止从传感器采集数据
<font color ='#e96900'>事件</font>  |[change](#change)| 传感器变化触发

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getSensorData><font color ='#0092db'>**getSensorData**</font></span>: 获取传感器数值

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sensorType** |<font color ='#808000'>**number**</font> | 是 | |传感器类型：1、加速度传感器；2、罗盘；3、转角；4、陀螺仪；5、距离传感器
- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 格式同change事件
- 说明: 根据传入的传感器类型，获取相应传感器数值
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=start><font color ='#0092db'>**start**</font></span>: 开始从传感器采集数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sensorType** |<font color ='#808000'>**number**</font> | 是 | |传感器类型：1、加速度传感器；2、罗盘；3、转角；4、陀螺仪；5、距离传感器。
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 手动开始某一种传感器
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=stop><font color ='#0092db'>**stop**</font></span>: 停止从传感器采集数据

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **sensorType** |<font color ='#808000'>**number**</font> | 是 | |传感器类型：1、加速度传感器；2、罗盘；3、转角；4、陀螺仪；5、距离传感器。
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: 
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=change><font color ='#e96900'>**change**</font></span>: 传感器变化触发

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: 1、加速度{sensorType:'1',data:{x:'沿x轴加速度值’,y:’沿y轴加速度值’,z:’沿z轴加速度值’}};2、罗盘（磁力传感器，特斯拉为磁力感应单位，表示垂直穿过单位面积的磁力线的多少）{sensorType:'2',data:{x:'x轴微特斯拉值’,y:’y轴微特斯拉值’,z:’z轴微特斯拉值’}}；3、转角，返回角度值{sensorType:'3',data:{x:'绕x轴旋转的角度’,y:’绕y轴旋转的角度’,z:’绕z轴旋转的角度’}}；4、陀螺仪，返回3轴角速度值 单位：弧度/秒{sensorType:'4',data:{x:'绕x轴旋转的角速度’,y:’绕y轴旋转的角速度’,z:’绕z轴旋转的角速度’}}；5、距离传感器,没有3轴的返回值，只是一个事件调用{sensorType:'5',data:{x:'’,y:’’,z:’’}}
- 说明: 传感器变化触发
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


