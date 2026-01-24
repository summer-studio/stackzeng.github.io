---
title: "Cloudflare Pages 全流程部署指南：从 GitHub 连接到运行环境配置"
date: 2025-12-04
tags: [Tutorials]
draft: false
slug: "cloudflare-pages-github-deployment-guide"
---

在将项目部署到线上时，我们往往希望整个过程既顺畅又高效。

Cloudflare Pages 提供了便捷的静态网站托管能力，只需连接 GitHub 仓库并做少量配置，就能自动构建并部署网站。

下面将带你一步步完成从创建 Pages 项目到最终成功访问页面的完整流程。

### **1. 创建 Cloudflare Pages 项目**

打开 **Cloudflare 的 Works & Pages**，点击右上角 **Add**，选择下拉菜单中的 **Pages**。

![img](/images/2025/Snipaste_2025-12-04_15-53-56.png)

连接 GitHub 仓库。

![img](/images/2025/Snipaste_2025-12-04_15-54-29.png)

选择对应的仓库。

![img](/images/2025/Snipaste_2025-12-04_15-54-50.png)

选择项目所使用的开发语言，其他选项保持默认即可。

![img](/images/2025/Snipaste_2025-12-04_15-56-27.png)

点击 **Deploy**，稍等片刻即可看到部署成功界面。

![img](/images/2025/Snipaste_2025-12-04_15-58-25.png)

### **2. 解决因未开启 Node.js 兼容而导致的访问错误**

首次访问部署后的链接时，如果出现错误提示，很可能是因为没有启用 Node.js 兼容模式。

进入项目的 **Settings** 页面，左侧选择 **Runtime**，右侧找到 **Compatibility flags**。

![img](/images/2025/Snipaste_2025-12-04_16-02-20.png)

输入 **nodejs_compat** 并启用该选项。

![img](/images/2025/Snipaste_2025-12-04_16-02-50.png)

### **3. 配置 Google API 密钥**

在左侧菜单选择 **Variables and Secrets**。

![img](/images/2025/Snipaste_2025-12-04_16-13-46.png)

切换到 **Secret** 标签，填写本地项目中 .env.local 内的相关配置。

![img](/images/2025/Snipaste_2025-12-04_16-14-28.png)

### **4. 访问最终部署效果**

完成上述设置后，重新访问页面即可查看最终效果。

![img](/images/2025/Snipaste_2025-12-04_16-17-31.png)

## ✨总结

对于独立开发者来说，部署流程越轻量、越自动化，就能把更多精力放在真正重要的地方产品本身。

Cloudflare Pages 正好满足了这一点：通过简单的仓库连接、自动构建和灵活的运行环境配置，你可以快速把想法从本地推向线上，不再被复杂的服务器运维束缚。

无论是个人主页、 side project，还是正在试验的新功能，只需一次设置，以后每次提交代码都会自动部署。

这种省心式的上线体验，让独立开发者能更高效地迭代项目、验证想法，并以更低的成本构建属于自己的产品生态。
