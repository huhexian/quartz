---
title: "Cloudflare 与 OneKey Card"
date: 2024-09-01
categories: 
  - "play-everything"
tags: 
  - "cloudflare"
  - "cloudflare-r2"
  - "onekey-card"
  - "webp-cloud"
---
![](https://webp.yinji.org/202409012242640.webp)

原本标题可以类似于“开通 Cloudflare R2，创建免费图床”、“域名转入 Cloudflare，香”、“OneKey Card 虚拟信用卡注册激活教程”等等，但我只取了其中两个关键词，诸如此类的教程随便 Google 一下就是一大堆，我没有必要照抄别人的内容，替换自己的图，然后标题一改或者索性不改，那叫什么，那tmd叫[洗稿](https://t.me/FindBlog/501)。

## 赛博佛祖

不止一次听过 [Cloudflare](https://www.cloudflare.com/zh-cn/) 赛博佛祖的外号，也一直想把域名转入到 Cloudflare，使用它的一些免费服务，但信用卡对我来说是一个门槛，没有办理，不知道该办理哪种信用卡，目前也不太想过早使用信用卡，所以 Cloudflare 在我这里还没有派上太大用场。

![](https://webp.yinji.org/202409012231465.webp)

前段时间参与 [Dogs](https://t.me/dogshouse_bot/join?startapp=m64px3aLRdSfQiipYchkCQ) 的空投（它的狗头画得真丑），昨天发现已经到账 Telegram 的 Wallet，46刀，正想着如何把它用掉，便想到很早之前注册过的 [OneKey Card](https://card.onekey.so/?i=VFDH2E)，因为当时需要充值 USDC 或 USDT 才能激活，兴趣不大，就搁置了，轻松几步，就将 Telegram Wallet 里的 Dogs 转入到 OneKey Card，并开通了虚拟 Visa 卡。

信用卡有了，那就开始用 Cloudflare。在将 OneKey Card 绑定到 Cloudflare 作为主要支付方式时，账单地址填写遇到了一点小问题，应该是地址需要稍微调整，不过我挺好奇，外国人非常喜欢邮寄账单吗，听上去是一种很传统的形式，虽然在美剧里也看到过邮寄水电煤账单和选票之类的情节。

## Cloudflare R2

[Cloudflare R2](https://www.cloudflare.com/zh-cn/developer-platform/r2/) 的使用，参考了 [Pseudoyu](https://www.pseudoyu.com/zh/2024/06/30/free_image_hosting_system_using_r2_webp_cloud_and_picgo/) 和 [Leslie](https://justgoidea.com/posts/2024-022/) 的文章，写得非常详细，我是两篇一起看的，理论上不冲突，但个人愚钝，差点搞混了里面的步骤。通过 Pseudoyu 的教程，进行了 Cloudflare 的基础设置，以及 [WebP Cloud](https://webp.se/) 的开通；通过 Leslie 的教程，部署了[一个球](https://github.com/jw-12138)大佬开发的 [R2 Uploader](https://github.com/jw-12138/r2-uploader) 工具，部署简单，界面也很简洁美观，和他[博客](https://jw1.dev/)一样。

我对 WebP Cloud 的理解，相当于国内云存储平台的图片处理功能，可以对图片进行体积压缩、添加水印、缓存等等，也有免费额度。

R2 Uploader 即是一个图片上传工具，替换 Cloudflare R2 后台简陋的上传页面，据 Leslie 的文章介绍，还有图像压缩、大文件上传等功能。

![](https://webp.yinji.org/202409012231824.webp)

将 WebP Cloud 和 R2 Uploader 联动起来，实现一键上传和代理。我在 Piclist 上也进行了相关设置，主要是想使用**从剪切板上传**和**上传后自动复制 markdown 链接**这两个功能，隔空喊话一个球大佬，后续是否有计划给 R2 Uploader 加上这两个功能。

域名转入不再赘述，就和将大象装进冰箱一样简单。仍然纳闷的是，为何国外域名服务商转移域名如此之快，6年前将一个域名从国内某主机服务商转入腾讯云，花了10天，今天从 Porkbun 转到 Cloudflare，10分钟左右搞定。

## OneKey Card

不记得什么时候注册的账号，当时一起的似乎还有 Depay，或者说 Dupay，不知道它们什么关系，现在情况如何。

看网上的消息，现在 [OneKey Card](https://card.onekey.so/?i=VFDH2E) 免月费，不用白不用，趁此机会绑定了支付宝，虽然不知道为什么无法在淘宝上使用这张卡，但在美团上实打实能支付，中午点了麦当劳外卖、买了团购优惠券，本想再充个话费，似乎不太行。

![](https://webp.yinji.org/202409012227703.webp)

头一回知道虚拟货币还能这样使用，也算是开了眼界。用它作为 Cloudflare 的主要支付方式，也非常方便，只不过以后需要支付，还得往里面充值虚拟货币。

[OneKey Card](https://card.onekey.so/?i=VFDH2E) 现在还能注册，Google 账号一键登录即可，建议尝试一下。

![](https://webp.yinji.org/202409012234583.webp)