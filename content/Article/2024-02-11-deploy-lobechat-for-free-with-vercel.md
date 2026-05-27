---
title: "使用 Vercel 免费部署 LobeChat"
date: 2024-02-11
categories: 
  - "play-everything"
tags: 
  - "chatgpt"
  - "lobechat"
  - "openai"
---

我在之前的文章《[充分发挥 ChatGPT 在日常生活中的作用](https://yinji.org/5225.html)》中介绍过一款开源项目——ChatNextWeb，搭配 Vercel 即可部署自己的网页对话机器人，但它仅支持对话，如果想使用 DELL·E 3 模型进行文生图，似乎无法实现。最近看到另一个类似的项目——[LobeChat](https://github.com/lobehub/lobe-chat)，功能更加齐全、丰富，UI 也更加好看，便记录一下部署过程。

![](images/6943e682bf035424e66991258bcbc9c2.webp)

## LobeChat 介绍

该项目在 GitHub 上已有 17.7k stars，这几个特性比较吸引人：

1. **GPT 视觉认知**。支持了 OpenAI 最新的 gpt-4-vision 模型，视觉识别，只需上传图片，即可识别图片内容，然后基于此进行对话。
2. **TTS & STT 语音会话**。这一功能在 ChatGPT 的官方客户端上就能体验，通过语音转文字或者文字转语音，与人工智能助手进行对话。
3. **Text to Image 文生图**。即支持通过插件唤醒 GPT-4 内置的 DALL-E 3 模型，直接调用文生图工具进行绘画，我在 Bing Create 上使用该功能绘制 Daily 图片，仅用一句诗，就能生成与之相符的图片。

如果开通了 ChatGPT Plus，以上三点应该可以轻松实现并体验，但对我来说太贵，便找到了平替方案。

## LobeChat 部署

LobeChat 提供了 Docker 镜像，也提供了 Vercel 的自托管版本，两种方式我都进行了测试，都可以正常部署并使用。

### Docker 部署

在 VPS 终端输入以下命令，就可以一键安装并启动 LobeChat 服务：

```bash
docker run -d -p 3210:3210 \
  -e OPENAI_API_KEY=sk-xxxx \
  -e OPENAI_PROXY_URL=https://api-proxy.com/v1 \
  -e ACCESS_CODE=lobe66 \
  --name lobe-chat \
  lobehub/lobe-chat
```

其中涉及到一些环境变量，`OPENAI_API_KEY` 是从 OpenAI 获取到的 API Key，如果你使用的 API Key 并不是来自官方，则需要加一条环境变量`OPENAI_PROXY_URL`配置代理地址，比如我使用的是第三方 API Key，由 [AIGC API](https://aigcapi.io/register?aff=HyYk) 提供，`ACCESS_CODE`是访问密码，建议设置。最后需要确保 VPS 端口 3210 保持开启且未被占用，然后通过 IP:端口的方式进行访问即可，或者进行反向代理，绑定域名使用。

### Vercel 部署

使用 Vercel 部署更加方便快捷，不用登录 SSH，也不用输入命令。

进入 GitHub 项目页面，fork LobeChat 项目之后登录 Vercel，选择对应的仓库进行导入。

![](images/82c6b012e45b84c72cffbdf8d69179b3.webp)

在环境变量部分填入相应的 Key 和 Value，如下图所示，我填写了`ACCESS_CODE` 、`OPENAI_API_KEY`和`OPENAI_PROXY_URL`，这样就可以通过 AIGCAPI 提供的第三方 API Key 使用 GPT-4 等模型。

![](images/97f59869fb2d9109e0507b1cc7f727a6.webp)

注意，如果在环境变量里填写了`OPENAI_API_KEY`等其他模型服务商的 API Key，则该服务部署成功之后可以直接使用，无需再在网站中填写 API Key，这一点在项目文档中写得比较清楚。

点击 Deploy，等待部署完成。

![](images/18adff18a50d10106962f2d511ec8c8c.webp)

即可访问网站，使用服务。

![](images/b5b42b544bd12b4ec4b0d3b2262ca577.webp)

切换 GPT-4 模型，打开内置的 DALL·E 3 插件，即可开启文生图模式。

![](images/b4172e6f91e026ea7db5bdd9907fec5d.webp)

除此之外，还内置了各种 AI 助手，涵盖写作、翻译、代码等方面。

![](images/5cd268f0e52a5df279954b707ff810e1.webp)

最后给大家分享一家我一直在使用的第三方 API Key 提供商，[AIGC API](https://aigcapi.io/register?aff=HyYk)，提供高效且稳定的 OpenAI 聚合 API，相比官方20$/月的 ChatGPT Plus，它提供的 API，价格低至1美元只需要2元人民币，除了 GPT-4 模型，图中这些也可以进行调用。

![](images/e3b81857165bf5d1b2580b2616fbcfd8.webp)

最近因为写毕业论文需要，便使用 LobeChat 和 [AIGC API](https://aigcapi.io/register?aff=HyYk) 的服务部署了一个网站，给自己和同学使用，效果还不错。
