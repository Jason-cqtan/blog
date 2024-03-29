---
title: "居家畅连世界方案分享"
date: 2022-07-02T23:40:57+08:00
description: "个人畅连世界方案分享，u know, it means fanqiang。"
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tocFolding: false
tocPosition: inner
tocLevels: ["h2", "h3", "h4"]
keywords:
- 科学上网
- r2s
- 路由器
- 软路由
- 旁路由
categories:
- life
image:
featured_image: "cover/connet_world.webp"
---

### 个人经历

早期接触这个东西是在大学里玩steam，某些游戏想玩外服，那会（2013年左右）叫vpn，下载一个客户端然后连接，速度尚可。
不止于玩游戏，还有和老外聊天，看看YouTube上逗比视频，顺便去注册Facebook啥的，然后那会游戏也还是买，不支持支付宝，又去尝试贝宝，谷歌账号etc。
噢 对了这是我的[steam账号](https://steamcommunity.com/id/93jc)，有机会一起玩:-）

出来工作后寻找某些免费的vpn，现记得有赛风、蓝灯，也有关注新的连接方案，亲身经历[breakwa11](https://twitter.com/breakwa11)大佬被请去喝茶，“删库跑路”。相关报道传送门：[wiki](https://zh.m.wikipedia.org/zh-sg/Shadowsocks)
上有政策下有对策，之后新的协议如雨后春笋般新开发出来，ssr v2ray xray trojan...
各种服务器安装脚本也应有尽有，只需外网vps、域名，傻瓜式一键安装就能用。
这种和传统的vpn不同，vpn是隧道，全部流量都经由一条线路走，而新兴的可选择全局或局部，还可通过规则动态使用。

so 我也去试了，顺便学习些服务器shell脚本相关知识，持有过搬瓦工绝版套餐vps $19.99/年

工作之余我又看剧嘛，我主要看美剧，好奇+找原版无删减就了解到`Netflix`等海外流媒体，要看这个东西，前提是网络质量好，流量够用。
前期我使用vps看的，但是时不时抽风，要去服务器上调试，不麻烦但是有点不爽。而且升级流量很贵的！
存在即合理，机场提供更多节点，价钱相当，也不用自己去维护，为什么不用呢，我就转用机场。

机场上的发展也是与协议同步发展的，早期`ss`再到`ssr`，后面`IPLC`专线、`IEPL`专线。想了解更多看[AK的系列视频](https://www.youtube.com/watch?v=XKZM_AjCUr0&list=PLqybz7NWybwUgR-S6m78tfd-lV4sBvGFG&index=1)


### 概念小解

从原理上看，都是客服端连接服务端，在用户层面更多只需关注客户端。
不同的客户端对协议的支持度不一，有些机场提供自研的客户端
不论是自建还是买机场服务，这里我们默认服务是稳定的，我们只需要设置好客户端连接

### 初级方案

嗯 在需要科学上网的设备上安装客户端，连接即可。
但是如果在电脑上，你电脑连接上了，还是不能打开某些，就算你修改dns也不行，比如Windows系统的应用商店，从网络协议的角度上来讲，并没有连接上，这时需要往网络协议层往下走，让ta连上，才是真的连上。
同理适用ssh客户端也一样，需要ssh这个环境连上才算真的连上，一般会有ssh客户端设置代理的方式解决，相关做开发的小伙伴可能对下面代码有点眼熟。

```sh
# where proxy
proxy () {
  export http_proxy="http://127.0.0.1:7890"
  export https_proxy="https://127.0.0.1:7890"
  echo "HTTP Proxy on"
}

# where noproxy
noproxy () {
  unset http_proxy
  unset https_proxy
  echo "HTTP Proxy off"
}
```

游戏设备（任天堂、switch等）类似，需要设置http代理，如果要连外网的话
你有多个设备且需要连接，就要在每个设备上都装客户端。想想，wifi从路由器发射出来的，要是在路由器上安装一个不就行了嘛。
bingo！

### 捣鼓路由器

在支持安装插件的路由器上安装相关客户端，你需要对路由器进行`刷机`。
有可能你刷不成功。
刷成功了，插件不维护了，机场协议较新，客户端还没适配等问题又来了。
如果配置不好会影响整个wifi系统连接国内会超慢。
当然设置好了，家里的设备都不用打开客户端连接，也不用设置代理，只需连接wifi，其他已连接又没连接的问题也解决了。
对于开发者而言，不用再去设置国内镜像，cnpm、等等，就很爽（前提是梯子质量好）
不过到这里可能劝退一大波人，支持刷机的路由器也不便宜，少则几百+，多则1k+。
还有没有更好的方式，有！

### 捣鼓软路由

在路由器前端的光猫那里动手脚，这里需要一个设备，可大可小，大的可用来做`Nas`，安装硬盘存电影、视频、音乐，居家流媒体方案，感兴趣你可以去搜搜看，烧钱程度不逊于玩单反
小的就单纯用来转发，比如`R2S`、`R4S`、`R5S`。买来刷`固件`，然后在上面使用客户端连接。
大概连接方案就是光猫连接软路由，路由器连接软路由，配置不同的网段，路由器也不用刷机了，便宜的路由器就行。
相比较来说这个是前几个最麻烦的，需要一定的网络基础知识和额外的硬件成本支出，最重要的是你需要有耐心和动力去折腾改善家中的网络状况。
还有吗，有！

### 旁路由

这种我没具体去尝试过，有了解到改变网口连接方式，使用废旧的笔记本或mac mini灵活的配置。更多参考[https://sspai.com/post/59708](https://sspai.com/post/59708)


### 最后

个人最推荐`软路由`，性价比最高，你可以体验各种`固件`，上面的插件相比路由器上丰富很多（非会员解锁网易云会员音乐，京东每日签到得金豆等等）。

使用`openclash`客户端，设置分流简直不要太爽
![alt 个人分流设置](/images/fenliu.jpg "个人分流设置")

当然良好的网络体验还是离不开机场的服务，这里推荐几个我使用过性价比较好的：
- [`tag`](https://tagss.pro/#/register?code=48JZfDYQ) 6年+老牌机场，90+国家节点，满足你各种特殊场景需求，流媒体稳定解锁，缺点贵，要合租联系我
- [`fnf`](https://fnf.one/auth/register?code=WUkO) 节点国家够多，分2种协议（ss、v2ray），还有游戏加速支持，电报每日签到获取更多流量
- [`猫熊网络加速器`](https://mxwljsq.top/auth/register?code=EEzb) 单v2ray用过一段时间，还行。你可以去网站了解其他


