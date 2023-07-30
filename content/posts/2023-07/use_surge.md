---
title: "使用surge旁路由"
date: 2023-07-30T11:56:04+08:00
description: Surge作为旁路由设置，侵入式与非侵入式区别
draft: false
hideToc: false
enableToc: true
enableTocContent: false
tocFolding: false
tocPosition: inner
tocLevels: ["h2", "h3", "h4"]
keywords:
- Surge
- 旁路由
- 规则
- 模块
- clash
- Quantumult
- stash
tags:
- Surge
- 旁路由
series:
-
categories:
- life
featured_image: "cover/surge-mac-icon.webp"
---

## Surge简介

![surge](/images/surge/celue.jpg)

ios/mac平台上一款网络调试工具，中国大陆网友将其广泛运用于突破网络审查

丰富的模块、脚本功能，给予生活更多便捷、happy


同类软件有

- stash
- Quantumult X
- clash x/pro || clash for windows

由于近年苹果拥有arm架构的machines，一般将其安装在mac min m*上长期待机，极低的功耗和极少的事故率受人追捧，更多人将其替换原有x86类软路由

## 获取Surge

官网购买，购买后一年内可随意跟随升级，到期后根据实际需求加钱升级，目前（2023-07）是5.2.2版本。
单设备授权或合租多设备套餐，见[官网](https://nssurge.com/buy_now)

## 开始使用

导入配置，使用机场提供模版或借鉴开源脚本规则自定义配置，注意手动设置规则模版时，选对`Surge`对应版本

提供几个脚本和规则参考仓库
 - https://github.com/blackmatrix7/ios_rule_script
 - https://github.com/Tartarus2014/Surge-Script

打开增强模式，用于解决打不开微软商店同类问题

以下以我的网络配置作为事例，参考设置
光猫拨号，路由器接光猫
路由器ip：`192.168.50.1`

### 设置Surge所在宿主机为静态ip上网

ip地址：`192.168.50.2`
子网掩码：`255.255.255.0`
路由器：`192.168.50.1`
dns：`198.18.0.2`

以下方案选择其一


### 方案一：作为旁路由 **非侵入式** 接管网络

非侵入式指的是，网络不全由`Surge`接管，需要接管的设备，需要手动进行上网设置

某**设备1**现在要使用`Surge`接管网络，连接网络后，手动修改上网ip
ip地址：`192.168.50.3`
子网掩码：`255.255.255.0`
路由器：`192.168.50.2` # Surge所在ip
dns：`198.18.0.2`

### 方案二：作为旁路由 **浸入式** 接管网络

侵入式指的是，网络完全由`Surge`接管，设备无需额外设置

首先关闭路由器的DHCP功能，重启路由器
开启`Surge`的DHCP服务器功能

设备连接网络后会默认被Surge接管（需勾上`将Surge自动作为新设备的网关`）
噢 对了，先前**设备1**若设置了手动设置ip，现在可以改为DHCP，让其自动获取

你还可以在`Surge`控制面板设备菜单栏自行配置设备ip或图标，更改ip后，断开设备连接重新连接方可生效
![surge](/images/surge/device.jpg)

## **非侵入式**与**浸入式**的区别

|对比项|优点|缺点|
|:----    |:---|:---|
|非侵入式 | 让不需要上外网的设备，使用路由器动态分配ip，不受`Surge`宿主机的影响（系统升级、当机等） | 需要上外网的设备需一个个手动设置上网ip|
|浸入式 |所有连入网络设备都可被`Surge`接管，面板都能看到每个详情请求及统计|若`Surge`所在宿主机当机等，将会影响所有已连接设备|

个人目前使用非侵入式，主要是设备不多，手动设置后后续也无需再设置，这下妈妈再也不说网络咋又卡了：）

## 参考

- https://surge.mitsea.com/