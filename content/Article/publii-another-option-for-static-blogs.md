---
title: "Publii：静态博客的另一个选择"
date: 2024-03-20
categories: 
  - "play-everything"
tags: 
  - "cms"
  - "netlify"
  - "publii"
  - "静态博客"
---
最近接触到一个以前没见过的静态内容管理系统，即我们俗称的静态博客生成器，Publii。从2023年提交代码至今一年多，一直在保持更新和维护，使用和部署并不难，提供了非常详细的使用文档。我借助文档，部署了一个，使用体验有点类似开源的 [Gridea](https://gridea.dev)，都是将静态博客的部署简单化、具体化，不同的是前者更偏向 CMS，后者更着重博客。

![](https://huhexian.s3.bitiful.net/pic/2024/03/6011e4c6407f52d9aae7767f372c29b8.webp)

由于自己运营着 Telegram 频道 @[FindBlog](https://t.me/findblog)，便在此记录部署的整个过程，并对 Publii 做一番简单的介绍。

## Publii 是什么

项目页面介绍称，这是一款面向隐私保护、SEO 优化网站的静态内容管理系统，支持 **Windows**、**macOS** 和 **Linux**，能够让初学者快速且轻松地创建静态网站，这一点我相信 Gridea 已经做到了。

它将开源的 WordPress 程序与其做对比，WordPress 是基于服务器的 CMS，而 Publii 由于提供了一个易于理解的用户界面，从某种程度上来说也像是在服务器上使用 CMS 程序。

使用 Publii 的三个步骤：
1. 下载 Publii
2. 撰写内容
3. 发布网站

## 部署之前需要做的事情

下载 Publii，设置语言。

![](https://huhexian.s3.bitiful.net/pic/2024/03/1bd5b4931fbee7909d7361cee09adee8.webp)

从 GitHub 或者官网获取安装包安装好之后，最初的界面为英文，需要点击右上角的语言选项安装中文语言包，中文语言包在 GitHub 上可以下载，由国内热心网友翻译维护。

![](https://huhexian.s3.bitiful.net/pic/2024/03/d94816d6fa8fa97d7c60e3f22fcde6cd.webp)

**如何部署 Publii**，目前支持 HTTP/HTTPS 服务器、Netlify、Amazon S3、GitHub Pages、Google Cloud 和 SFTP。

## 使用 Netlify 免费部署 Publii

在 Netlify 需要做这些步骤：

![](https://huhexian.s3.bitiful.net/pic/2024/03/976aab30f21fc489e36ecc41c42e117f.webp)

![](https://huhexian.s3.bitiful.net/pic/2024/03/e04507c6095f0a1c00adf1fb24619dce.webp)

首先，前往 Netlify 主页登录，创建一个新的站点——deploy manually，然后上传由 Publii 提供的压缩包，不用解压，直接一整个压缩包上传。随后我们会获得一个 Netlify 提供的域名，可以将其作为博客域名使用，也可以提前解析并绑定自定义域名。

然后，点击站点设置（Site setting）按钮，找到站点信息（Site information）部分，保存好站点 ID，稍后会用到。

![](https://huhexian.s3.bitiful.net/pic/2024/03/54589910771cbec4803e44b085f37692.webp)

最后，需要生成一个访问令牌（Access Token）。点击右上角账户名称，在个人资料（Profile）部分，点击应用程序（Application），然后新建访问令牌，生成之后保存，稍后会用到。

![](https://huhexian.s3.bitiful.net/pic/2024/03/769602e04f3d6750451038af9abc1d1a.webp)

以上是在 Netlify 需要进行的设置，接下来打开 Publii，进入服务器设置。

![](https://huhexian.s3.bitiful.net/pic/2024/03/7f51d1b5fdd8fa8fdfef9adb2ca53a63.webp)

推荐使用 Git Repository 或者 Netlify 部署。使用 Netlify 部署，只需要填写上述提到的三个内容，域名、Site ID 和 Access Token。

![](https://huhexian.s3.bitiful.net/pic/2024/03/e84ec222b3d6b730499f4a34c38d5b8a.webp)

保存好设置之后可以点击“测试链接”，测试是否能与 Netlify 进行链接，这里有点问题，我点了之后一直没反应，但同步网站之后能正常访问。

接着点击左下角“同步您的网站”，即可通过域名访问。之后每次有内容更新，可以先在本地预览更改，再同步到 Netlify 进行部署。

![](https://huhexian.s3.bitiful.net/pic/2024/03/817e0e533c7c75b81d777d151f0e42d8.webp)

## Publii 的特色

就像它在 GitHub 项目页面上所说的，专为 SEO 优化和注重隐私的网站设计，这应该是 Publii 最大的两个特色。

![](https://huhexian.s3.bitiful.net/pic/2024/03/12571ce6ac08afa4dce16d4f5ae87809.webp)

![](https://huhexian.s3.bitiful.net/pic/2024/03/9a9874c4e8c2b717bd939dc5106a83fe.webp)

对 URL、Sitemap、OpenGraph、Twitter Cards 的支持都直接放在了网站设置里，不用单独的主题进行适配。

![](https://huhexian.s3.bitiful.net/pic/2024/03/f5cdc6847c8015f785a6f48d8a0efdcb.webp)

包括对于机器人、爬虫的屏蔽，都可以一键手动开启或屏蔽。

![](https://huhexian.s3.bitiful.net/pic/2024/03/85823d20b2af680b9fb1ea0dc497aa43.webp)

主题的自定义设置，翻译有待更新。我不确定每个主题的自定义设置是否一致，目前默认主题支持以上自定义设置，包括字体、页脚、搜索、菜单栏等内容。

官网[主题市场](https://marketplace.getpublii.com/themes/)展示的主题较为丰富，分为博客、文档、问答、杂志、照片、旅行等类别，有免费和付费。

![](https://huhexian.s3.bitiful.net/pic/2024/03/0bc9a0686eacd723d8cd61a152a74692.webp)

提供三种编辑模式，区块编辑器、所见即所得编辑器、Markdown 编辑器，不过我认为 Obsidian 的 Markdown 是最好用的。在文章编辑页面提供的设置也比较多，发布状态、是否精选、精选图片、标签，以及 SEO 设置。

默认主题呈现的效果也还不错，大气、美观，但似乎没有找到创建和编辑单独页面的功能，希望开发者后期能够更新。

以上便是我对 Publii 部署的体验分享，对于新手用户来说，确实比 Hugo、Hexo 甚至 Gridea 还要容易上手，并且官网的使用文档十分清楚明了，但可能还需要了解 GitHub、Netlify 的注册和使用，尤其是访问这两个网站。

如果你对该项目感兴趣，可以点击下方的链接详细了解。

- [Publii 官网](https://getpublii.com/)
- [Publii 项目地址](https://github.com/GetPublii/Publii)
- [我部署的 Publii 博客](https://publii.yinji.org/)