---
layout: post
title: Brupsuite Proxy选项卡
key: 20180326
tags: Brupsuite
---

关于Brupsuite中Proxy选项卡的各功能介绍
- Intercept
- HTTP history
- WebSockets history
- Options

<!--more-->

## Intercept
该选项卡主要负责Brupsuite Proxy的拦截功能，主要分为以下四个子选项卡
- Forward
- Drop
- Intercept is on
- Action

### Forward
该选项卡的功能为，当你查看过或修改过消息后，点击此按钮，将消息发送至服务器。

### Drop
通过该选项卡，你可以将消息丢弃，使消息不能到达服务器。

### Intercept is on
通过该选项卡来选择是否拦截通过Brupsuite的请求数据，凸起为关闭状态，表示不拦截，凹陷为打开状态，拦截请求。

### Action
可以通过该选项卡将当前拦截到的消息传递到Spider、Scanner、Intruder、 Repeater、Sequencer、Decoder等其他与Proxy同级别的选项卡。
另外还可以做一些请求消息的修改，通过Change request method可以修改消息的请求方式，如GET变为POST。通过Change body encoding可以改变请求body的编码。
Don't intercept requests选项可以对请求消息进行不拦截类型设置，如不拦截此主机/IP地址/文件类型/目录的消息。
Do intercept选项可以针对此消息来拦截其服务器返回的信息。

#### Comment this item/Highlight
对拦截到的消息进行备注及高亮显示

## HTTP history
该选项卡由以下三部分组成
- 过滤器
- 历史记录列表
- 消息详情

### 过滤器
单击Filter处，弹出过滤器界面，该界面分为七个部分
- Filter by request type
  >Show only in-scope item(仅显示当前作用域)  
  >Hide items without responses(仅显示服务器响应)  
  >Show only parameterized request(仅显示带有请求参数的)
- Filter by search term
  >Regex(正则表达式)  
  >Case sensitive(区分大小写)  
  >Negative search(否定搜索)
- Filter by MME type
- Filter by status code
- Filter by file extension
- Filter by annotation 
- Filter by listener

## WebSockets history
>WebSockets history所提供的功能和选项是HTTP history的一个子集，只是因为采用的通信方式的不同，而被独立出来成为一个专门的视图  
>其功能的使用方式与HTTP history雷同

## Options
该选项卡包含以下几个部分：
- Proxy Listeners
- Intercept Client Requests
- Intercept Server Responses
- Intercept WebSockets Messages
- Response Modification
- Match and Replace
- SSL Pass Through
- Miscellaneous

### Intercept Client Requests
