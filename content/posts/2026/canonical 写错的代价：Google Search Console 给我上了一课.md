---
title: "canonical 写错的代价：Google Search Console 给我上了一课"
date: 2026-01-12
draft: false
slug: "google-search-console-canonical-errors"
---

今天在 Google Search Console 后台看到这样一个消息提示：

```
备用网页（有适当的规范标记）

此类网页未编入索引或不会显示在 Google 搜索结果中
```
![img](/images/2026/Snipaste_2026-01-12_21-34-09.png)

初看这个消息不太明白，经过查询资料后之后才明白真正的含义。

其实是在说，Google 选择了另一个 URL 作为主版本。

Google 发现这个 URL 和另一个 URL 内容一模一样，你得告诉我（或我判断）哪一个才是规范版本。

可能的原因在于 canonical 标记没有指向自己的域名。

我查看了 canonical 标记，发现了问题所在。

![img](/images/2026/Snipaste_2026-01-12_15-26-57.png)

原来 Kiro 人工智能在创建网站时给 canonical 配置了占位符域名，而我当时没有发现直接上线，导致 Google 无法判断哪个才是主版本。

解决方案就是将 canonical 标记改为域名即可。

## **为什么 Google 非常需要 canonical？**

网站域名同一内容，多种 URL 是常态：

常见重复场景

- https://www.domain.com/

- https://domain.com/

- https://www.domain.com/index.html

- https://www.domain.com/?utm_source=twitter

👉 人看是同一个网页，Google 看是 4 个页面

如果你不说清楚：

- Google 会自己选一个

- 权重会被拆

- GSC 就会报你现在看到的那些提示

配置了 canonical 后，会把权重集中到一个 URL。

所有重复页面的：

- 外链权重

- 内部链接权重

- 历史信号

👉 都会尽量汇总到 canonical URL 上

这点对 SEO 工具站 非常关键。

