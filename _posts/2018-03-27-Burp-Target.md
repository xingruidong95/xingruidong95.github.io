---
layout: post
title: BurpSuite Target选项卡
key: 20180327
tags: BurpSuite
---

本篇文章主要内容：
- Site map
- Scope
- Target部分工具

<!--more-->

## Site map
该页面由以下几个部分组成：
>Filter  
>访问的URL列表  
>Contents  
>Issues  
### 访问的URL列表
按照网站的层级和深度，树形展示整个应用系统的结构和关联其他域的url情况。

### Contents
某一个url被访问的明细列表，共访问哪些url，请求和应答内容分别是什么，都有着详实的记录。 基于左边的树形结构，我们可以选择某个分支，对指定的路径进行
扫描和抓取（右键单击选中的分支，选择Spider this host/Actively scan this host），也可以通过Add to scope选项将某个域加入Target Scope中。

### Issues
用来显示访问的网站存在的漏洞问题信息。

## Scope
目标域设置，主要使用于以下的几种场景中：
>限制站点地图和Proxy history中的显示结果  
>告诉Burp Proxy 拦截哪些请求  
>Burp Spider抓取哪些内容  
>Burp Scanner自动扫描哪些作用域的安全漏洞  
>在Burp Intruder和Burp Repeater 中指定URL
该页面由两部分组成，一个是Include in scope（包含规则），另一个为Exclude from scope（去除规则）。特别注意的是，出现在Include列表中的规则将会被拦截，
而出现在Exclude列表中的规则允许通过。  
选中Use advanced scope control按钮，则添加规则时，会出现高级选项，可以从协议、主机名/IP地址、端口、文件名4个维度去控制规则。

## Target部分工具
- Compare site maps
- Analyze target

### Compare site maps
主要应用于以下几个场景中：
>同一个帐号，具有不同的权限，比较两次请求结果的差异  
>两个不同的帐号，具有不同的权限，比较两次请求结果的差异  
>两个不同的帐号，具有相同的权限，比较两次请求结果的差异

### Analyze target
该功能位于右键，Engagement tools中，点击后，在弹出的页面中，可以看到有四个标签页，分别为：
- Summary
- Dynamic URLs
- Static URLs
- Parameters
#### Summary
>该视图主要展示当前站点动态URL数量、静态URL数量、参数的总数、唯一的参数名数目，通过这些信息，我们对当前站点的总体状况有粗线条的了解。

#### Dynamic/Static URLs
>该视图展示所有动态的URL请求和应答消息，跟其他的工具类似，当你选中某一条消息时，下方会显示此消息的详细信息。

#### Parameters
>该视图有上中下三部分组成，上部为参数和参数计数统计区，你可以通过参数使用的次数进行排序，对使用频繁的参数进行分析；中部为参数的使用情况列表，
记录参数每一次的使用记录；下部为某一次使用过程中，请求消息和应答消息的详细信息。

## 小结
本篇文章主要记录了一些关于Burp Suite的Target选项卡的相关知识，涉及到的知识点有Site map、Scope、Compare site maps、Analyze target。
>最近在总结Burp Suite的相关知识点，由于之前并不是对Burp Suite很了解，因此借鉴了很多其他的资料，如有不足之处，请见谅啦~
