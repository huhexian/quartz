---
title: "ChatGPT 帮我写代码，实现“已写完哪本书”统计"
date: 2023-04-17
categories: 
  - "play-everything"
tags: 
  - "chatgpt"
---

我算是第一批用上 [ChatGPT](https://chat.openai.com) 的人群，去年12月就已经注册好了。到目前为止，我用它帮我写过调查问卷、日常作业，也会问一些奇奇怪怪的问题。昨天利用它，帮我写了一段 WordPress 的代码。

起初是在林木木的博客里看到他写《[已写完了哪本书](https://immmmm.com/what-book-i-write/)》 ，原理我懂，获取全站所有文章的字数，然后看你字数在哪个区间，便输出对应字数的书籍，奈何人家使用的是 Hugo，我便问他如果用在 WordPress 上需要如何修改，他给了我 Typecho 的修改版本，具体看《[博客全站总字数统计](https://www.jdeal.cn/152.html)》。又难倒我了，我随即向 ChatGPT 寻求帮助。

我先将林木木博客的代码发给它，解释了一遍代码原理。

![](images/20230417084350.png)

随后，我让它将此代码修改为 WordPress 可用的版本，但是写出来似乎不起作用。我就给它发送 Typecho 的版本进行修改，同样也给我解释了代码的原理。

![](images/20230417084410.png)

最后，再要求它基于上述代码，修改为 WordPress 可用的版本，虽然由于字数限制，它无法一次性生成全部代码，但好在成功了。

![](images/20230417084440.png)

我将完整代码贴出来，并说明用法。

```php
/*
 * 输出全站字数，并匹配书籍
 * 原作者：林木木
 * 修改者：胡鹤仙&ChatGPT
 */
function allwords() {
    global $wpdb;
    $chars = 0;
    $results = $wpdb->get_results("SELECT post_content FROM {$wpdb->posts} WHERE post_status = 'publish' AND post_type = 'post'");
    foreach ($results as $result) { $chars += mb_strlen(trim($result->post_content), 'UTF-8'); }
    if($chars<50000){
    echo '全站共 '.$chars.' 字，还在努力更新中..加油！加油啦！';}
    elseif ($chars<70000 && $chars>50000){
    echo '全站共 '.$chars.' 字，写完一本埃克苏佩里的《小王子》了！';}
    elseif ($chars<90000 && $chars>70000){
    echo '全站共 '.$chars.' 字，写完一本鲁迅的《呐喊》了！';}
    elseif ($chars<100000 && $chars>90000){
    echo '全站共 '.$chars.' 字，写完一本林海音的《城南旧事》了！';}
    elseif ($chars<110000 && $chars>100000){
    echo '全站共 '.$chars.' 字，写完一本马克·吐温的《王子与乞丐》了！';}
    elseif ($chars<120000 && $chars>110000){
    echo '全站共 '.$chars.' 字，写完一本鲁迅的《彷徨》了！';}
    elseif ($chars<130000 && $chars>120000){
    echo '全站共 '.$chars.' 字，写完一本余华的《活着》了！';}
    elseif ($chars<140000 && $chars>130000){
    echo '全站共 '.$chars.' 字，写完一本曹禺的《雷雨》了！';}
    elseif ($chars<150000 && $chars>140000){
    echo '全站共 '.$chars.' 字，写完一本史铁生的《宿命的写作》了！';}
    elseif ($chars<160000 && $chars>150000){
    echo '全站共 '.$chars.' 字，写完一本伯内特的《秘密花园》了！';}
    elseif ($chars<170000 && $chars>160000){
    echo '全站共 '.$chars.' 字，写完一本曹禺的《日出》了！';}
    elseif ($chars<180000 && $chars>170000){
    echo '全站共 '.$chars.' 字，写完一本马克·吐温的《汤姆·索亚历险记》了！';}
    elseif ($chars<190000 && $chars>180000){
    echo '全站共 '.$chars.' 字，写完一本沈从文的《边城》了！';}
    elseif ($chars<200000 && $chars>190000){
    echo '全站共 '.$chars.' 字，写完一本亚米契斯的《爱的教育》了！';}
    elseif ($chars<210000 && $chars>200000){
    echo '全站共 '.$chars.' 字，写完一本巴金的《寒夜》了！';}
    elseif ($chars<220000 && $chars>210000){
    echo '全站共 '.$chars.' 字，写完一本东野圭吾的《解忧杂货店》了！';}
    elseif ($chars<230000 && $chars>220000){
    echo '全站共 '.$chars.' 字，写完一本莫泊桑的《一生》了！';}
    elseif ($chars<250000 && $chars>230000){
    echo '全站共 '.$chars.' 字，写完一本简·奥斯汀的《傲慢与偏见》了！';}
    elseif ($chars<280000 && $chars>250000){
    echo '全站共 '.$chars.' 字，写完一本钱钟书的《围城》了！';}
    elseif ($chars<300000 && $chars>280000){
    echo '全站共 '.$chars.' 字，写完一本张炜的《古船》了！';}
    elseif ($chars<310000 && $chars>300000){
    echo '全站共 '.$chars.' 字，写完一本茅盾的《子夜》了！';}
    elseif ($chars<320000 && $chars>310000){
    echo '全站共 '.$chars.' 字，写完一本阿来的《尘埃落定》了！';}
    elseif ($chars<340000 && $chars>320000){
    echo '全站共 '.$chars.' 字，写完一本艾米莉·勃朗特的《呼啸山庄》了！';}
    elseif ($chars<350000 && $chars>340000){
    echo '全站共 '.$chars.' 字，写完一本雨果的《巴黎圣母院》了！';}
    elseif ($chars<400000 && $chars>350000){
    echo '全站共 '.$chars.' 字，写完一本东野圭吾的《白夜行》了！';}
    elseif ($chars<1000000 && $chars>400000){
    echo '全站共 '.$chars.' 字，写完一本我国的名著了！';}
    elseif ($chars>1000000){
    echo '全站共 '.$chars.' 字，已写一本列夫·托尔斯泰的《战争与和平》了！';}
}
```

将上述代码添加到主题文件的 function.php 文件中，并在需要调用的地方添加代码。

```php
<?php echo allwords(); ?>
```

我目前是放在了 footer.php 文件中，显示在页面末尾。上述代码可以根据实际情况自由修改，比如字数、书名等等，也可以添加更多的字数区间和书名。以上便是我用 ChatGPT 的过程。效果如下图所示。

![](images/20230417085513.png)

另外，本来想让它继续写一个友情链接页面的模板文件，但试了多次，效果始终不太理想，目前的效果见[友情链接](https://yinji.org/friends.html)页面查看吧，待优化中。
