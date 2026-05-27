---
title: "从 Bitwarden 开始讲起"
date: 2024-08-15
categories: 
  - "play-everything"
tags: 
  - "bitwarden"
  - "cloudcone"
  - "vps"
---
我是一个强迫症患者，程度算不上低，很早之前就想将自己的博客和其他 self-hosted 服务分开，博客单独一台 VPS，其他杂七杂八的自部署服务放在另一台 VPS 上，既要雨露均沾，也要有个孰轻孰重，以此体现我对于博客的重视，毕竟自诩博客爱好者。

![](https://huhexian.s3.bitiful.net/pic/2024/08/5fc03acde3880f0cede8eb33abd9d285.webp)

好巧不巧，[CloudCone](https://yinji.org/cloudcone.html) 最近不知抽什么风，上架两款 VPS，其中一款为4核心、2GB内存、30GB SSD 存储，4TB 流量，价格为[19.9美元](https://app.cloudcone.com.cn/vps/268/create?token=hashtag-2024-ssd-vps-2&ref=9587)，从没摸透过他们的营销手法。从刚开始接触时的复活节，到后面的黑色星期五（被鸽了）、圣诞节、周年庆等活动，优惠力度一次比一次小，这次也算是赶上了，账户里也有点余额，便剁手了一台，买之前想着，多部署一点有意思的工具或服务，让它充分利用起来。

我对于 VPS 的测试一窍不通，只会学着网友的教程，输入一段代码，运行一个脚本，等待测试结果。VPS 开通之后我用一个融合怪脚本进行测试，下面是它给出的数据结果。

![](https://huhexian.s3.bitiful.net/pic/2024/08/a4d78c936f762f50267f0e23e7c4373d.webp)

![](https://huhexian.s3.bitiful.net/pic/2024/08/4c2077e2933595c26b623667331f1078.webp)

![](https://huhexian.s3.bitiful.net/pic/2024/08/4c1b6f4e21ecb12243c96e64c9311f59.webp)

![](https://huhexian.s3.bitiful.net/pic/2024/08/a773555289b9ec2e1f96ae4e3140787e.webp)

机房在美国洛杉矶，大多数人用它做一些特殊服务，所以就会关注流媒体解锁情况，我目的不在此，部署网站之后的访问情况令我比较满意，包括现在这个博客，一直运行在 CloudCone 的 VPS 上，也较为稳定。

一切准备就绪之后想到的第一个服务便是密码管理工具。在这个方面我没有良好的习惯，过去一直都将密码存储在 Edge 浏览器上，通过 Microsoft 账户同步服务在多个设备之间使用，而且有过多个网站使用相同密码的情况，但是从上半年用 iPhone 之后，手机上的浏览器就一直是 Safari，懒得再下一个 Edge，以至于每次想登录某个网站，都得掏出我的荣耀30 Pro。

之前也使用过 Bitwarden，但后面随着某个域名过期，它也就不了了之。这次仍然采用 Docker 部署的形式，参照了 [Jack](https://veryjack.com/technique/%E7%BB%93%E5%90%88%E5%AE%9D%E5%A1%94%E5%92%8Cdocker-%E5%AE%89%E8%A3%85-bitwarden%E5%8F%8A%E6%95%B0%E6%8D%AE%E8%BF%81%E7%A7%BB/) 和 [aptX](https://atpx.com/blog/docker-vaultwarden/) 的教程，非常轻松地部署了 Bitwarden。

多说一句，aptX 的博客审美十分在线，语言文字、页面排版十分优雅。

```
docker run -d --name bitwardenrs \ 
--restart unless-stopped \ 
-e WEBSOCKET_ENABLED=true \ 
-v /www/wwwroot/demo/:/data/ \ 
-p 6666:80 \ 
-p 3012:3012 \ 
vaultwarden/server:latest
```

```
docker run -d --name bitwardenrs \ 
--restart unless-stopped \ 
-e SIGNUPS_ALLOWED=false \ 
-e WEBSOCKET_ENABLED=true \ 
-v /www/wwwroot/demo/:/data/ \ 
-p 6666:80 \ 
-p 3012:3012 \ 
vaultwarden/server:latest
```

步骤还是那几个步骤，先部署，能够访问之后先注册自己的账号，接着关闭注册功能，除此之外也加上了自动同步功能，网页上添加或更新密码，手机客户端也能同步更新。

浏览器上安装好官方扩展，手机上下载好官方客户端，剩下的就让 Bitwarden 发挥作用吧。

你以为我会继续部署一些玩意儿吗，找了半天，研究了半天，最后再部署了一个网站资源监控工具——Uptime Kuma，因为我发现自己没那么多需求，现有的工具足够，整个过程让我有一种为了这瓶醋，包了一锅饺子的感觉。文章开头写 CloudCone，但标题却是“从 Bitwarden 开始讲起”，原因是为了避免自己有打广告之嫌。

使用 Bitwarden，千万记住一点，你的主密码。当然，最主要的，不要做一个[虚假的自托管爱好者](https://blog.gujiakai.top/2024/04/fake-selfhost-lover)。

---
目前正在使用的自部署服务：
- [Umami](https://umami.is/)
- [Uptime Kuma](https://uptime.kuma.pet/)
- [Bitwarden](https://bitwarden.com/)
- [FreshRSS](https://freshrss.org/index.html)