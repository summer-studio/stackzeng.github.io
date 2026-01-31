---
title: "Cloudflare R2 详细使用教程"
date: 2024-11-30
tags: [Tutorials]
draft: false
slug: "cloudflare-r2-comprehensive-tutorial-guide"
---

Cloudflare R2 是 Cloudflare 推出的兼容亚马逊 S3 的存储服务。

每月 10GB 免费存储，读取数据：1000万次/月免费，操作数据：100万次/月免费。

![img](/images/2024/Snipaste_2024-02-04_21-25-01.jpg)

R2 可以用来做什么？

最大的用处就是作为个人开发者刚起步时免费的图片存储应用。

如果你正在做图片存储的应用，那么 R2 非常适合。

## 注册

填写信用卡基本信息，带有 Visa 或者万事达标识的卡都行，提交成功后会发生一笔 0 元的交易信息，以确认信用卡的可用性。

![img](/images/2024/Snipaste_2024-01-27_17-16-56.png)

## 创建 Bucket

点击 Create Bucket。

![img](/images/2024/Snipaste_2024-01-28_16-47-11.jpg)

输入 Bucket name。

![img](/images/2024/Snipaste_2024-01-28_16-47-50.jpg)

根据自己的业务选择对应的地区，美国、欧洲、中国。

## 上传文件

控制台直接上传图片。

![img](/images/2024/Snipaste_2024-01-28_16-53-58.jpg)

![img](/images/2024/Snipaste_2024-01-28_16-54-40.jpg)

## 创建 API Token

Token 主要用来做 API 调用。

![img](/images/2024/Snipaste_2024-01-28_16-57-01.jpg)

权限选择读写权限。

![img](/images/2024/Snipaste_2024-01-28_16-59-46.jpg)

选择刚才创建的 Bucket，TTL 选择永久。

![img](/images/2024/Snipaste_2024-01-28_17-00-25.jpg)

![img](/images/2024/Snipaste_2024-01-28_17-02-00.jpg)

## 域名配置

配置域名可以公开访问图片，不配置使用 Cloudflare 的私有域名访问速度会被限制。

## SDK 调用

Cloudflare 其实是对亚马逊 S3 的封装，SDK 的使用方法和亚马逊的 S3 是一样的。
