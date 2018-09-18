---
title: Hello World
date: 2018-08-31 10:50:38
copyright: true
categories: "个人整理"
tags:
- hexo
---
终于搭建好了个人博客，写下了第一篇博客，按照惯例，作为程序猿，第一篇博客的名称就叫“Hello World”了。

实在不知道应该写点啥，就整理一下如何用hexo写博客好了。

先说一下基本配置：使用Hexo+GitHub Pages搭建博客，next主题以及Windows OS。
<!-- more -->
## 1 新建文章
以hello world为例，在hexo目录下命令行输入```hexo new "hello_world"```，然后会在source的_posts目录下生成一个hello_world.md文件,在该markdown文件中就可以编辑这篇文章的内容了。编辑完成后刷新博客，博客里便会出现这篇文章，同时hexo也会直接为这篇文章生成一个页面。
## 2 新建草稿
hexo默认配置是新建文章，所以如果需要新建一篇草稿，需要输入```hexo new draft "文章名称"```，然后再source的目录下会生成一个_drafts文件夹，里面会有所有新建的草稿，如果想要预览草稿，可以输入```hexo server --draft```命令来预览草稿文件

当草稿完成以后，可以通过输入```hexo publish "文章名称"```来发布草稿，然后这篇草稿会从_drafts中被删除，出现在_posts目录下。
## 3 删除文章
删除文章十分简单，只需要把_posts目录下需要删除的markdown删除，然后刷新博客之后这篇文章就不会出现在博客中了。

当然还有更多的教程可以直接去<a href="https://hexo.io/zh-cn/docs/writing.html" target="_blank">官网</a>学习。