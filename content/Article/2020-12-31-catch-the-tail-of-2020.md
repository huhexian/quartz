---
title: "抓住2020的尾巴"
date: 2020-12-31
categories: 
  - "life"
tags: 
  - "2020年"
  - "回顾"
---

这一年过得真TM的快。

经历了年初的疫情、最长的高三寒假，以及史无前例的高考[推迟](http://yinji.org/3013.html)。一眨眼，高三下学期和大一上学期就这样结束了。

2020年或许并没有我们小时候想象的那么美好。曾经在作文里写，2020年是一个特别“科幻”的年代，有许多高科技产品诞生，实际上，经历了这一年，2020年是比较“魔幻”的。直到现在，在抖音上时不时会刷到人们悼念[科比](http://yinji.org/2768.html)的视频，我们还记得科比，还记得吹哨人[李文亮](http://yinji.org/2789.html)医生，钟南山院士，我们还记得国内疫情最严重的时候。

2020年，我度过了我的第十八个[生日](http://yinji.org/2897.html)，家里配置了一个[书桌](http://yinji.org/2906.html)，到高考、高中毕业，暑假和朋友们去了一趟武功山，干了5天的[暑假工](http://yinji.org/3233.html)，九月中旬开学。虽然高考考得不太理想，但也在大学里遇到了她，这就不多说了，小秘密只能我们俩知道。

用**WP Word Count**插件，统计了我2020年所有文章的字数，一年里我总共写了**42**篇文章，共计**38400**字，收到有效评论**1708**条，不过这应该包括了我回复的。比[2019年](http://yinji.org/2931.html)稍微少一点点，今年手写日记也比较少，甚至是很水，往往几笔带过，希望2021年能够再勤奋一点。

热门前十博客文章（即评论数前十）：

| ID | 文章 | 评论 |
| --- | --- | --- |
| 3013 | [写在高考延期之后](http://yinji.org/3013.html) | 97 |
| 2897 | [生日快乐](http://yinji.org/2897.html) | 89 |
| 2931 | [博客两周年](http://yinji.org/2931.html) | 82 |
| 2906 | [许久的愿望](http://yinji.org/2906.html) | 53 |
| 3233 | [暑假工第二天](http://yinji.org/3233.html) | 53 |
| 2778 | [疫情中的人情](http://yinji.org/2778.html) | 51 |
| 2972 | [同青山共云雨](http://yinji.org/2972.html) | 47 |
| 2794 | [“失踪”多年的小学同学](http://yinji.org/2794.html) | 46 |
| 3438 | [海底捞：去过一次不想去第二次](http://yinji.org/3438.html) | 45 |
| 3321 | [扯淡集（四）](http://yinji.org/3321.html) | 43 |

正好豆瓣给我推送了2020年影音书报告，顺便统计下看过的书和电影。

和女朋友在电影院看了《[金刚川](http://yinji.org/3335.html)》和《一秒钟》，和高中同学在电影院看了《[姜子牙](http://yinji.org/3299.html)》，和家里人在电影院看了《多力特的奇幻冒险》，基本上在电影院里看的就这四部。

《澳门风云1-4》、《反贪风暴1-4》、《犯罪现场》、《危城》、《one day》、《无间道1》、《叶问4》、《美味侦探》、《扫毒1-2》、《误杀》、《蜘蛛侠：英雄远征》、《一出好戏》、《少林寺十八罗汉》、《调音师》、《木乃伊3》、《中国机长》、《我和我的祖国》、《攀登者》、《双子杀手》、《囧妈》、《东方快车谋杀案》

《白说》、《[自在独行：贾平凹的独行世界](http://yinji.org/3244.html)》、《菊次郎与佐纪》、《[一往无前 : 雷军亲述小米热血10年](http://yinji.org/3294.html)》、《显微镜下的大明》、《品人录》、《马化腾：先人一步》、《有话说》

一对比，书看得很少，这离我对自己的要求也还很远，2021年加把劲。

分享下来自[小赖子](https://justyy.com/)的SQL查询语句

获取这一年博文发表数的SQL：

```
SELECT 
  Count(1) 
FROM 
  `wp_posts` 
WHERE 
  date_format(`post_date_gmt`, "%Y") = '2020' and 
  `post_type` = 'post' and 
  `post_status` = 'publish'
```

获取这一年评论发表数的SQL：

```
SELECT 
  Count(1) 
FROM 
  `wp_comments` 
WHERE 
  date_format(`comment_date`, "%Y") = '2020' and 
  `comment_approved` = '1'
```

根据以下SQL来获得评论最多的10篇博文：

```
SELECT 
  `id`, `post_title`, `comment_count`
FROM
   `wp_posts` 
WHERE 
  date_format(`post_date_gmt`, "%Y") = '2020' and 
  `post_type` = 'post' and 
  `post_status` = 'publish' 
ORDER BY
  `comment_count` DESC
LIMIT 10
```

最后的最后，新年快乐。
