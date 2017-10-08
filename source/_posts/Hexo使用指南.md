---
title: Hexo搭建博客不完全指南
id: 1
categories:
  - 编程
  - Hexo
date: 2017-10-08 18:00:00
tags:
---

> ## 配置环境

* 安装Node并配置npm
  * 打开 https://nodejs.org/en/download/ ，选择适合自己的版本进行下载安装。
  * 打开CMD，对Node进行如下配置：
  * `npm config set registry https://registry.npm.taobao.org/`
  * `npm config set loglevel http`
  * `npm config set progress false`
  * 安装Hexo，命令如下
  * `npm install -g hexo-cli`
* 初始化Blog
  * 在存放Blog文件夹执行
  * `hexo init myBlog`
  * `cd myBlog`
  * `npm i`
  * `hexo new first-post`
  * 你会看到`source/_posts`文件夹里多了一个`first-post.md`的文件，那就是你的第一篇Markdown博文
  * 在命令行执行`hexo server`，打开浏览器访问 http://localhost:4000/ ，即可看到你的Blog


> ## 初始化Hexo