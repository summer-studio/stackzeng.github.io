---
title: "Better Stack 使用教程"
date: 2024-11-30
tags: [Tutorials]
draft: false
slug: "better-stack-comprehensive-tutorial-guide"
---

## Better Stack 是什么？

Better Stack 是一个综合平台，旨在增强开发者和工程团队的可观测性和事件管理。它结合了多个功能，帮助高效监控、调试和解决技术栈中的问题。

## Better Stack 能做什么？

日志管理：Better Stack可以高速集中存储和搜索日志，将日志转化为结构化数据，并使用SQL查询。

正常运行时间监控：平台可以监控从网站到服务器的一切，确保任何停机时间都能迅速检测和解决。用户可以设置轮班值班，接收可操作的警报，并有效管理事件。

可观测性仪表板：Better Stack提供精美设计的仪表板，汇总来自各种来源的指标。这些仪表板可以通过不同的图表类型进行定制，并可以使用SQL查询进行调整。

## Better Stack 监控使用教程

我主要用来做网站监控，使用方式非常简单。

首先注册 Better Stack，https://uptime.betterstack.com/users/sign-up

填入网站域名和自己的邮箱。

注册成功后，进入到配置页面。

![img](/images/2024/Snipaste_2024-06-01_16-28-57.jpg)

告警功能只有邮箱是免费的，短信、推送、Call 都需要收费。

手机上装一个邮箱客户端就能白嫖告警功能。

配置检查间隔。

![img](/images/2024/Snipaste_2024-06-01_16-43-02.jpg)

检查间隔、恢复后检查间隔、检查区域、超时时间这些都有对应的配置，可以自行配置。

查看报表。

有了监控数据后，后台会生成报表方便查看。

![img](/images/2024/Snipaste_2024-06-01_16-48-31.jpg)

邮件通知。

当网站返回非 2xx 状态码时，会出发邮件推送，推送消息如下。

![img](/images/2024/Snipaste_2024-06-01_16-54-00.jpg)






