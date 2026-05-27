---
title: "如何利用 Telegram 打造 0 成本微博客"
date: 2024-10-13
categories: 
  - "play-everything"
tags: 
  - "broadcastchannel"
  - "microblog"
  - "telegram"
  - "telegram-channel"
  - "微博客"
---

![](images/6Jtvo36MfuDqNmxf.png)

看到标题可能有人就说了，Telegram Channel 本身就可以作为一个微博客使用，但问题是并不是所有人都有能力和方法使用并访问 Telegram Channel，CloudFlare 和开源项目 BroadcastChannel 巧妙地解决了这个问题。

## BroadcastChannel 介绍

[BroadcastChannel](https://github.com/ccbikai/BroadcastChannel) 是[面条](https://chi.miantiao.me)大佬开发的项目，可以将 Telegram Channel 转为微博客使用，通过 Telegram Channel 发布内容，另一端通过 [Astro](https://astro.build) 程序进行呈现。

事先需要准备好 CloudFlare 账号和可以使用 Telegram 的网络。

项目提供了 Serverless 和 Docker 两种部署方式，前者简单易懂，也是我目前使用的。

## BroadcastChannel 部署

第一步，Fork 该项目到自己的 GitHub，接着前往 CloudFlare 或者 Vercel、Netlify 等平台创建项目，仓库即选择刚刚 Fork 的 BroadcastChannel。

![](images/WX20241013-231431@2x.png)

选择 BroadcastChannel 项目和 Astro 框架，然后再配置环境变量，其中必须事先配置的是 CHANNEL 变量，内容填频道名称，例如我的 @[FindBlog](https://t.me/findblog) 频道，变量就填写 FindBlog 即可。

![](images/WX20241013-231556@2x.png)

其他保持默认即可，该项目还提供了其他环境变量可供配置，可以在部署之后自行添加。

![](images/WX20241013-231743@2x.png)

只需一眨眼的功夫，该项目成功在 CloudFlare Pages 上部署，可以访问默认域名，也可以添加自定义域名。

后续只需要在 Telegram Channel 更新内容，即可自动同步并部署至 CloudFlare Pages，无需动手。

我在该项目开源之后第一时间部署了 @FindBlog 的微博客，效果很惊人，不仅界面美观，SEO 友好，还提供了 RSS，对于想简单写点博客的人来说，是一种简单、快捷的体验方式。

地址：[https://broadcastchannel.pages.dev/](https://broadcastchannel.pages.dev/)

![](images/lcheiO8aJYdBgtau.png)

其他变量：

```php
## Telegram 频道用户名，必须配置。 t.me/ 后面那串字符
CHANNEL=FindBlog

## 语言和时区设置，语言选项见[dayjs](https://github.com/iamkun/dayjs/tree/dev/src/locale)
LOCALE=zh-cn
TIMEZONE=Asia/Shanghai

## 社交媒体用户名
TELEGRAM=huhexian
TWITTER=huhexian
GITHUB=huhexian

## 下面两个社交媒体需要为 URL
DISCORD=https://DISCORD.com
PODCASRT=https://PODCASRT.com

## 头部尾部代码注入，支持 HTML
FOOTER_INJECT=FOOTER_INJECT
HEADER_INJECT=HEADER_INJECT

## SEO 配置项，可不让搜索引擎索引内容
NO_FOLLOW=false
NO_INDEX=false

## Sentry 配置项，收集服务端报错
SENTRY_AUTH_TOKEN=SENTRY_AUTH_TOKEN
SENTRY_DSN=SENTRY_DSN
SENTRY_PROJECT=SENTRY_PROJECT

## Telegram 主机名称和静态资源代理，不建议修改
HOST=telegram.dog
STATIC_PROXY=
```
