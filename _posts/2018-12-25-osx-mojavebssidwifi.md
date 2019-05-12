---
layout: post
title: "OSX Mojave根据BSSID选择指定Wifi路由"
tagline: ""
description: ""
category: 博客
tags: [OSX]
last_updated:
---

在公共场合使用Mac的时候偶尔会遇到所处的地方有多个同名的Wifi路由器，出于各种原因你可能只想连接其中一个。在OSX Mojave下可以通过airport-bssid这个工具让系统连接到指定的路由器上。

## 准备工作
在开始之前需要先从Github下载 [airport-bssid](https://github.com/deekayw0n/airport-bssid)。

```bash
git clone https://github.com/deekayw0n/airport-bssid.git
```

## 获取目标路由的BSSID
但是其实airport-bssid本身也自带扫描路由信号的功能。如果要用airport-bssid来扫描的话，运行：
路由器的BSSID就是该设备的MAC地址。我会使用NetSpot这个软件来自动找到信号最强的那个路由的MAC地址。
```bash
./airport-bssid/Build/Release/airport-bssid en0 scan
```

其中en0是使用系统自带网卡时的接口（Interface），如果使用外接Wifi网卡的话需要按住Option键点击顶部的Wifi图标查看一下当前的Interface Name是什么。


## 连接至指定路由

假设想要连接的BSSID地址是 XX:XX:XX:XX:XX:XX ，那么运行
```bash
./airport-bssid/Build/Release/airport-bssid en0 XX:XX:XX:XX:XX:XX
```





## 后续
目前用以上这个方法连接到指定BSSID之后还是有可能会被系统自动跳跃去其他“系统认为更好的”其他BSSID路由，所以可以说还没有完全解决问题。其实直到OSX 10.9都还有原生的airport命令可以用来控制连接到哪一个路由，从OSX 10.10这个命令就消失了。
近几个版本的OSX一直有着一个很糟糕的移除好用功能的名声，比如移除了对建立Mac Server的大量原声支持。这种快速升级忽视后向兼容的开发倾向对于软件和生态系统的稳定性来说实在是很糟糕。
