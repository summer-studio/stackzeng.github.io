---
title: "Supbase 数据库详细使用教程"
date: 2024-11-30
tags: [Tutorials]
draft: false
slug: "supabase-database-comprehensive-tutorial-guide"
---

## Supbase 是什么？

Supabase 是一个开源的 Firebase 替代品，它提供了一系列后端服务，帮助开发者快速构建应用程序，包括以下功能。

基于 PostgreSQL 数据库：Supabase 使用 PostgreSQL 数据库作为其数据存储的基础。

认证和授权：提供用户认证和数据访问控制功能。

即时 API 和实时同步：自动生成 RESTful API，并支持数据库变更的实时订阅。

文件存储和边缘函数：允许存储文件和在边缘位置运行代码。

向量嵌入和 AI 工具：提供向量处理和 AI 功能的工具。

## Supbase 能解决什么问题？

数据库方案一般有两种方案，第一种方案是购买云服务器自建数据库，第二种方式是购买云服务的数据库服务。

无论哪种方案对于刚起步的独立开发者来说，成本都比较高昂。

Subbase 则是提供了 500 MB 的免费存储空间，每月 50,000 的活跃用户的访问量。

详情可以查看 https://supabase.com/pricing

## 如何使用 Supbase？

注册账号后，创建 Project。

![img](/images/2024/Snipaste_2024-03-27_10-44-23.png)

填入名称、密码，选择业务的物理区域。

![img](/images/2024/Snipaste_2024-03-27_10-44-44.png)

创建表，以用户表为例。

![img](/images/2024/Snipaste_2024-03-27_10-59-21.png)

连接数据库，点击创建后的 Project，左侧选择 database 菜单。

![img](/images/2024/Snipaste_2024-03-27_11-21-19.png)

右侧界面就是连接数据库的账号和密码。
