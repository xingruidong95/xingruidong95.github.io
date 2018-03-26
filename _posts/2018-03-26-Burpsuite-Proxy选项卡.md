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
>拦截规则配置  
>错误消息自动修复  
>自动更新Content-Length消息头

#### 拦截规则配置
如果intercept request based on the follow rules被选中，则按下方勾选的规则进行拦截。要注意，拦截时对规则的执行是自上而下的。可以通过点击Up和Down按钮对规则的顺序进行调节。  
Operator是指当前规则与其它规则之间的关系，or 或者 and  
Match type是指匹配类型，如域名、IP地址、协议、请求方法、URL等  
Relationship是指此条规则是否匹配Condition中输入的关键字  

#### 错误消息自动修复
如果Automatically fix missing or superfluous new lines at end of request被选中，则表示在消息传输中，Brupsuite会自动修复丢失或多余的新行。  
>一条被修改过的请求消息，如果丢失了头部结束的空行，Brupsuite会自动添加上；如果一次请求的消息体中，URL编码参数中包含任何新的换行，Brupsuite将会移除。此项功能在手工修改请求消息时，为了防止错误，有很好的保护效果。  

#### 自动更新Content-Length消息头
如果Automatically update Content-Length header when the request is edited被选中，则当请求的消息被修改后，Content-Length消息头部也会自动被修改，替换为与之相对应的值。  

### Intercept Server Responses
与Intercept Client Requests功能类似  

### Response Modification
每一个选项分别对应的功能如下：
>显示form表单中隐藏字段  
>高亮显示form表单中隐藏字段  
>使form表单中的disable字段生效，变成可输入域  
>移除输入域长度限制  
>移动JavaScript验证  
>移动所有的JavaScript  
>移除标签  
>转换https超链接为http链接  
>移除所有cookie中的安全标志  
