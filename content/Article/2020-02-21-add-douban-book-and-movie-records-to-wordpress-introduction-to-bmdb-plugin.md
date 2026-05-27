---
title: "WordPress添加豆瓣书影记录——bmdb插件介绍"
date: 2020-02-21
categories: 
  - "play-everything"
tags: 
  - "wordpress"
  - "豆瓣"
---

[![](images/2020060911012597-1170x730.jpg)](http://yinji.org/wp-content/uploads/2020/06/2020060911012597-scaled.jpg)

介绍一款一条龙全自动添加豆瓣书影记录的插件。该插件为[熊野](https://bearye.cn/)在基于牧风的项目上开发的WordPress插件。

在该页面申请Secret：[https://bm.weajs.com/](https://bm.weajs.com/)另外还需要填写你的豆瓣id及昵称，在该网站可同步豆瓣平台标注的电影和书籍信息，也可以在上面标注电影。

下一步即是安装插件，填写好secret即可。新建页面并填入

\[bm db\]movies\[/bm db\]或\[bm db\]books\[/bm db\]   （使用时请删去空格）

作者的话：WordPress 自带 jQuery 并不支持 $ 关键字，head 设置 meta 也需要通过官方钩子实现，如果你想在自己的 WordPress 的站点上布置读书观影记录，并不能完全按照牧风的教程来做，对没有接触过编程的人来说，这存在一定难度。

下载地址：[https://github.com/ibearye/bmdb-for-wordpress](https://github.com/ibearye/bmdb-for-wordpress)

牧风的项目地址：[https://github.com/iMuFeng/bmdb/](https://github.com/iMuFeng/bmdb/)

效果演示：[阅读记录](http://yinji.org/book.html) [观影记录](http://yinji.org/movie.html)

作者也介绍了集成到主题的方法。一并转载参考。

## 集成到主题

在wordpress上布置bmdb，核心基本与Github上的readme没区别，特别就在于如何在wordpress上正确

1. 设置头部meta；
2. 引入资源文件。

第一点，设置头部meta，在 `functions.php` 添加代码：

```
function bmdb_head()
{
    echo '<meta name="referrer" content="never">';
}
add_action('wp_head','bmdb_head');
```

第二点，引入资源，在 `functions.php` 添加代码：

```
function bmdb_css_js(){
    wp_enqueue_script("jquery");//如果已引入jquery，就去掉这一行代码
    wp_enqueue_style( 'bmdb', get_template_directory_uri().'/dist/Bmdb.min.css' );//第二个参数填css的地址
    wp_enqueue_script( 'bmdb', get_template_directory_uri().'/dist/Bmdb.min.js' );//第二个参数填js的地址
}
add_action('wp_enqueue_scripts', 'bmdb_css_js');
```

如果你直接把Github上下载的dist文件夹扔到了主题文件夹里，上面的代码就不用改了。

这两点解决了其他就很简单了，没必要再说了。
