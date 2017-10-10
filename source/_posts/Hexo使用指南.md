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

> ## 初始化Hexo

* 在存放Blog文件夹执行
  * `hexo init myBlog`
  * `cd myBlog`
  * `npm i`
* 执行`hexo new first-post`
* 你会看到`source/_posts`文件夹里多了一个`first-post.md`的文件，那就是你的第一篇Markdown博文，稍微修改一下吧
* 在命令行执行`hexo server`，打开浏览器访问 http://localhost:4000/ ，即可看到你的Blog

>## 部署Blog

* 在 GitHub 上新建一个空 repo，repo 名称是「**你的用户名.github.io**」（请将你的用户名替换成真正的用户名）
* 按下面几步配置Hexo的deploy
  * 执行`vim _config.yml`
  * 把第 6 行的`title`改成你想要的名字
  * 把第 9 行的`author`改成你的大名
  * 把最后一行的`type`改成`type: git`
  * 在最后一行，与`type`平齐，加上一行`repo: 上面repo的仓库地址`
  * `type:`和`repo:`后面有个空格，不要眼瞎
* `npm install hexo-deployer-git --save`，安装 git 部署插件
* `hexo deploy`
* 进入「**你的用户名.github.io**」对应的 repo，打开 GitHub Pages 功能，如果已经打开了，就直接点击预览链接
* 你现在应该看到了你的博客！


