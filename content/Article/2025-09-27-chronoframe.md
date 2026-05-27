---
title: 展示照片的好地方
date: 2025-09-27
categories: 
  - "play-everything"
tags: 
  - "afilmory"
  - "chronoframe"
---
## 缘起

我见过许多可以上传照片，将其作为作品展示的平台，比如小红书、Instagram、抖音，再或者是图虫，或者是国外的 [Unsplash](https://unsplash.com/@huhexian) 等平台。或许和写博客一样，内心有一股执念，数据只有掌握在自己手里才安全，紧接着便开始搜索各种可自部署的图片展示服务。

过去使用 Typecho 搭配立云图志的 [Snapic Plus](http://www.lopwon.com/snapic-plus-v5.html) 主题，折腾了一段时间，最近又因为拾一的 [Afilmory](https://github.com/Afilmory/afilmory) 项目，勾起自己的折腾兴趣，尝试了许多次，终究因为它缺少后台管理功能，无法直接在后台添加新的照片，需要在存储端进行增加，较为繁琐。最近找到另一款类似的项目——[ChronoFrame](https://github.com/HoshinoSuzumi/chronoframe)，外观、功能大差不差，最重要的是有 dashboard，随时随地登录后台添加新照片，极其方便。

## ChronoFrame

相比较 Afilmory，ChronoFrame 的部署也更简单利落，熟悉 Docker 则非常容易上手。提供 Docker 和 Docker Compose 两种形式，这里将自己的过程记录下来，方便以后继续使用。

我在服务器上安装了 1panel，新建文件夹，命名“photo”，然后新建文件，命名为 .env，在文件里填入下列信息：

```
# Admin user email (required)
CFRAME_ADMIN_EMAIL=
# Admin user name (required)
CFRAME_ADMIN_NAME=
# Admin user password (required)
CFRAME_ADMIN_PASSWORD=

# 应用标题与口号
NUXT_PUBLIC_APP_TITLE=
NUXT_PUBLIC_APP_SLOGAN=
NUXT_PUBLIC_APP_AUTHOR=
NUXT_PUBLIC_APP_AVATAR_URL=

# Mapbox Token
NUXT_PUBLIC_MAPBOX_ACCESS_TOKEN=

# 存储提供者（s3/github/local）(required)
NUXT_STORAGE_PROVIDER=s3
# S3 存储服务配置(required)
NUXT_PROVIDER_S3_ENDPOINT=
NUXT_PROVIDER_S3_BUCKET=chronoframe
NUXT_PROVIDER_S3_REGION=auto
NUXT_PROVIDER_S3_ACCESS_KEY_ID=
NUXT_PROVIDER_S3_SECRET_ACCESS_KEY=
NUXT_PROVIDER_S3_PREFIX=photos/
NUXT_PROVIDER_S3_CDN_URL=

# 会话密码（32 位随机字符串，必须设置）(required)
NUXT_SESSION_PASSWORD=

# GitHub OAuth
NUXT_OAUTH_GITHUB_CLIENT_ID=
NUXT_OAUTH_GITHUB_CLIENT_SECRET=
```

备注 required 的则是必填项，最上面是登录邮箱和密码，接着是网站标题和描述、头像地址等，如果照片上存有地点信息，则可以申请 Mapbox 的 Token 一并部署，网站上就可以显示相应的地理信息；最主要的是存储提供者，目前仅支持 S3 协议，比如缤纷云、阿里云 OSS、腾讯云 COS，都可以使用，难点在于存储桶的相关信息要填写正确。

另外还需要创建 `docker-compose.yml` 文件，填入下列信息：

```
services:
  chronoframe:
    image: ghcr.io/hoshinosuzumi/chronoframe:latest
    container_name: chronoframe
    restart: unless-stopped
    ports:
      - '3000:3000'
    volumes:
      - ./data:/app/data
    env_file:
      - .env
```

最后一步，启动命令：

```
docker-compose up -d
```

这是我部署的：

> [https://fade.im](https://fade.im)

这是陈仓颉部署的：

> [https://photo.imzm.org](https://photo.imzm.org)

他一开始部署没成功，气得红温，最后还是折腾成功了。

## 后话

部署完这个服务之后，上传了一些自认为还不错的照片，然后呢，内心又陷入一阵空虚。照片没拍几张，却一心想着如何展示，你拍得很好吗？其实也一般，但只要自己喜欢，就足够了。

最后，问一下小孙，你的 [Camlife](https://github.com/sun0225SUN/camlife) 进展如何。
