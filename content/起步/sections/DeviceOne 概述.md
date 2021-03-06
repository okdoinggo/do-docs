---
title: DeviceOne 概述
---
### DeviceOne 概述

#### 一. DeviceOne是什么?

DeviceOne(以下简称**Do**)是一个移动开发的平台或技术，与之对等的是Android移动开发技术，iOS移动开发技术，Windows移动开发技术。我们可以从下面的表里看出他们之间的关联和区别.

  | 开发环境 | IDE |开发语言|SDK|生成安装包
-----|---------|-----|-------|---|----|---------
**Android** |Windows/MAC|Eclipse/Android Studio | Java|Android SDK|apk安装包
**iOS** |MAC|XCode | ObjectC/Swift|iOS SDK|ipa安装包
**Windows** |Windows|Visual Studio | C#|Windows SDK|appx安装包
**DeviceOne** |Windows/MAC|Do Studio | JavaScript/lua|DeviceOne SDK|apk,ipa和appx安装包

从这个表我们可以了解**Do**的特点:

1.  移动App开发过程的所有阶段**Do**都介入：编码—调试—编译—测试—发布。在任何一个环节都有对应的产品和服务来对应。
2.  使用**Do**开发App完全不需要了解其它三种技术的技术细节,也不需要搭建开发环境.
3.  使用**Do**开发需要了解**Do**的基本框架和API
4.  使用**Do**能做到一次开发，多平台发布，`Write Once，Run Anywhere`
5.  使用**Do**开发App需要云编译，需要联网。
6.  使用**Do**开发使用JavaScript/Lua，相对于其它开发语言，使用更简单，更易理解
7.  **Do**平台具有自己的JS/Lua SDK，目前有100多个组件，每个组件都有2-3个平台的原生实现。组件还在不断扩展中。这个组件可以由官方来开发，也可以由任何有原生开发能力的开发者开发并分享。
8.  **Do**平台只是移动端开发平台，并没有提供服务端开发的任何服务和技术。

#### 二. 为什么有DeviceOne技术?
既然不同的移动操作系统有不同的开发技术，为什么还需要**Do**？**Do**是解决原生开发的二个重要问题：

1.  相同的业务逻辑需要在 iOS 和 Android 平台各实现一次，多套人，多套代码带来的开发，维护以及交流的效率和成本。除了开发成本高，也会引入体验的细微差别。是否有一种技术方案可以做到一份代码，两个平台运行，行为相同
2.  移动 APP 开发领域，要极致体验发布就不灵活（Native），要灵活发布就没有极致体验（H5）。有没有一种技术方案可以兼顾极致的体验和灵活的发布？
**Do**能很好的解决这二个问题。

#### 三. DeviceOne的优点?
1. 不同于其它跨平台技术以H5为基础,**Do**从ui到功能所有都是对应原生的实现,比如do_Button组件运行在Android下对应的是Button类,在iOS下对应是UIButton类. 从而确保跨平台而不牺牲体验.
2. **Do**的ui搭建可以通过所见即所得的方式在我们提供的IDE上可视化拖拽生成,方便而且精准.
3. **Do**的ui构建能做到一次开发,多平台多屏幕适配.
4. 用**Do**开发的js源码可以自己加密成二进制文件,而不是简单的混淆,确保安全性
5. 用**Do**开发很容易实现热升级,而且[不会被Apple商店限制](http://bbs.deviceone.net/forum.php?mod=viewthread&tid=1659)

#### 四. DeviceOne开发和原生开发的关系?
**Do**并没有脱离原生开发，只不过把原生开发和App开发者分离了，原生开发者只负责开发和业务无关的组件，比如Button，VideoView之类的。而App开发者不需要理解操作系统的差异，只需要参考组件的一套JS／Lua的API，然后专心整理自己App的业务需求，就能搭建出跨平台的App。

**Do**构建的平台也是积累和沉淀原生开发人员的技术的一种方式，而且是比代码级别更高级别的组件重用，我们提供了一个标准的平台，让原生开发者可以封装积累自己的技术，我们的平台会保证质量。
而且原生开发者在我们的平台上销售自己的组件，App开发者购买使用组件开发App，从而促进一个完整的生态圈的发展。
组件扩展的基本过程就是：

1.   我们提供的组件开发管理界面上创建组件，定义属性，事件，方法
2.   定义完后，可以下载我们自动生成的原生Android, iOS项目，很多代码已经自动生成
3.   开发者在这个项目里添加真正功能实现的原生代码，编译成jar包或者a文件
4.   上传jar包和a文件到我们的平台，然后自己开发App使用或者分享到组件商店给所有App开发者使用

#### 五. 如何学习DeviceOne?
**Do**是使用js语言来开发，需要开发者对js有所了解。
但是**Do**的框架是基于Android，iOS开发的抽象和封装,开发的App绝大部分功能都是由封装的原生组件来实现的，js基本上只是用来编写逻辑，所以开发者并不需要非常熟悉js语言。有类似Java，C#开发经验的开发者很容易上手。

官方提供了多个渠道来帮助你快速入门和掌握这项技术:
[文档](http://document.deviceone.net)
[视频](http://video.deviceone.net)
[论坛](http://bbs.deviceone.net)
QQ官方群（365443130）
[示例中心](http://source.deviceone.net)
[示例Github开源](https://github.com/do-project)
[Android组件Github开源](https://github.com/do-android)
[iOS组件Github开源](https://github.com/do-ios) 

