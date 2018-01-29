---
layout: post
title: duet display
category: 应用笔记
keywords: 应用笔记,duet
---

## 使用效果

![](https://moetu.fastmirror.org/images/2018/01/28/9676FFD92D8F845A2FB562B608AAE0C5a911d6e5d92c34bf.png)

## 安装
duet需要mac和iOS两个客户端
mac端免费，iOS端原价128

安装了两个客户端，并打开后,用USB连接之后，就会在iOS设备上，显示一个mac的桌面

## 配置
mac端可以设置外接屏幕的相对位置，是否显示iPad TouchBar。
iPad TouchBar 可以在iPad上对应当前应用做一些操作，形式与mac的touchBar相似

## 定位
这个软件其实就是适合把，iPad屏幕作为一个资料展示器，在上面并不适合做复杂的操作

## 使用感受
iPad作为mac的扩展屏幕。逻辑其实是一对一的，意思是当mac上有两屏内容时，iPad其实也是对应的两屏，mac切换屏幕时，iPad也会对应的切换。

可以理解为iPad是对当前mac屏幕的一个扩展。

但由于iPad上面触控使用鼠标，体验并不好，如果需要滑动界面还是要借助电脑的触控版

## 原理
Duet Display 并非通过纯粹的「屏幕拓展」来实现，而是依靠 Mac 端的视频压缩技术，将当前画面传输到 iOS 端显示

需要设备有较强性能

**PeerTalk** :
USB基座和TCP协议，实现iOS和Mac间通讯的Cocoa库
通过数据线输出视频
可以在热拔插状态下，实现自动断开和连接
mac客户端使用该技术去同步视频画面

**CocoaSplit**:
一种视频流媒体技术的服务

**GPUImage**
实时滤镜的开源库

## 相关网页

[官网](https://www.duetdisplay.com/)

[一秒把平板变 PC 电脑的扩展屏幕：TwomonUSB & Duet Display 对比评测 - 少数派](https://sspai.com/post/29016)

[一秒把 iPad 变成 Mac 的第二块屏幕：Duet Display - 少数派](https://sspai.com/post/27758)

[一款刚上架的屏幕拓展应用为何迅速走红？浅谈 Duet Display 背后的技术 - 少数派](https://sspai.com/post/27806)
