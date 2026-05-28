---
title: "Cycling Page"
date: 2025-08-24
categories: 
  - "play-everything"
tags: 
  - "cycling-page"
  - "running-page"
---
![](https://img.yinji.org/WX20250824-213928@2x.webp)

yihong 开源的 [Running Page](https://github.com/yihong0618/running_page/) 项目特别有意思，他本人是一个跑步爱好者，从他的[页面](https://yihong.run/)数据可以了解到，跑步 14 年，总里程 12737km，相当于 0.3 个赤道。

我不喜欢跑步，体力不太行，去年年底买了[公路自行车](https://yinji.org/5386.html)，上半年骑了不少，后来[搬家](https://yinji.org/5548.html)买了二手电动车，自行车时不时就被闲置，以及 6 月买的一块 iGPSORT 码表，如何再次提起骑行的兴趣，部署一个 ~~Running~~ Cycling Page 或许是不错的选择。

刚买自行车那会儿就想折腾一番，想着直接从 Apple Watch 上同步数据，奈何苹果比较封闭，需要手动导出，后来看到小孙同学曲线救国的方法，将 iGPSPORT 的数据同步到 Strava，再通过 yihong 的代码获取 Strava 数据，最后部署静态网站。防止以后忘记，把过程记录下来。

第一步，Fork 仓库，[小孙同学](https://cyc.guoqi.dev/)也是骑公路车，我直接 Fork 他的仓库，在上面修改一些数据。

第二步，获取 Strava 的 Token 和 Code。

![](https://img.yinji.org/WX20250824-211330@2x.png)

主要是 Client ID、Client Secret 和 Refresh Token，前两个直接从 [Strava Developers](http://developers.strava.com/) 创建应用再获取，第三个有点复杂。

首先需要通过下方的链接获取 Code，要替换成自己的 Client ID。

```
https://www.strava.com/oauth/authorize?client_id=${your_id}&response_type=code&redirect_uri=http://localhost/exchange_token&approval_prompt=force&scope=read_all,profile:read_all,activity:read_all,profile:write,activity:write
```

接着在终端里输入代码，获取最后需要的 Refresh Token，也是要替换相应内容。

```
curl -X POST https://www.strava.com/oauth/token \
-F client_id=${Your Client ID} \
-F client_secret=${Your Client Secret} \
-F code=${Your Code} \
-F grant_type=authorization_code
```

最后把获取到的三项内容，添加到 Repository secrets 中。

![](https://img.yinji.org/1756041873870.jpg)

最主要的就是这几步，至于还有什么步骤我现在也忘了……yihong 原项目页面上有非常详细的教程，不过对于没什么 Code 基础的我来说还是需要费点时间。做完这些我就部署到了 Cloudflare Page 上，每天通过 GitHub Actions 同步 Strava 数据。

7 月份下载使用 Strava，它只能同步最新的数据，考虑到 iGPSPORT 还有不少记录，加起来骑行里程也快 100km，不放上去觉得可惜了，幸好没有多少条，全部手动下载 gpx 文件，再导入到 Strava 上，最后总共骑行里程是 200km 左右，一点点的成就感油然而生。

>https://cycling.yinji.org

![](https://img.yinji.org/WX20250824-213928@2x.webp)

