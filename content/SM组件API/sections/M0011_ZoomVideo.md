---
title: M0011_ZoomVideo 组件
---

### M0011_ZoomVideo 组件

 支持平台: iOS,Android4.0 以上
 [组件示例](https://github.com/do-api/docs-example/tree/master/source/view/M0011_ZoomVideo)
 集成了zoom的MobileRTC的视频会议组件

#### <font color ='#40A977'>**0.**</font> 目录

     | ID | 说明
---- |------|------|
<font color ='#0092db'>同步方法</font>  |[getMeetingState](#getMeetingState)| 获取会议状态
<font color ='#0092db'>同步方法</font>  |[isMeetingHost](#isMeetingHost)| 是否为会议主持人
<font color ='#0092db'>同步方法</font>  |[isMeetingLocked](#isMeetingLocked)| 会议是否被锁定
<font color ='#0092db'>同步方法</font>  |[isNoMeetingAudio](#isNoMeetingAudio)| 音频不存在
<font color ='#0092db'>同步方法</font>  |[joinMeeting](#joinMeeting)| 加入会议
<font color ='#0092db'>同步方法</font>  |[leaveMeetingWithCmd](#leaveMeetingWithCmd)| 离开会议
<font color ='#0092db'>同步方法</font>  |[logoutRTC](#logoutRTC)| 登出
<font color ='#0092db'>同步方法</font>  |[pauseMeetingAudio](#pauseMeetingAudio)| 暂停／恢复会议音频
<font color ='#0092db'>同步方法</font>  |[startMeeting](#startMeeting)| 开始会议
<font color ='#0092db'>同步方法</font>  |[init](#init)| 初始化组件
<font color ='#0092db'>异步方法</font>  |[loginWithEmailAndPassword](#loginWithEmailAndPassword)| 使用邮箱密码登陆
<font color ='#e96900'>事件</font>  |[MeetingError](#MeetingError)| Designated for Meeting Error message.
<font color ='#e96900'>事件</font>  |[MeetingReturn](#MeetingReturn)| Designated for Meeting Response.
<font color ='#e96900'>事件</font>  |[MeetingStateChange](#MeetingStateChange)| Designated for Meeting State Change.
<font color ='#e96900'>事件</font>  |[MobileRTCAuthReturn](#MobileRTCAuthReturn)| Designated for MobileRTC Auth response.
<font color ='#e96900'>事件</font>  |[MobileRTCLoginReturn](#MobileRTCLoginReturn)| Designated for MobileRTC Login response.
<font color ='#e96900'>事件</font>  |[MobileRTCLogoutReturn](#MobileRTCLogoutReturn)| Designated for MobileRTC Logout response.
<font color ='#e96900'>事件</font>  |[onMeetingReady](#onMeetingReady)| Designated for Meeting has been ready.

#### <font color ='#40A977'>**1.**</font> 属性

#### <font color ='#40A977'>**2.**</font> 同步方法

>##### <span id=getMeetingState><font color ='#0092db'>**getMeetingState**</font></span>: 获取会议状态

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: A MobileRTCMeetingState to tell client the meeting state currently. 
    //Idle
    MobileRTCMeetingState_Idle        = 0,
    //Connecting
    MobileRTCMeetingState_Connecting  = 1,
    //In Meeting
    MobileRTCMeetingState_InMeeting   = 2,
- 说明: This method is used to tell the client whether the meeting is ongoing or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=isMeetingHost><font color ='#0092db'>**isMeetingHost**</font></span>: 是否为会议主持人

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true, the current user is the host of the meeting.
- 说明: This method is used to tell whether the current user is the host of the meeting or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=isMeetingLocked><font color ='#0092db'>**isMeetingLocked**</font></span>: 会议是否被锁定

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true, the meeting has been locked by host.
- 说明: This method is used to tell whether the meeting is locked by host or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=isNoMeetingAudio><font color ='#0092db'>**isNoMeetingAudio**</font></span>: 音频不存在

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: Return true if the meeting audio does not exist.
- 说明: This method is used to tell the client whether the meeting audio existed or not.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=joinMeeting><font color ='#0092db'>**joinMeeting**</font></span>: 加入会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **userName** |<font color ='#808000'>**string**</font> | 是 | |加入会议时显示的用户名
  **meetingPassword** |<font color ='#808000'>**string**</font> | 是 | |会议密码（如果创建时没有设置密码，则随便填写一个都可以加入会议）
  **meetingNumber** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: A MobileRTCMeetError to tell client whether the meeting started or not.    
    //Success
    MobileRTCMeetError_Success                    = 0,
    //Incorrect meeting number
    MobileRTCMeetError_IncorrectMeetingNumber     = 1,
    //Meeting Timeout
    MobileRTCMeetError_MeetingTimeout             = 2,
    //Network Unavailable
    MobileRTCMeetError_NetworkUnavailable         = 3,
    //Client Version Incompatible
    MobileRTCMeetError_MeetingClientIncompatible  = 4,
    //User is Full
    MobileRTCMeetError_UserFull                   = 5,
    //Meeting is over
    MobileRTCMeetError_MeetingOver                = 6,
    //Meeting does not exist
    MobileRTCMeetError_MeetingNotExist            = 7,
    //Meeting has been locked
    MobileRTCMeetError_MeetingLocked              = 8,
    //Meeting Restricted
    MobileRTCMeetError_MeetingRestricted          = 9,
    //JBH Meeting Restricted
    MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
    //Invalid Arguments
    MobileRTCMeetError_InvalidArguments           = 99,
    //Invalid Arguments
    MobileRTCMeetError_InvalidUserType            = 100,
    //Already In another ongoing meeting
    MobileRTCMeetError_InAnotherMeeting           = 101,
    //Unknown error
    MobileRTCMeetError_Unknown                    = 102,
- 说明: This method is used to join a meeting with parameters in a dictionary.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=leaveMeetingWithCmd><font color ='#0092db'>**leaveMeetingWithCmd**</font></span>: 离开会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **cmd** |<font color ='#808000'>**number**</font> | 是 | |Leave meeting by the command type.
- 返回值类型 : <font color ='#808000'>**无**</font>
- 返回值描述: 无
- 说明: This method is used to end/leave an ongoing meeting.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=logoutRTC><font color ='#0092db'>**logoutRTC**</font></span>: 登出

- 参数: **无**
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: return true, if user can logout.
- 说明: Designated for logout MobileRTC.（暂未实现）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=pauseMeetingAudio><font color ='#0092db'>**pauseMeetingAudio**</font></span>: 暂停／恢复会议音频

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **pause** |<font color ='#808000'>**boolean**</font> | 是 | |if true to pause audio; if false to resume audio.
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: 操作是否成功
- 说明: This method is used to pause/resume audio in the meeting.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=startMeeting><font color ='#0092db'>**startMeeting**</font></span>: 开始会议

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **userID** |<font color ='#808000'>**string**</font> | 是 | |
  **userName** |<font color ='#808000'>**string**</font> | 是 | |
  **userToken** |<font color ='#808000'>**string**</font> | 是 | |
  **meetingNumber** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**number**</font>
- 返回值描述: //Success
MobileRTCMeetError_Success                    = 0,
//Incorrect meeting number
MobileRTCMeetError_IncorrectMeetingNumber     = 1,
//Meeting Timeout
MobileRTCMeetError_MeetingTimeout             = 2,
//Network Unavailable
MobileRTCMeetError_NetworkUnavailable         = 3,
//Client Version Incompatible
MobileRTCMeetError_MeetingClientIncompatible  = 4,
//User is Full
MobileRTCMeetError_UserFull                   = 5,
//Meeting is over
MobileRTCMeetError_MeetingOver                = 6,
//Meeting does not exist
MobileRTCMeetError_MeetingNotExist            = 7,
//Meeting has been locked
MobileRTCMeetError_MeetingLocked              = 8,
//Meeting Restricted
MobileRTCMeetError_MeetingRestricted          = 9,
//JBH Meeting Restricted
MobileRTCMeetError_MeetingJBHRestricted       = 10,
    
//Invalid Arguments
MobileRTCMeetError_InvalidArguments           = 99,
//Invalid Arguments
MobileRTCMeetError_InvalidUserType            = 100,
//Already In another ongoing meeting
MobileRTCMeetError_InAnotherMeeting           = 101,
//Unknown error
MobileRTCMeetError_Unknown                    = 102,
- 说明: This method is used to start a meeting with parameters in a dictionary.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>##### <span id=init><font color ='#0092db'>**init**</font></span>: 初始化组件

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **appKey** |<font color ='#808000'>**string**</font> | 是 | |
  **appSecret** |<font color ='#808000'>**string**</font> | 是 | |
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: true成功，false失败
- 说明: 需要在https://zoom.us/developer/ios/credential登录之后，选择iOS或者Android后再选择Credential来查看
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

#### <font color ='#40A977'>**3.**</font> 异步方法

>##### <span id=loginWithEmailAndPassword><font color ='#0092db'>**loginWithEmailAndPassword**</font></span>: 使用邮箱密码登陆

- 参数:

  名称 | 类型 |必填|默认值|说明
  ---- |-------------  |--------------|--------|------
  **email** |<font color ='#808000'>**string**</font> | 是 | |login email account.
  **password** |<font color ='#808000'>**string**</font> | 是 | |login password.
- 返回值类型 : <font color ='#808000'>**boolean**</font>
- 返回值描述: return true, if user can login with work email.目前没有使用场景必须要求登录
- 说明: Designated for login MobileRTC with work email account.（暂未实现）
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


#### <font color ='#40A977'>**4.**</font> 事件

>###### <span id=MeetingError><font color ='#e96900'>**MeetingError**</font></span>: Designated for Meeting Error message.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {error:错误码,message:错误信息}
- 说明: Designated for Meeting Error message.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=MeetingReturn><font color ='#e96900'>**MeetingReturn**</font></span>: Designated for Meeting Response.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {error:错误码,internalError:内部错误码}
- 说明: Designated for Meeting Response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=MeetingStateChange><font color ='#e96900'>**MeetingStateChange**</font></span>: Designated for Meeting State Change.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {state:0},tell client meeting state chagne.
     //Idle
    MobileRTCMeetingState_Idle        = 0,
    //Connecting
    MobileRTCMeetingState_Connecting  = 1,
    //In Meeting
    MobileRTCMeetingState_InMeeting   = 2,
- 说明: Designated for Meeting State Change.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=MobileRTCAuthReturn><font color ='#e96900'>**MobileRTCAuthReturn**</font></span>: Designated for MobileRTC Auth response.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {code:0} //Auth Success 
    MobileRTCAuthError_Success = 0,
    //Key or Secret is empty
    MobileRTCAuthError_KeyOrSecretEmpty = 1,
    //Key or Secret is wrong
    MobileRTCAuthError_KeyOrSecretWrong = 2,
    //Client Account does not support
    MobileRTCAuthError_AccountNotSupport = 3,
    //Client account does not enable SDK
    MobileRTCAuthError_AccountNotEnableSDK = 4,
    //Auth Unknown error
    MobileRTCAuthError_Unknown = 5,
- 说明: Designated for MobileRTC Auth response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=MobileRTCLoginReturn><font color ='#e96900'>**MobileRTCLoginReturn**</font></span>: Designated for MobileRTC Login response.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {code:2} returnValue tell user when the login state changed.
- 说明: Designated for MobileRTC Login response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=MobileRTCLogoutReturn><font color ='#e96900'>**MobileRTCLogoutReturn**</font></span>: Designated for MobileRTC Logout response.

- 返回值类型 : <font color ='#808000'>**object**</font>
- 返回值描述: {code:0}returnValue tell user whether the logout success or not.
- 说明: Designated for MobileRTC Logout response.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)

>###### <span id=onMeetingReady><font color ='#e96900'>**onMeetingReady**</font></span>: Designated for Meeting has been ready.

- 返回值类型 : <font color ='#808000'>**string**</font>
- 返回值描述: 
- 说明: Designated for Meeting has been ready.
- 示例:

  ```javascript
  ...

  ```

[回到顶部](#top)


