---
title: "用 Antigravity IDE 创建搜索意图分析英文网站—完整详细教程"
date: 2025-12-03
tags: ["Tutorials"]
draft: false
slug: "antigravity-ide-search-intent-tutorial"
---

在做 SEO、选关键词、做垂直细分市场研究时，你是否常常会遇到这种情况：

明明有了一个关键词，却不知道背后真正的搜索意图？

到底是求购买、求教程、求工具，还是求比较？

如果能有个网站输入一个 Google 关键词 → 自动分析其背后的搜索意图（Markdown 排版） → 轻松找到细分市场

那将会是一个不可多得的效率工具。

接下来，我就用 Goolge Antigravity IDE 一步步把这个网站从零构建出来。

## 网站开发完整流程

### **1️⃣ Step 1：确定网站需求（Planning 模式提示词）**

在 Antigravity 的 Planning 模式输入以下提示词，用于让 Gemini 规划网站文件结构、组件划分、UI 设计以及 API 逻辑：

```
我要创建一个英文工具网站，网站主要功能是：用户输入 Google 搜索关键词，返回关键词背后的搜索意图，以此帮助用户能够找到该关键词的垂直细分市场。

要求如下：

1. 网站界面为全英文
2. 使用 Next.js（稳定版本） + TailwindCSS 构建
3. 网站只需要一个首页
4. 页面包含：
   - 一个关键词输入框
   - 按全球语言使用人数排序的语言下拉框
   - 一个用于展示 Markdown 的结果输出框
5. 页面底部有一个 FAQ 区域，说明网站用途与使用方式
6. API 调用 Google 的模型：gemini-2.5-flash-lite
7. 请规划文件结构、UI 布局与 API 逻辑
```

Gemini 会自动给出：

- 项目文件结构

- 组件规划

- API Route 建议

- UI 布局

- Prompt 优化建议

确认后进入 Fast 模式执行。

![img](/images/2025/Snipaste_2025-12-03_17-08-16.png)

### **2️⃣ Step 2：进入 Fast 模式，让 Gemini 自动生成代码**

切换到 Fast 模式，对 Gemini 说：

> “请根据规划生成完整代码，包括首页、API Route、Tailwind 样式、Markdown 渲染、FAQ 区域，并标注我需要粘贴 Google API Key 的位置。”

### 3️⃣ Step 3：粘贴 API Key

在 .env.local 中加入 API Key。

```
GOOGLE_API_KEY=你的 Google AI Studio 密钥
```

### 4️⃣ Step 4：最终效果

![img](/images/2025/Snipaste_2025-12-03_16-59-23.png)

![img](/images/2025/Snipaste_2025-12-03_16-59-50.png)

## 🧭 Antigravity IDE 简介

Google 推出的免费 AI IDE，专为自动生成、修改、调试代码而设计。

首先到[官网](https://antigravity.google/)下载安装包。

下载完成后需要开全局和 TUN 模式才能登录并打开 IDE。

有两种模式可选择，Planning 和 Fast 模式。

![img](/images/2025/Snipaste_2025-12-03_16-43-47.png)

Planning 模式为在执行任务之前进行分析和规划，用于深度研究和复杂任务。

Fast 模式主要用于执行具体的任务，适用于那些能够快速完成的简单任务。

IDE 提供了 5 种模型供选择，Gemini 3 Pro(High)、Gemini 3 Pro(Low)、Claude 4.5、Claude 4.5(Thinking)、GPT-OSS(Medium)，目前所有模型免费。

![img](/images/2025/Snipaste_2025-12-03_16-44-12.png)
