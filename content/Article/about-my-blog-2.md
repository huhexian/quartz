---
title: "关于我的博客2.0"
date: 2023-05-07
categories: 
  - "play-everything"
tags: 
  - "twenty-twelve"
  - "wordpress"
  - "主题"
  - "博客"
  - "折腾"
---
终于动手写《关于我的博客2.0》。

在两年前写了一篇介绍自己博客的文章《[[about-my-blog|关于我的博客]]》，两年时间过去了，和当时相比，只能说大同小异。正好前段时间有网友留言，看到我对于 Twenty Twelve 主题的修改，问能否写个教程。我也是从网上各种教程文章扒的代码，便找时间记录下来吧。

## 框架

依然使用 WordPress 和 Twenty Twelve 主题，但是主题经过了比较大的修改，后面会详细说明。

运行在 CloudCone 提供的美国 VPS 上，具体情况可以看之前的文章。

域名是昨天在 NameSilo 注册的，由于我没有信用卡，无法使用 Google Domains 进行注册。Google Domains 土耳其区注册 .net 域名每年仅需人民币25元左右。亏大发了。

## 插件

目前加上强化拓展，一共只使用了3个插件。

分别是 [WP Githuber MD](https://github.com/terrylinooo/githuber-md)（用于 Markdown 写作）、[WP-Douban](https://fatesinger.com/101005)（用于生成豆瓣条目信息） 和 object-cache.php（用于外部对象缓存）。

其他能用代码集成到 function.php 文件中的都用代码替代插件了。

## 主题

一开始我是基于 WordPress 官方默认主题 Twenty Twelve 进行修改的，但后面看到有一款修改程度更好的成品——[Twenty Twelve 木头人修改精简版](https://xuv.cc/1)，就在它的基础上继续修改。

所以有想法的朋友可以直接使用上面提到的成品主题，或者继续看我的内容。

我修改的最终版本：[2012-huhexian](https://github.com/huhexian/2012-huhexian)

### 首页右上角图片

先在 header.php 加入下列代码：

```php
<a href="https://yinji.org/" title="回到首页"><img src="https://dogefs.s3.ladydaily.com/lucy/storage/1680832936501.png" alt="胡鹤仙"width="70" height="70"/></a>
```

具体位置大概在 `<hgroup>`下方，上述内容请替换为自己的网址。

然后在 style.css 中加入样式代码：

```css
/*顶部图片*/
.site-header hgroup{position: relative;}
.site-header hgroup img{position: absolute;right: 0;}
@media (max-width: 650px) {
.site-header hgroup img{ display:none}
}
```

### 标签云

```css
/* 标签云样式修改 */ 
 .tagcloud {
     overflow:hidden;
     line-height:20px;
 }
 .tagcloud a {
    font-size: 13px!important;
    padding: 3px;
    margin-right: 3px;
    float: left;
    display: block;
 }
 .tagcloud a:not(.dots):hover {
     background-color: #336699;
     color: #FFFFFF;
     border:0;
 }
```

### 引用

```css
/*引用*/
.entry-content blockquote,
.comment-content blockquote
{
    background-image: url(data:image/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBzdGFuZGFsb25lPSJubyI/PjwhRE9DVFlQRSBzdmcgUFVCTElDICItLy9XM0MvL0RURCBTVkcgMS4xLy9FTiIgImh0dHA6Ly93d3cudzMub3JnL0dyYXBoaWNzL1NWRy8xLjEvRFREL3N2ZzExLmR0ZCI+PHN2ZyB0PSIxNTg1NTQxNjE3MDQ5IiBjbGFzcz0iaWNvbiIgdmlld0JveD0iMCAwIDEwMjQgMTAyNCIgdmVyc2lvbj0iMS4xIiB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHAtaWQ9IjM3MTgiIHdpZHRoPSIzMiIgaGVpZ2h0PSIzMiIgeG1sbnM6eGxpbms9Imh0dHA6Ly93d3cudzMub3JnLzE5OTkveGxpbmsiPjxkZWZzPjxzdHlsZSB0eXBlPSJ0ZXh0L2NzcyI+PC9zdHlsZT48L2RlZnM+PHBhdGggZD0iTTQwNi41NTcyNTcgMTE4LjUzNTMxNHYxMzcuOTAzNTQzYy04Ny4xNDI0IDE5Ljk1MzM3MS0xMjguODkyMzQzIDc0LjQ3NDA1Ny0xMzQuMzYzNDI4IDE3Ni4wMTA5NzJoMTM0LjM2MzQyOHYzMjYuNzQzNzcxSDExNC4yOTMwMjlWNDkwLjUxMDYyOWMwLTE5NC4xNzk2NTcgODMuNDk5ODg2LTM0My4wMTA3NDMgMjkyLjI2NDIyOC0zNzEuOTc1MzE1bTAtNTguNTE0Mjg1Yy0yLjY3NzAyOSAwLTUuMzU0MDU3IDAuMTkwMTcxLTguMDQ1NzE0IDAuNTU1ODg1QzE3Ny41MDMwODYgOTEuMjM4NCA1NS43Nzg3NDMgMjQzLjkzMTQyOSA1NS43Nzg3NDMgNDkwLjUxMDYyOXYyNjguNjY4MzQyYTU4LjUxNDI4NiA1OC41MTQyODYgMCAwIDAgNTguNTE0Mjg2IDU4LjUxNDI4NmgyOTIuMjY0MjI4YTU4LjUxNDI4NiA1OC41MTQyODYgMCAwIDAgNTguNTE0Mjg2LTU4LjUxNDI4NlY0MzIuNDQ5ODI5YTU4LjUxNDI4NiA1OC41MTQyODYgMCAwIDAtNTguNTE0Mjg2LTU4LjUxNDI4NmgtNjQuNTI2NjI4YzE0LjQ1MzAyOS0zNy42MTAwNTcgNDEuNDI4MTE0LTUyLjE4MDExNCA3Ny41ODk5NDItNjAuNDU5ODg2YTU4LjUxNDI4NiA1OC41MTQyODYgMCAwIDAgNDUuNDUwOTcyLTU3LjAzNjhWMTE4LjUzNTMxNGE1OC41MTQyODYgNTguNTE0Mjg2IDAgMCAwLTU4LjUxNDI4Ni01OC41MTQyODV6TTkwOS43MDY5NzEgMjY0LjgyMTAyOXYxMzcuOTAzNTQyYy04Ny4xMTMxNDMgMTkuOTUzMzcxLTEyOC44NjMwODYgNzQuNDc0MDU3LTEzNC4zMzQxNzEgMTc2LjAxMDk3MmgxMzQuMzM0MTcxdjMyNi43NDM3NzFINjE3LjQ0Mjc0M1Y2MzYuNzk2MzQzYzAtMTk0LjE3OTY1NyA4My41MTQ1MTQtMzQzLjAxMDc0MyAyOTIuMjY0MjI4LTM3MS45NzUzMTRtMC01OC41MTQyODZjLTIuNjc3MDI5IDAtNS4zNTQwNTcgMC4xOTAxNzEtOC4wNDU3MTQgMC41NTU4ODYtMjIxLjAwODQ1NyAzMC42NzYxMTQtMzQyLjczMjggMTgzLjM1NDUxNC0zNDIuNzMyOCA0MjkuOTQ4MzQydjI2OC42NjgzNDNhNTguNTE0Mjg2IDU4LjUxNDI4NiAwIDAgMCA1OC41MTQyODYgNTguNTE0Mjg2aDI5Mi4yNjQyMjhhNTguNTE0Mjg2IDU4LjUxNDI4NiAwIDAgMCA1OC41MTQyODYtNTguNTE0Mjg2VjU3OC43MzU1NDNhNTguNTE0Mjg2IDU4LjUxNDI4NiAwIDAgMC01OC41MTQyODYtNTguNTE0Mjg2aC02NC40OTczNzFjMTQuNDUzMDI5LTM3LjYxMDA1NyA0MS40MTM0ODYtNTIuMTgwMTE0IDc3LjU3NTMxNC02MC40NTk4ODZhNTguNTE0Mjg2IDU4LjUxNDI4NiAwIDAgMCA0NS40MzYzNDMtNTcuMDM2OHYtMTM3LjkwMzU0MmE1OC41NDM1NDMgNTguNTQzNTQzIDAgMCAwLTU4LjUxNDI4Ni01OC41MTQyODZ6IiBmaWxsPSIjY2YzZjc0IiBwLWlkPSIzNzE5Ij48L3BhdGg+PHBhdGggZD0iTTM1OS42MTQxNzEgNjY2LjU1MDg1N2ExNC42Mjg1NzEgMTQuNjI4NTcxIDAgMCAxLTE0LjYyODU3MS0xNC42Mjg1NzFWNDkxLjI3MTMxNGgtNjguMDgxMzcxYTE0LjYyODU3MSAxNC42Mjg1NzEgMCAxIDEgMC0yOS4yNTcxNDNoODcuNzcxNDI4YzguMDg5NiAwIDkuNTY3MDg2IDYuMjkwMjg2IDkuNTY3MDg2IDE0LjM2NTI1OHYxNzUuNTQyODU3YTE0LjYyODU3MSAxNC42Mjg1NzEgMCAwIDEtMTQuNjI4NTcyIDE0LjYyODU3MXpNODcxLjYxNDE3MSA4NDIuMDkzNzE0YTE0LjYyODU3MSAxNC42Mjg1NzEgMCAwIDEtMTQuNjI4NTcxLTE0LjYyODU3MXYtMjkuMjU3MTQzYTE0LjYyODU3MSAxNC42Mjg1NzEgMCAxIDEgMjkuMjU3MTQzIDB2MjkuMjU3MTQzYTE0LjYyODU3MSAxNC42Mjg1NzEgMCAwIDEtMTQuNjI4NTcyIDE0LjYyODU3MXpNODcxLjYxNDE3MSA3NTQuMzIyMjg2YTE0LjYyODU3MSAxNC42Mjg1NzEgMCAwIDEtMTQuNjI4NTcxLTE0LjYyODU3MnYtMTAyLjEzNjY4NWgtNjguMDgxMzcxYTE0LjYyODU3MSAxNC42Mjg1NzEgMCAxIDEgMC0yOS4yNTcxNDNoODcuNzcxNDI4YzguMDg5NiAwIDkuNTY3MDg2IDYuMjkwMjg2IDkuNTY3MDg2IDE0LjM2NTI1N3YxMTcuMDI4NTcxYTE0LjYyODU3MSAxNC42Mjg1NzEgMCAwIDEtMTQuNjI4NTcyIDE0LjYyODU3MnoiIGZpbGw9IiNjZjNmNzQiIHAtaWQ9IjM3MjAiPjwvcGF0aD48L3N2Zz4=);
    background-repeat: no-repeat;
    color: rgba(0,0,0,.7);
    margin-top: 0;
    margin-bottom: 15px;
    margin-left: 0;
    margin-right: 0;
    padding: 20px 20px 20px 60px;
    position: relative;}
```

### 头像转动

```css
/*头像转动*/
.avatar{-webkit-transition:0.4s;-webkit-transition:-webkit-transform 0.4s ease-out;transition:transform 0.4s ease-out;-moz-transition:-moz-transform 0.4s ease-out;}
.avatar:hover{transform:rotateZ(360deg);-webkit-transform:rotateZ(360deg);-moz-transform:rotateZ(360deg);}
```

### 调整网页宽度

```css
/* 网页宽度 */
 .site {
     margin: 0 auto;
       max-width: 960px;
     overflow: hidden;
 }
html {
    margin-top: 32px !important;
}
```

### 小工具及首页文章标题下划线

```css
/* 小工具标题字体样式以及下横线 */
 .widget-title {
     font-size: 18px;
     font-weight: normal;
     color: #21759b;
     border-bottom: 1px solid #ededed;
 }
/* 首页文章标题行高以及下横线 */
 .entry-header .entry-title {
     line-height: 2.181818182;
     border-bottom: 1px solid #ededed;
 }
```

### 二级、三级标题样式

```css
/*标题样式*/
.entry-content h2, .comment-content h2, .mu_register h2 {
    font-weight: bold;
    background-color: #f6f6f6;
    margin: 20px 0;
    border-bottom: 0px solid #21759b;
    padding: 5px 12px;
    border-left: 5px solid #21759b;
}

.entry-content h3, .comment-content h3, .mu_register h3 {
    font-weight: bold;
    background-color: #f6f6f6;
    margin: 20px 0;
    border-bottom: 0px solid #53a7dc;
    padding: 0px 12px;
    border-left: 5px solid #53a7dc;
}
```

### 归档页面样式修改

```css
#archives {
    position: relative;
}

#archives h3 {
    margin-bottom: 0;
    padding: 0 15px;
    border-bottom: 1px solid #ddd;
    font-size: 20px;
    font-weight: 400;
    text-align: center;
    letter-spacing: 5px
}

#archives ul {
    list-style: none;
    margin: 0 30px;
    padding: 10px 0 20px 10px;
    border-left: 1px solid #ddd;
    font-size: 18px
}

#archives li {
    list-style: none;
    position: relative;
    line-height: 30px
}

#archives ul ul {
    margin: -15px 0 0 0;
    padding: 15px 0 10px 0
}

#archives ul ul li {
    padding: 0 0 0 15px
}

#archives ul ul li:before {
    content: "";
    position: absolute;
    left: 0;
    top: 10px;
    border-top: 5px dashed transparent;
    border-bottom: 5px dashed transparent;
    border-left: 10px solid #ddd
}

#al_expand_collapse {
    display: inline-block;
    line-height: 24px;
    padding: 0 10px;
    color: #fff;
    font-size: 12px;
    text-decoration: none;
    background: linear-gradient(to bottom, #4caf50 20%, #388e3c 80%) repeat scroll 0 0 transparent;/*这个颜色和下面的我都做了一些修改*/
    background: -webkit-linear-gradient(to bottom, #4caf50 20%, #388e3c 80%) repeat scroll 0 0 transparent
}

#al_expand_collapse:hover {
    background: linear-gradient(to bottom, #388e3c 20%, #4caf50 80%) repeat scroll 0 0 transparent;
    background: -webkit-linear-gradient(to bottom, #388e3c 20%, #4caf50 80%) repeat scroll 0 0 transparent
}

#archives em {
    padding-left: 5px;
    font-size: 12px;
    color: #777
}

#archives .al_mon {
    padding-left: 5px;
    font-size: 14px;
    font-weight: 700
}

#archives .al_mon:after {
    content: "";
    position: absolute;
    left: -10px;
    top: 15px;
    width: 10px;
    height: 1px;
    background: #ddd
}

#archives .al_mon em {
    font-size: 12px;
    font-weight: 400
}
```

### 添加面包屑导航

在 functions.php 中加入下列代码：

```php
// 面包屑导航
function breadcrumb() {
  // Check if is front/home page, return
  if ( is_front_page() ) {
    return;
  }
  // Define
  global $post;
  $custom_taxonomy  = ''; // If you have custom taxonomy place it here
  $defaults = array(
    'seperator'   =>  ' / ',
    'id'          =>  'breadcrumb',
    'classes'     =>  'breadcrumb',
    'home_title'  =>  esc_html__( '⚐ Home', '' )
  );
  $sep  = '<li class="seperator">'. esc_html( $defaults['seperator'] ) .'</li>';
  // Start the breadcrumb with a link to your homepage
  echo '<ul id="'. esc_attr( $defaults['id'] ) .'" class="'. esc_attr( $defaults['classes'] ) .'">';
  // Creating home link
  echo '<li class="item"><a href="'. get_home_url() .'">'. esc_html( $defaults['home_title'] ) .'</a></li>' . $sep;
  if ( is_single() ) {
    // Get posts type
    $post_type = get_post_type();
    // If post type is not post
    if( $post_type != 'post' ) {
      $post_type_object   = get_post_type_object( $post_type );
      $post_type_link     = get_post_type_archive_link( $post_type );
      echo '<li class="item item-cat"><a href="'. $post_type_link .'">'. $post_type_object->labels->name .'</a></li>'. $sep;
    }
    // Get categories
    $category = get_the_category( $post->ID );
    // If category not empty
    if( !empty( $category ) ) {
      // Arrange category parent to child
      $category_values      = array_values( $category );
      $get_last_category    = end( $category_values );
      // $get_last_category    = $category[count($category) - 1];
      $get_parent_category  = rtrim( get_category_parents( $get_last_category->term_id, true, ',' ), ',' );
      $cat_parent           = explode( ',', $get_parent_category );
      // Store category in $display_category
      $display_category = '';
      foreach( $cat_parent as $p ) {
        $display_category .=  '<li class="item item-cat">'. $p .'</li>' . $sep;
      }
    }
    // If it's a custom post type within a custom taxonomy
    $taxonomy_exists = taxonomy_exists( $custom_taxonomy );
    if( empty( $get_last_category ) && !empty( $custom_taxonomy ) && $taxonomy_exists ) {
      $taxonomy_terms = get_the_terms( $post->ID, $custom_taxonomy );
      $cat_id         = $taxonomy_terms[0]->term_id;
      $cat_link       = get_term_link($taxonomy_terms[0]->term_id, $custom_taxonomy);
      $cat_name       = $taxonomy_terms[0]->name;
    }
    // Check if the post is in a category
    if( !empty( $get_last_category ) ) {
      echo $display_category;
      echo '<li class="item item-current">'. get_the_title() .'</li>';
    } else if( !empty( $cat_id ) ) {
      echo '<li class="item item-cat"><a href="'. $cat_link .'">'. $cat_name .'</a></li>' . $sep;
      echo '<li class="item-current item">'. get_the_title() .'</li>';
    } else {
      echo '<li class="item-current item">'. get_the_title() .'</li>';
    }
  } else if( is_archive() ) {
    if( is_tax() ) {
      // Get posts type
      $post_type = get_post_type();
      // If post type is not post
      if( $post_type != 'post' ) {
        $post_type_object   = get_post_type_object( $post_type );
        $post_type_link     = get_post_type_archive_link( $post_type );
        echo '<li class="item item-cat item-custom-post-type-' . $post_type . '"><a href="' . $post_type_link . '">' . $post_type_object->labels->name . '</a></li>' . $sep;
      }
      $custom_tax_name = get_queried_object()->name;
      echo '<li class="item item-current">'. $custom_tax_name .'</li>';
    } else if ( is_category() ) {
      $parent = get_queried_object()->category_parent;
      if ( $parent !== 0 ) {
        $parent_category = get_category( $parent );
        $category_link   = get_category_link( $parent );
        echo '<li class="item"><a href="'. esc_url( $category_link ) .'">'. $parent_category->name .'</a></li>' . $sep;
      }
      echo '<li class="item item-current">'. single_cat_title( '', false ) .'</li>';
    } else if ( is_tag() ) {
      // Get tag information
      $term_id        = get_query_var('tag_id');
      $taxonomy       = 'post_tag';
      $args           = 'include=' . $term_id;
      $terms          = get_terms( $taxonomy, $args );
      $get_term_name  = $terms[0]->name;
      // Display the tag name
      echo '<li class="item-current item">'. $get_term_name .'</li>';
    } else if( is_day() ) {
      // Day archive
      // Year link
      echo '<li class="item-year item"><a href="'. get_year_link( get_the_time('Y') ) .'">'. get_the_time('Y') . '年</a></li>' . $sep;
      // Month link
      echo '<li class="item-month item"><a href="'. get_month_link( get_the_time('Y'), get_the_time('m') ) .'">'. get_the_time('M') .'</a></li>' . $sep;
      // Day display
      echo '<li class="item-current item">'. get_the_time('jS') .' '. get_the_time('M'). '</li>';
    } else if( is_month() ) {
      // Month archive
      // Year link
      echo '<li class="item-year item"><a href="'. get_year_link( get_the_time('Y') ) .'">'. get_the_time('Y') . '年</a></li>' . $sep;
      // Month Display
      echo '<li class="item-month item-current item">'. get_the_time('M') .'</li>';
    } else if ( is_year() ) {
      // Year Display
      echo '<li class="item-year item-current item">'. get_the_time('Y') .'年</li>';
    } else if ( is_author() ) {
      // Auhor archive
      // Get the author information
      global $author;
      $userdata = get_userdata( $author );
      // Display author name
      echo '<li class="item-current item">'. 'Author: '. $userdata->display_name . '</li>';
    } else {
      echo '<li class="item item-current">'. post_type_archive_title() .'</li>';
    }
  } else if ( is_page() ) {
    // Standard page
    if( $post->post_parent ) {
      // If child page, get parents
      $anc = get_post_ancestors( $post->ID );
      // Get parents in the right order
      $anc = array_reverse( $anc );
      // Parent page loop
      if ( !isset( $parents ) ) $parents = null;
      foreach ( $anc as $ancestor ) {
        $parents .= '<li class="item-parent item"><a href="'. get_permalink( $ancestor ) .'">'. get_the_title( $ancestor ) .'</a></li>' . $sep;
      }
      // Display parent pages
      echo $parents;
      // Current page
      echo '<li class="item-current item">'. get_the_title() .'</li>';
    } else {
      // Just display current page if not parents
      echo '<li class="item-current item">'. get_the_title() .'</li>';
    }
  } else if ( is_search() ) {
    // Search results page
    echo '<li class="item-current item">Search results for: '. get_search_query() .'</li>';
  } else if ( is_404() ) {
    // 404 page
    echo '<li class="item-current item">' . 'Error 404' . '</li>';
  }
  // End breadcrumb
  echo '</ul>';
}
```

然后在 header.php 末尾添加下列代码：

```php
<?php// 文章页面添加面包屑导航
if ( function_exists('breadcrumb') ) breadcrumb();
?>
```

最后添加样式代码：

```css
/* 面包屑导航样式 */
 .breadcrumb {
     font-size: 12px;
     color: #888;
     margin:0 auto;
 }
 .breadcrumb a {
     color: #888;
 }
 .breadcrumb a:not(.dots):hover {
     color: #CC0033;
 }
 .breadcrumb li {
     display: inline;
     line-height:20px;
 }
```

### 首页文章标题、正文标题下方添加元素

其中有一个用于统计每篇文章的字数的代码，需要添加到 functions.php 文件中。

```php
//字数统计
function zm_count_words ($text) {
    global $post;
    $output='';
    if (empty($text)) {
        $text = $post->post_content;
        if (mb_strlen($output, 'UTF-8') < mb_strlen($text, 'UTF-8')) $output .= '<span class="word-count">共' . mb_strlen(preg_replace('/\s/','',html_entity_decode(strip_tags($post->post_content))),'UTF-8') .'字</span>';
        return $output;
    }
}
```

打开 content.php，找到以下代码：

```php
<?php if ( is_single() ) : ?>
<h1 class="entry-title"><?php the_title(); ?></h1>
<?php else : ?>
```

然后在 `<?php else: ?>` 的上面添加以下代码：

```php
<p class="meta"><!--文章页标题下标签-->
Auth:<?php the_author_nickname(); ?>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
Date:<?php echo the_time('Y/m/j'); ?>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
Cat:<?php the_category('、'); ?>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
Word:<?php echo zm_count_words($text); ?>
</p>
```

在 content.php 找到`<footer></footer>`，将这两个标签内（包括这两个标签）的所有内容删除，并替换为以下代码：

```php
<?php if ( is_single() ) : ?>
            <footer class="content-foot"><!--文章页脚部显示修改-->
                <?php the_tags('⚑Tags：','、'); ?>&nbsp&nbsp&nbsp&nbsp&nbsp&nbsp
            </footer><!-- .content-foot -->
        <?php else : ?>
            <footer class="home-foot"><!--除文章页脚部显示修改-->
                ◷<?php echo the_time('Y/m/j'); ?>&nbsp&nbsp
                @<?php the_author_nickname(); ?>&nbsp&nbsp
                ▤<?php the_category('、'); ?>&nbsp&nbsp
                ⚑<?php the_tags('','、'); ?>
                <?php edit_post_link( __( '——编辑', 'twentytwelve-child' ), '<span class="edit-link">', '</span>' ); ?>
            </footer><!-- .entry-meta -->
        <?php endif;  // is_single() ?>
```

最后添加样式代码：

```css
/* 文章页标题、meta块、和脚部样式修改 */
#content .title {
    font-size: 24px;
    padding-bottom: 24px;
    text-align: center;
}
#content .meta {
    font-size: 13px;
    padding: 10px 0 10px 0;
    border: 1px dashed rgba(0, 0, 0, 0.15);
    text-align: center;
    letter-spacing: 0.035rem;
}
#content .content-foot {
    font-size: 13px;
    padding: 10px 0 10px 24px;
    margin: 0 -24px -24px -24px;
    letter-spacing: 0.035rem;
    background-color: #ededed;
}
```

### 禁止加载语言包

在 functions.php 中加入下列代码：

```php
//关闭翻译
add_filter('locale', function($locale) {
    $locale = ( is_admin() ) ? $locale : 'en_US';
    return $locale;
});
```

### 为摘要添加“继续阅读”字样

```php
//为摘要添加继续阅读字样
// Remove the ... from excerpt and change the text
function change_excerpt_more()
{
function new_excerpt_more($more)
{
// Use .read-more to style the link
return '......<span class="read-more"> <a href="' . get_permalink($post->ID) . '"><br/><br/>继续阅读»»»</a></span>';
}
add_filter('excerpt_more', 'new_excerpt_more');
}
add_action('after_setup_theme', 'change_excerpt_more');
```

### 页面添加 html 后缀

```php
//WordPress页面链接添加html后缀
function html_page_permalink() {
global $wp_rewrite;
if ( !strpos($wp_rewrite->get_page_permastruct(), '.html')){
$wp_rewrite->page_structure = $wp_rewrite->page_structure . '.html';
}
}
add_action('init', 'html_page_permalink', -1);
```

### 修改全局字体

我采用的是开源字体——[霞鹜文楷](https://github.com/lxgw/LxgwWenKai)。在 header.php 添加下列代码：

```php
<!-- Screen version -->
<link rel="stylesheet" href="https://npm.elemecdn.com/lxgw-wenkai-screen-webfont@1.1.0/style.css" />
  <style>
    body {
      /* Screen version */
      font-family: "LXGW WenKai Screen", sans-serif;
    }
  </style>
```

### 网站统计小工具

在主题目录新建文件 **widget-websitestat.php**，并添加下列内容。

```php
<?php
// WordPress统计信息小工具

// 定义小工具的类 EfanWebsitestat
class EfanWebsitestat extends WP_Widget{

  function __construct(){
    // 定义小工具的构造函数
    $widget_ops = array('classname' => 'widget_Websitestat', 'description' => '显示网站的统计信息');
//     $this->WP_Widget(false, '网站统计', $widget_ops);
    parent::__construct( false, '网站统计', $widget_ops);
  }

  function form($instance){
    // 表单函数,控制后台显示
    // $instance 为之前保存过的数据
    // 如果之前没有数据的话,设置默认量
    $instance = wp_parse_args(
      (array)$instance,
      array(
        'title' => '网站信息统计',
        'establish_time' => '2021-01-01'
      )
    );

    $title = htmlspecialchars($instance['title']);
    $establish_time = htmlspecialchars($instance['establish_time']);

    // 表格布局输出表单
    $output = '<table>';
    $output .= '<tr><td>标题</td><td>';
    $output .= '<input id="'.$this->get_field_id('title') .'" name="'.$this->get_field_name('title').'" type="text" value="'.$instance['title'].'" />';
    $output .= '</td></tr><tr><td>建站时间：</td><td>';   
    $output .= '<input id="'.$this->get_field_id('establish_time') .'" name="'.$this->get_field_name('establish_time').'" type="text" value="'.$instance['establish_time'].'" />';   
    $output .= '</td></tr></table>';  
    echo $output;   
  }

  function update($new_instance, $old_instance){
    // 更新数据的函数
    $instance = $old_instance;
    // 数据处理
    $instance['title'] = strip_tags(stripslashes($new_instance['title']));
    $instance['establish_time'] = strip_tags(stripslashes($new_instance['establish_time']));
    return $instance;
  }

  function widget($args, $instance){
    extract($args); //展开数组
    $title = apply_filters('widget_title',empty($instance['title']) ? ' ' : $instance['title']);
    $establish_time = empty($instance['establish_time']) ? '2021-01-01' : $instance['establish_time'];
    echo $before_widget;
    echo $before_title . $title . $after_title;
    echo '<div class="widgest-boys"><ul>';
    $this->efan_get_websitestat($establish_time);
    echo '</ul></div>';
    echo $after_widget;
  }

  function efan_get_websitestat($establish_time){
    // 相关数据的获取
    global $wpdb;
    $count_posts = wp_count_posts();
    $published_posts = $count_posts->publish;
    $comments_count = $wpdb->get_var("SELECT COUNT(*) FROM $wpdb->comments");
    $time = floor((time()-strtotime($establish_time))/86400);
    $count_tags = wp_count_terms('post_tag');
    $count_pages = wp_count_posts('page');
    $link = $wpdb->get_var("SELECT COUNT(*) FROM $wpdb->links WHERE link_visible = 'Y'"); 
    $users = $wpdb->get_var("SELECT COUNT(ID) FROM $wpdb->users");
    $last = $wpdb->get_results("SELECT MAX(post_modified) AS MAX_m FROM $wpdb->posts WHERE (post_type = 'post' OR post_type = 'page') AND (post_status = 'publish' OR post_status = 'private')");
    $last = date('Y-m-d', strtotime($last[0]->MAX_m));
    $total_views = $wpdb->get_var("SELECT SUM(meta_value+0) FROM $wpdb->postmeta WHERE meta_key = 'views'");  
    // 显示数据
    $output = '<div class="widgest-bg widgest-bg1 wb-top"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-snowflake-o" aria-hidden="true"></i> 文章总数：';
    $output .= $published_posts;
    $output .= ' 篇</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg2"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-paper-plane-o" aria-hidden="true"></i> 评论数目：';
    $output .= $comments_count;
    $output .= ' 条</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg3"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-star-o" aria-hidden="true"></i> 标签总数：';
    $output .= $count_tags;
    $output .= ' 个</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg4"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-pie-chart" aria-hidden="true"></i> 浏览次数：';
    $output .= $total_views;
    $output .= ' 次</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg5"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-link" aria-hidden="true"></i> 友链总数：';
    $output .= $link;
    $output .= ' 个</li></div></div></div>';

    $output .= '<div class="widgest-bg widgest-bg7"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-refresh" aria-hidden="true"></i> 运行天数：';
    $output .= $time;
    $output .= ' 天</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg8"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-calendar" aria-hidden="true"></i> 建站时间：';
    $output .= $establish_time;
    $output .= '</li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg9"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-clock-o" aria-hidden="true"></i> 最后更新：';
    $output .= $last;
    $output .= '</li></div></div></div>';
    //   页面生成耗时+数据库查询  
    $output .= '<div class="widgest-bg widgest-bg10"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-podcast" aria-hidden="true"></i> 数据查询：';
    $output .= get_num_queries();
    $output .= ' 次 </li></div></div></div>';
    $output .= '<div class="widgest-bg widgest-bg11 wb-bottom"><div class="widgest-main"><div class="widgest-meat"><li><i class="fa fa-hourglass-half" aria-hidden="true"></i> 生成耗时：';
    $output .= timer_stop(0,5);
    $output .= '秒</li></div></div></div>';
    echo $output;
  }
}

function EfanWebsitestat(){
  // 注册小工具
  register_widget('EfanWebsitestat');
}

add_action('widgets_init','EfanWebsitestat');

?>
```

然后在 functions.php 文件中加入下列代码。

```php
//添加站点统计小工具
include("widget-websitestat.php");
```

网站后台添加小工具即可。

### 写完哪本书了？

详见文章《[ChatGPT 帮我写代码，实现“已写完哪本书”统计](https://yinji.org/4901.html)》

* * *

大致就是以上这些，具体还有一些小细节，我直接在 style.css 对照审查元素进行修改了，没有记录，需要的可以下载文件，对照我博客进行修改。

参考文章：

- 《[WordPress建站，twenty twelve子主题修改全记录](https://www.bgbiji.com/701.html)》
- 《[WordPress 经典主题 TwentyTwelve 木头人修改精简版](https://xuv.cc/1)》

## 下载地址

- 我修改的：[GitHub](https://github.com/huhexian/2012-huhexian)
- 木头人修改版：[蓝奏网盘](https://pan.lanzouw.com/ilrtz0uyd82d)
