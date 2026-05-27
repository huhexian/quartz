---
title: "2023年，你可以用 Thorn 写博客"
date: 2023-11-30
categories: 
  - "play-everything"
tags: 
  - "thorn"
  - "博客"
---
作为 Telegram 频道 @[FindBlog](https://t.me/FindBlog) 的运营者，我非常关注和博客相关的工具。最近在少数派看到关于 Thorn 的介绍文章，便和开发者联系，可以在频道无偿为他宣传产品，借此机会我也能够亲自使用2023年的全新写作和建站工具——[Thorn](https://thorn.red/)，在此做一个体验分享。

![](https://huhexian.s3.bitiful.net/2023/11/30/6d07f168a03ac1a743c09c62a215b736.webp)

2023年，博客已经不是新鲜玩意，但和博客相关的建站工具却层出不穷。前有 WordPress、Hugo、Hexo 等动态/静态博客程序，后有基于 Notion 的无代码建站工具 NotionNext 和 Nobelium，以及十分轻便、简单的 Gridea，让不懂代码的小白也能轻松搭建博客。

如何让搭建博客的门槛降低，是程序开发者应该考虑的问题，Thorn 似乎更符合这一点。

## 写作与建站集成

我用 WordPress 搭建博客，但我并不是用它进行写作，而是需要在电脑上用 Obsidian 写好文章，复制到 WordPress 上进行呈现，Obsidian 是我的写作工具，WordPress 是建站工具。

Thorn 将写作和建站集成在一起。

![](https://huhexian.s3.bitiful.net/2023/11/30/b5280794e2e468226ac322a9ce0e347a.webp)

如上图所示，我打开的是一个空间，将它命名为 Bruce，即我的一个写作空间。在该空间内，我可以编辑文章、添加随记，完完全全将它作为一个写作工具来使用，有字数统计、标签管理，数据在本地和云端都有备份。

文章编辑页面十分细节。支持 Markdown 语法，直接复制粘贴带有该语法的内容，会自动识别。右侧展示文章信息、大纲、标签，除此之外还可以将特定的文章通过链接分享到网络，也可以邀请他人一起协作编辑，支持导出各种格式的文件。

![](https://huhexian.s3.bitiful.net/2023/11/30/deccc5f8b33338586fdd37530eda3120.webp)

![](https://huhexian.s3.bitiful.net/2023/11/30/db29c49089e50bf8112c7cdc6761bd45.webp)

另外我觉得在文章配图方面，开发者也很用心。提供来自 Unsplash 的免版税图片，文章的封面可以随机切换，有多种样式可以选择。真正让我感到惊讶的是正文的图片编辑功能。

裁剪、滤镜、微调、标注、马赛克、边框、贴纸，您这是集成了 Photoshop 吗？

![](https://huhexian.s3.bitiful.net/2023/11/30/e06397dadad8d8609224e9106b245042.webp)

不要觉得华而不实，我认为非常实用。要想写好一篇文章，文字和图片同样重要，但大多数人在写作前会对图片花费大量时间，比如配图、修图等等，Thorn 集成了图片编辑功能，我们在写作时可以更加专注文字，图片好不好看先不管，添加的文章里再说，等形成一篇有模有样的文章之后，再回过头对图片进行编辑。

借助下面介绍的 Cloudflare Works 建立站点，便可以自由创建网站、搭建博客。

![](https://huhexian.s3.bitiful.net/2023/11/30/8e9700e0f913d4ce3bc93de6520cbda5.gif)

进入站点管理，可以对你的博客站点进行设置。常用的模板配置，包括设置站点基本信息、站点 SEO 信息、站点全局配置、文章全局配置；页面管理，自由添加、修改页面内容；数据管理，文章的增删修改。

![](https://huhexian.s3.bitiful.net/2023/11/30/ec9bca0a19c1613b597f204dc976ab69.webp)

![](https://huhexian.s3.bitiful.net/2023/11/30/402bd1358d5a401d69165ca3ee575c66.webp)

还有一个十分全面的仪表盘，可以查看站点分析。


## 写作是一种享受

得益于 Thorn 大气、漂亮的外观，精美的 UI 设计，以及灵动的气泡提示音，整个写作过程像是一种享受。

提供多种墙纸，打造优雅的协作环境。

![](https://huhexian.s3.bitiful.net/2023/11/30/cf8937f92d5c4e21a95387316ec4a727.webp)

这些都是细节部分，能够从使用上提升用户的体验。

实际编辑时，界面大气，文字显示效果非常棒，对于格式的处理也十分丰富。

![](https://huhexian.s3.bitiful.net/2023/11/30/3faff52df55fcc4b26677537043e94d1.gif)

提供了类似 Notion 的块编辑，Command/Ctrl + 单击节点，就会出现节点样式菜单，同时也可以拖动节点进行排序。

![](https://huhexian.s3.bitiful.net/2023/11/30/de583d7912c441eba1e9cae02e04525c.gif)

输入“/”，可以唤醒格式菜单。

![](https://huhexian.s3.bitiful.net/2023/11/30/0a728f329cbd252d000667c9e3d90971.gif)

## 借助 Cloudflare Works 建立站点

过去像 Hugo、Hexo 等静态博客程序一般都采用 GitHub Pages 或者 Cloudflare Pages 作为托管平台，前者对于小白来说，门槛较高，也时常面临着访问困难的问题，后者也差不多，也需要 GitHub 作为中介。

![](https://huhexian.s3.bitiful.net/2023/11/30/23ddbb5c6a99580dd29c1051e7c822c9.webp)

Thorn 采用 Cloudflare Works 作为托管平台，只需要注册登录 Cloudflare，在 Works 中获取所需的 ID 和 API 令牌，填入 Thorn 程序中，即可等待站点创建。而且，Cloudflare 有中文界面，更容易看懂。

即使你不懂什么是 Cloudflare，官网也提供了十分详尽的[使用文档](https://docs.thorn.red/)，跟着文档来，不会出错。

在此之后，你只需要通过 Thorn 创建文章，Cloudflare 会帮助你发布站点，一眨眼的功夫，即可访问。支持绑定自定义域名，绑定之后，SSL 证书之类的都会自动搞定。

最后，就有了下图中的博客，欢迎访问我的 [Thorn](https://thorn.yinji.org) 站点。

![](https://huhexian.s3.bitiful.net/2023/11/30/139a07bb5769e5a223c906d65ddc38bb.webp)


## Thorn 的美中不足

实际体验下来，也有一些使用槽点，不太符合我个人习惯，希望开发团队在后期能够进行优化改进。

首先是站点管理中发布文章的流程。使用文档中提到将 Thorn 空间中的文章作为内容进行发布，但为什么是拖动？如下图所示。

![](https://huhexian.s3.bitiful.net/2023/11/30/11b8a513b744e26b3093d3d96dbc1e2e.gif)

我很不理解这个逻辑。虽然使用文档中说了有很多个拖拽点可以将文章拖拽至放置点来完成设置操作。

但为什么不是使用选择文章的形式呢？拖动文章，要打开两个窗口，十分不便。

![](https://huhexian.s3.bitiful.net/69213543-3550541.webp)

其次是定价，如果是低频使用，免费方案足矣，但如果高强度使用的话，个人觉得付费方案定价稍贵，希望开发团队后续能够有所调整。

最后是生态。主题模板不多，目前只有三款，据官网了解，每月会上架1~2款来自官方以及社区的精选模板，如果能保持这样的进度进行确实挺好，但最好是有良好的生态和用户群体，包括使用者和开发者，能够提供更加丰富的模板。另外我希望在进行站点管理时，模板配置这一块增加一个自定义CSS，帮助用户自定义主题。

---

以上便是我对 Thorn 的体验分享，希望能给想写博客的你提供可行的参考建议。