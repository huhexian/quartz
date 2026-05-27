---
title: "如何订阅一个博客？"
date: 2023-12-21
categories: 
  - "play-everything"
tags: 
  - "fluent-reader"
  - "netnewswire"
  - "readyou"
  - "reeder-5"
  - "rss"
---
![](https://huhexian.s3.bitiful.net/2023/12/21/9749b3e13fab9b3563e7553c93ffc58e.webp)

我很喜欢 [Inoreader](https://inoreader.com) 首页的一句话：Build your own newsfeed，建立你自己的信息推送。下方还有一段描述，内容如下：

>Follow your favorite websites and creators, collect articles, and discover inspiring content from across the web. Filter out the noise and make the most of your time online.

![](https://huhexian.s3.bitiful.net/2023/12/21/905175569e0de331cb2de0dd896c2f80.webp)

关注我们喜欢的网站和创作者，过滤掉噪音，充分利用我们的上网时间。

前几天在即刻上看到网友[阿粒](https://web.okjike.com/originalPost/657e51e079cb2b9f35882272)的手机桌面截图，她利用 Safari 的书签功能，在桌面上存了几个博客的地址，数量不多，如果数量多了，桌面上全是书签似乎也不太好看，便借此机会向她介绍了 RSS 订阅以及相关的软件，今天以此为基础，分享如何订阅一个博客的经验。

介绍两种方式，RSS 订阅和邮箱订阅。

## RSS 订阅

RSS 是什么，我也无法用生动形象的语言描述它，这不重要。一般的网站，比如我们使用 WordPress 搭建的博客、Hugo/Hexo 生成的静态网站等都支持 RSS 协议，通过特定的访问路径即可获取该站的 RSS 地址，如果不支持、没有找到 RSS 地址，这不重要，因为可以使用 [DIYgod](https://diygod.cc) 开发的 [RSSHub](https://github.com/DIYgod/RSSHub) 和 [RSSHub Rader](https://github.com/DIYgod/RSSHub-Radar) 工具，前者帮你生成该网站的 RSS 订阅，后者帮助你快速寻找该网站的 RSS 地址，并一键订阅至阅读器软件。

不管你有没有理解上面的内容，这不重要，重要的是用于订阅 RSS 的阅读器软件。

获取到某个网站的 RSS 地址之后，在阅读器里输入该地址，即可完成订阅。

正好我有 Windows、Android、iOS/iPadOS 三个系统的设备，便从这三个系统介绍对应的阅读器软件。


### Windows

总感觉 Windows 上的 RSS 阅读器并不多，虽然在 Microsoft Store 上搜索“RSS”能看到许多结果，但大部分都是停更多年。希望这只是我的错觉。

首推 Fluent Reader，外观、功能方面都很给力，不仅支持 Windows 系统，Linux 和 macOS 系统也有对应的软件。

下图是软件的界面截图，由此可见，如果博客文章的封面风格和形式统一，还挺好看的。

![](https://huhexian.s3.bitiful.net/2023/12/21/0ece7757fe662336de114b489706b809.webp)

切换阅读视图，这个界面和 iOS 平台上大多数软件相似。左侧是订阅源列表，中间是选中订阅源的文章列表，右侧是获取到的 RSS 正文内容。

![](https://huhexian.s3.bitiful.net/2023/12/21/776caf680c3e0e0f99156466c8e3c536.webp)

这是 Windows 系统上唯一一款让我觉得非常舒服的 RSS 软件，UI 设计、功能交互，都比较完美、流畅。最开始使用的时候，不支持多选订阅源，后面越来越多用户提交相关的反馈，最新版已经支持多选订阅源，在对订阅源分组的时候也可以多选。功能方面相对比较完善，除此之外还可以通过 Inoreader、Fever API、Google Reader API 等服务跨设备保持同步。

另一款，RSS 追踪，风格类似，以前也写过相关的介绍，具体请阅读《[RSS追踪：Windows平台上一款好用的RSS阅读器](https://yinji.org/3363.html)》。

- 项目地址：[GitHub](https://github.com/yang991178/fluent-reader)
- 下载地址：[Microsoft Store](https://www.microsoft.com/store/apps/9P71FC94LRH8?cid=github)

### Android

Android 由于自身系统开源，软件生态比较开放，催生出许多优秀的开源软件，RSS 阅读器这方面也没有落下。我首推的是在 GitHub 收获 3.2k stars 的 ReadYou。

虽然距离上次更新已经过去了两个月，但仍然抵挡不住我对它的喜爱，尤其是它使用了 Material You 风格的设计，在阅读方面，对中文、英文字体都很友好。

![](https://huhexian.s3.bitiful.net/2023/12/21/9c744b6ab64f5892d146cd423cd4693c.webp)|![](https://huhexian.s3.bitiful.net/2023/12/21/12333e89a8e73bfbb3f3614a0b212ebf.webp)
---|---

有的网站禁止 RSS 输出全文，但这还是不重要，因为部分 RSS 阅读器软件支持全文解析，比如上面提到的 Fluent Reader 和现在介绍的 ReadYou。

![](https://huhexian.s3.bitiful.net/2023/12/21/a2c8c0d81c967d16274dd7454a27039c.webp)|![](https://huhexian.s3.bitiful.net/2023/12/21/c75f0eb17fd8f0a1edf0f712f9b95554.webp)
---|---

上图是文章列表和正文阅读界面，下方提供收藏、下一篇、全文解析等功能按钮，似乎还有一个语音朗读功能未推出。

在 GitHub 上看到了该软件未来的计划，比如 Bionic reading、Android Widget、集成 FreshRSS 和 Inoreader 等，可以保持关注，应该会越来越好用，同时，我要远程催更。

- 项目地址：[GitHub](https://github.com/Ashinch/ReadYou)
- 下载地址：[GitHub](https://github.com/Ashinch/ReadYou)


### iOS/iPadOS


#### NetNewsWire

iOS/iPadOS 上的软件就更多了，大多数都同时支持 iOS、iPadOS、macOS 系统，而且支持苹果原生 iCloud 同步，在这一方面我表示十分羡慕。

![](https://huhexian.s3.bitiful.net/2023/12/21/6f0bbafaaf0503aba100294cfdce47f2.webp)

首推 NetNewsWire。支持 iOS、iPadOS、macOS 的开源软件，从2002年更新至今，是多数 RSS 爱好者的选择，可以在 App Store 上免费下载使用。

由于我没有 macOS 设备，因此向朋友 @[Demochen](https://demochen.com) 要了几张他在 MacBook 上使用 NetNewsWire 的截图，以供参考。

我猜 @Demochen 一定是个处女座，订阅源整理得这么舒服，命名如此有规则。

![](https://huhexian.s3.bitiful.net/2023/12/21/d551085a81a97841177955817b1b25a1.webp)

我也分享几张在 iPad 上的使用截图，效果大差不差，区别应该就只在于屏幕的大小。

![](https://huhexian.s3.bitiful.net/2023/12/21/9133e02cf415d8b60fb19b1221a02de5.webp)

怎么说呢，界面 UI 说不上很好看，但也不丑，非常板正，一眼望过去不觉得杂乱，非常整齐、干净。

- 官网地址：[NetNewsWire](https://netnewswire.com/)
- 下载地址：[App Store](https://apps.apple.com/us/app/netnewswire-rss-reader/id1480640210)


#### Reeder 5

第二款是 Reeder 5，付费软件。目前已经出到了第5版，似乎每次推出新版本，上一个版本就会开启限免活动，免费下载。我借了朋友的光，用朋友的账号在 iPad 上安装了 Reeder 5 正在使用。

![](https://huhexian.s3.bitiful.net/2023/12/21/7a7515ce6d6fa1c6dd0284f9fef0b083.webp)

或许因为是付费软件，功能支持比较多，设计得也要比 NetNewsWire 更加美观。支持 iCloud 同步、iCloud 稍后读、桌面小组件、Bionic Reading，对第三方服务的支持也很全面，Feedbin、Feedly、Inoreader、FreshRSS 等都支持。

我目前的方案就是自部署 FreshRSS，搭配 Reeder 5 在 iPad 上使用。

![](https://huhexian.s3.bitiful.net/2023/12/21/118240369f69888a573f0211119aee14.webp)

![](https://huhexian.s3.bitiful.net/2023/12/21/59da130b1cebb88177ddbe84c6a89f6f.webp)

但一般的用户估计用不上 FreshRSS、Tiny Tiny RSS 这类自部署 RSS 服务，只需要获取到 RSS 地址，然后使用上面提到的软件进行订阅即可。

- 官网地址：[Reeder 5](https://reederapp.com/)
- 下载地址：[App Store](https://apps.apple.com/app/id1529445840)

**国区 Apple ID 不一定能搜索到 RSS 相关的软件，请切换为美区或其他外区 Apple ID 进行下载**。

### 在线服务

在线服务是指只需要进入网站，注册账号进行订阅的 RSS 服务，常见的比如有 Inoreader、Feedly，大部分都有免费方案，对订阅数量有所限制，同时也有对应的移动端软件。

这些内容我在以前的文章《[我还是更喜欢这样的RSS阅读](https://yinji.org/3249.html)》都有所介绍，感兴趣的可以自行查阅。

至于像 FreshRSS、Tiny Tiny RSS 这类自部署 RSS 服务，可写的内容就更多，网上也有对应的介绍和教程，这里就不多说。

## 邮箱订阅

我在想，是不是有的人不喜欢使用 RSS 订阅，反而更习惯于邮箱订阅呢？

比如 newsletter 就受到挺多人的喜欢，虽然二者都是非常传统、经典的获取信息的方式，但考虑到用户对于工具便捷性的考虑，我还是通过插件，给博客加上了邮箱订阅的功能。

在博客右侧小工具栏，输入你的任意一个电子邮箱地址，点击订阅，在邮箱里确认订阅之后，便可以在未来收到博客更新的邮件通知。

当然，这只是我博客这样做了，其他博客可能有自己的想法，如果出现了邮箱订阅，从中选择合适的、习惯的即可。

从读者的角度来说，使用 RSS 订阅有一个好处，随时导入导出，再多订阅源，最后都可以导出为一份 OPML 文件，随时将其导入到其他 RSS 阅读器中；但从创作者的角度来讲，邮箱订阅的形式更有好处，创作者可以导出订阅者的邮箱地址名单，将其随时导入其他支持邮箱订阅的平台，将作品和读者掌握在创作者手中，不被平台束缚。

**那如何订阅我的博客？**

1. 使用上面提到的 RSS 阅读器，订阅我的博客（https://yinji.org/feed）
2. 前往我的博客，填写邮箱地址，即可完成邮箱订阅

## 最后的话

前几天看到 @[Dayu](https://anotherdayu.com) 的文章《[个人博客 RSS 订阅数统计](https://anotherdayu.com/2023/5523/)》，其中提到可以通过 API 的方式获取到博客在 Feedly、Inoreader、Feeds.pub 上的订阅数，但并不是所有人都是通过这三个网站订阅博客，自建服务和本地客户端软件的订阅如何统计呢？[虹线](https://1q43.blog/)的作者[评论尸](https://twitter.com/JeffreyCalm/status/1734451079536890080)给出了一个想法。

>可以混合统计，Inoreader、Feedly 这种平台写个接口去定期读数。然后Feed的每篇正文里加入一个0像素图片，去统计self-host阅读器的加载次数。理论上是可行的，但好像是没有现成的方案。

理论上是可行的，但好像没有现成的方案。那就期待开发者的行动咯。

---
以上便是我对于“**如何订阅一个博客**”这一话题所展开的分享，如有不正确之处，欢迎指正。