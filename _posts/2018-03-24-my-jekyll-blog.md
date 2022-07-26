---
layout: post
title: "在Github上搭建免费博客：Jekyll"
tagline: ""
description: ""
category: 博客
tags: [Jekyll]
last_updated:
---


这个博客是用Jekyll搭建在Github Pages上的。根据[阮一峰老师的教程文章](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html)，使用Jekyll+Github Page建立博客的好处主要是：

* 免费，无限流量。
* 享受git的版本管理功能，不用担心文章遗失。
* 你只要用自己喜欢的编辑器和Markdown标注写文章就可以了，其他事情一概不用操心，都由github处理。

而缺点在于：
* 有一定技术门槛，你必须要懂一点git和网页开发。
* 它生成的是静态网页，添加动态功能必须使用外部服务，比如评论功能就只能用disqus。
* 它不适合大型网站，因为没有用到数据库，每运行一次都必须遍历全部的文本文件，网站越大，生成时间越长。

 综合来看，它不失为搭建中小型Blog或项目主页的最佳选项之一。

# 技术细节

我最开始是从阮一峰的介绍([搭建一个免费的，无限流量的Blog----github Pages和Jekyll入门](http://www.ruanyifeng.com/blog/2012/08/blogging_with_jekyll.html))里了解到还有这种轻便的方式实现可以自己高度控制的博客。后来我在网上冲浪的时候遇到了[Verne的博客](http://einverne.github.io/)，非常喜欢他调的[蓝白色简洁模板](einverne.github.io/post/2011/12/jekyll-introduction.html)。这样简洁的模板在保持对超文本标注可读性的同时，最大程度的使非内容的排版、美术形式从读者的眼中消失，保证阅读可以专注于内容。

安装这个Jekyll主要是看[官方的引导](https://jekyllrb.com/docs/installation/#macOS)<https://jekyllrb.com/docs/installation/#macOS>，写的还是非常清晰了。毕竟Jekyll的作者入职了Github。在Mac上安装完之后需要执行 ``` bundle update``` 更新一下gem的组件。我在安装的时候还读了这篇[48 个你需要知道的 Jekyll 使用技巧](https://crispgm.com/page/48-tips-for-jekyll-you-should-know.html)文章学到了不少实用技巧。

## 给我自己看的代码备忘

- 在博客内部超链接另外一篇文章的格式：
  - 链接到我的另外一篇 [post]({{ site.baseurl }}{% post_url 2018-03-24-read-plan-for-2018 %})

``` md
链接到我的另外一篇 [post]( { {  site.baseurl } } { % post_url 2018-03-24-read-plan-for-2018  % } )
```

- 打开本地服务器<http://localhost:4000>实时查看网页编译结果，目录下运行

``` bash
JEKYLL_ENV=production bundle exec jekyll serve -w
```

- 新建Post，Title可为中文，自动转变成拼音

``` bash
rake post title="A Title" [date="2012-02-09"] [tags=[tag1,tag2]] [category="category"]
```

- 新建页面

``` bash
rake page name="about.html"
```

- 插入图片

<img src="{{ site.baseurl }}/images/sep-2018-read-list/breakfast.jpg" alt="Marriage A-la-Mode: The Tête à Tête, William Hogarth, 1743, Oil on Canvas, 69.9 x 90.8 cm, National Gallery, London">
**<center>荷加斯代表作「时髦婚姻：早餐」 Marriage A-la-Mode: The Tête à Tête, William Hogarth, 1743, Oil on Canvas, 69.9 x 90.8 cm, National Gallery, London</center>**

```html
<img src="{{ site.baseurl }}/images/sep-2018-read-list/breakfast.jpg" alt="Marriage A-la-Mode: The Tête à Tête, William Hogarth, 1743, Oil on Canvas, 69.9 x 90.8 cm, National Gallery, London">
```

```markdown
**<center>荷加斯代表作「时髦婚姻：早餐」 Marriage A-la-Mode: The Tête à Tête, William Hogarth, 1743, Oil on Canvas, 69.9 x 90.8 cm, National Gallery, London</center>**
```

## Latex 支持

在行内的Ｌａｔｅｘ：`$$\int x = \lamba $$`->$$\int x = \lamba $$

在行间的Ｌａｔｅｘ：

`$$\int x = \lamba $$`

->

$$\int x = \lamba $$

## 本地更新gem包

```bash
gem update package_name
```
注意在本地更新gem所使用的包并不意味着在Github远程编译的时候包是被更新的。

正确的做法应该是在gemfile里面加入对应的行，对特定的包要求特定的最低版本。
