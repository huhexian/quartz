---
title: "过去的互联网完全由网站组成"
date: 2025-08-29
categories: 
  - "life"
tags: 
  - "internet"
  - "互联网"
  - "网站"
---
![](https://img.yinji.org/ezgif-6-fda79a0b31c0.gif)

>Younger readers may not even know that the internet used to be made entirely of websites, created by human beings, connected only by hyperlinks.
>
年轻的读者可能甚至不知道，互联网曾经完全由网站组成，这些网站是由人类创建的，仅通过超链接连接。

上面这段话来自 [Raptitude](https://www.raptitude.com/) 的文章《[How to Surf the Web in 2025, and Why You Should](https://www.raptitude.com/2025/06/how-to-surf-the-web-in-2025-and-why-you-should/)》，听起来匪夷所思，2025 年了，上网还需要人教吗？一部手机应该就足够了吧，但实际情况是会用手机不一定会上网，手机上的应用软件像是打包好了的各种各样的内容，只需要你点开它，肆意滑动屏幕，上下或者左右即可。然而，互联网过去完全由网站组成。

作者在文章中提到，要冲浪，就需要从一个带有外部链接的普通网站开始，同时也要避免所有由算法驱动的网站，例如 Twitter、Reddit、微博，包括上面提到的应用软件，尽快大部分互联网的流量都流向了他们，最后你必须使用真正的电脑，而不是手机，使用社交媒体不算是上网冲浪。

这让我回忆起 15 年前第一次上网的场景，通过 [hao123](https://hao123.com) 网站，进入了 [4399](https://www.4399.com/) 和 [7k7k](https://www.7k7k.com/) 小游戏网站，我依然记得当时的 hao123 上面有各种类型的链接，按照不同的分类进行摆放，非常直观地让你一眼看到并进入想要浏览的网站。令人泪目的是，时至今日访问 4399，页面和 15 年前几乎没什么区别。

最直观的显示外部链接的方式，我觉得就是文字下方画一条横线，并显示为蓝色，这已经是刻在 DNA 里的印象，一看到类似的文字就忍不住点开，跳转到另一个网站探寻新的内容。学会用 Google 之后偶然间发现了 [Wikipedia](https://zh.wikipedia.org/)，任意进入一个词条页面，都有许多蓝色字体链接着另一个词条，而站外链接则是用参考文献的方式放在了最末尾，没有下划线，似乎是更加美观了。一旦进入 Wikipedia，很难再关闭，一个词条连着多个词条，了解一个东西的时候，不知不觉就打开了许多新的标签页。

反观现在的大多数网站，外部链接变得更加稀少，或者压根就不提供外部链接，只想让访客留在自己的网站里，避免流量流失。这就是我为什么喜欢逛博客的原因，现在每天浏览的资讯网站只有 [IT 之家](https://ithome.com)，剩余几乎都通过 RSS 阅读博客，包括自己写博客，需要链接到其他网站时必然会链接，就比如今天这篇文章，无意间就在文字中分享了 [Raptitude](https://www.raptitude.com/) 博客。再或者昨天[陈仓颉](https://imzm.im)在群里分享的 [Floor796](https://floor796.com/)，这是一个展示了来自各种作品的角色在一个巨大空间站第 796 层的生活，许多角色的还原度极高，点击每个角色会显示对应的出处，视频链接或者图片链接。博客圈是个圈，从一个博客跳转到另一个博客，兜兜转转还会回到原来的地方。

![](https://img.yinji.org/WX20250829-225905@2x.webp)

现在的互联网似乎是一团糟，互相限制和拦截，人们更加倾向于大型的社交平台，社交平台内部又存在各种限制，比如在马斯克手下的 X 中，如果帖子中含有外部链接，曝光度则会降低。

或许是因为昨天看到这篇文章，也或许是因为很早之前的想法，今天给博客做了一个微小的调整，将原先使用 post_ID 形式的固定链接修改成 post_name 的形式，本来还想找一个插件，自动将标题翻译成英文并设置成固定链接，转念一想，翻译虽然更准确，但自己编辑更有意义，更能记住文章写了什么，post_ID 只对系统有意义，于我而言只是记不住的编码，而文章标题则是更加重要。具体的步骤不多记录，主要分为三步，导出文章 ID、标题和链接，手动或自动翻译成英文，导入数据库，通过 SQL 语句进行替换，最后再设置重定向，大部分都参考了 [Ouroboros](https://blog.pursuitus.com/) 的文章《[批量实现WordPress固定链接的中译英与重定向](https://blog.pursuitus.com/batch-translation-and-redirection-of-wordpress-permalinks.html)》进行操作。

>The old internet is still out there though, beneath and between the elevated freeways, but you probably have to surf your way there.
>
>旧的互联网仍然存在，在高架公路的下方和之间，但你可能需要自己冲浪才能到达那里。



