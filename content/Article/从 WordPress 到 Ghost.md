三个月前购买了搬瓦工的 Megabox 服务器，将博客搬到了上面，刚开始运行良好，后来不记得从什么时候开始，CPU 占用异常，经常飙升至 100%，搬瓦工限制也很高，时不时断连，另外还有一件奇怪的事情，别人挂代理无法访问，我挂搬瓦工代理却能正常浏览，IP 和域名都没有问题，一番决定之下，继续用 CloudCone，并且将 WordPress 换成 Ghost。

用 1panel 尝试过，非常方便，安装一个 Ghost 应用，再新建一个网站进行反向代理，就可以正常访问，但换一台设备登录却提示无法发送邮件验证码，遂放弃。Docker 安装更加适合我，也更容易修改配置，这次使用宝塔国际版——aapanel，按照官方文档提供的教程，新建文件夹、新建 Docker-compose 文件等，最后同样进行反向代理，成功搭建并顺利访问。


```
git clone https://github.com/TryGhost/ghost-docker.git /opt/ghost && cd /opt/ghost

cp .env.example .env
cp caddy/Caddyfile.example caddy/Caddyfile

docker compose pull
docker compose up -d

```

照着官方文档一步一步操作，基本上没有问题。

至于文章的固定链接，最初在 1panel 上使用时，所有的链接都变成了 Ghost 的默认形式，原本已经做好了手动修改的打算，切换到 Docker 安装，原来 postid.html 形式的链接现在只剩下了 postid，免除了很多操作步骤，剩下的几篇手动改改即可，现在新文章都打算用英文标题作为固定链接。

![](https://img.yinji.org/WechatIMG44.webp)

Ghost 的后台十分简单，写作和邮件是最主要的两大功能，免费主题不多，可折腾的地方很少，顶多把 Mailgun 配置好，让读者可以进行邮件订阅，我目前使用的是 Gmail 的 SMTP 服务，凑合用就行。另外，后台集成了 Unsplash 图库，配图十分方便，也很丰富，最新的 Ghost 6 还加上了联邦宇宙功能，通过 Mastodon 或者 GoToSocial 等服务即可关注，也第一时间用上了。最后还有一个无法理解的点，对于站点名称，居然有三个字的限制，目前还没想到方法解决。

自从工作以来，对博客的折腾就变得越来越少，关注度也也越来越低，这次换一个程序，希望能带来一些乐趣，以及对自身小小的满足感。