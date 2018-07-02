---
title: 开业大吉
date: 2016-08-13 12:46:21
tags: web
---
稍微记录一下这个站的搭建过程吧。

<!--more-->

## 建立GitHub Page ###

- github新建一个repo，起名为vallis-neria.github.io

- clone到本地，随便丢一个index.html进去，提交更改，打开https://vallis-neria.github.io/，好的能用。

## 使用Hexo

#### _What is Hexo?_

>_[Hexo](https://hexo.io/) 是一个简单的、轻量的、基于Node.js的一个静态博客框架，可以方便的生成静态网页托管在github和Heroku上。_

### 安装Hexo


- 先去[官网](https://nodejs.org)下个node.js

- 然后再去下个git客户端（最好GitHub Desktop）

- 安装Hexo：

~~~sh
npm install -g hexo-cli 
~~~

### 设置Hexo


Hexo是一个命令行工具，可以在Git Shell里方便的使用。如果想要在Windows的cmd或者Powershell里用的话，需要修改环境变量PATH，加入git.exe的路径。总之在控制台敲"git"不会提示找不到命令或外部程序就行。

- cd到工作目录

- 初始化

~~~sh
Hexo init
~~~

- 进行设置

    打开_config.yml，重点是deployx项

    对于github，仿照如下设置：
    
~~~yml
deploy:
- type: git
  repo: git@github.com:username/username.github.io.git
~~~

- 新建第一个日志

~~~sh
Hexo new "Hello World"
~~~

- 编写日志正文

    在source/_posts文件夹里找到你的日志，用Markdown撰写。

- 生成页面

~~~sh
Hexo generate
~~~


- 部署到网站上
~~~sh
Hexo deploy
~~~



~~（未完待续）~~