---
layout: post
title: universal link 官方文档 阅读笔记
category: iOS笔记
keywords: universal link
---

[App Search Programming Guide: Support Universal Links](https://developer.apple.com/library/content/documentation/General/Conceptual/AppSearch/UniversalLinks.html)

iOS9之后支持配置universal link，iOS9之前点击universal link就直接用浏览器打开链接。

## 需求

用户点击一个链接达到无感跳转到app的效果，不需要经过浏览器。
如果应用没有安装，则直接使用浏览器打开链接。

## 优势

相比schema，Universal links的主要优势
1. 唯一性，别的应用无法注册与你一样的Universal links
2. 保密性，只有你能够设置你的应用与网站的联系
3. 灵活性，没有安装应用的时候，直接用浏览器打开你的链接
4. 私密性，其他应用不需要知道你的应用是否已经安装了，就能与你的应用产生联系

## 配置

1. 创建apple-app-site-association，用JSON描述你的应用能够处理的URL
2. 将apple-app-site-association上次到https服务器根目录下
3. 在app添加处理url的代码



## 编写apple-app-site-association

指定网站要处理的Universal links的路径
```
{
    "applinks": {
        "apps": [],
        "details": [
            {
                "appID": "9JA89QQLNQ.com.apple.wwdc",
                "paths": [ "/wwdc/news/", "/videos/wwdc/2015/*"]
            },
            {
                "appID": "ABCD1234.com.apple.wwdc",
                "paths": [ "*" ]
            }
        ]
    }
}
```

1. 必须包含一个apps的空数组
2. details是一个字典数组，每一个字典对应应该app，系统根据顺序去系统里面寻找应用处理url。
3. appID指的是app中的entitlements注册时对应的“application-identifier”
4. paths对应网站与应用关联的部分
5.  * 代表所有，？代表单个字符

## 应用处理通用链接

1. 添加entitlement，指定应用支持的域名
2. 更新delegate，处理 NSUserActivity 事件
```
 the Associated Domains section in the Capabilities tab
可以添加一份支持的域名列表，such as applinks:www.mywebsite.com.
```

## 其他NSUserActivity

[Shared Web Credentials | Apple Developer Documentation](https://developer.apple.com/documentation/security/shared_web_credentials)
```
如果要支持Handoff and Shared Web Credentials，apple-app-site-association需要签名
```
