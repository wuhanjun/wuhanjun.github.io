# [wuhanjun.github.io](https://github.com/wuhanjun/wuhanjun.github.io)


## 前言

W 的 Blog 就这么开通了。

[跳过废话，直接看记录的坑 ](#build)



16年的博客因为收费关闭了，现在在github上开一个。


刚开始自己吭哧吭哧写了页面，后来突然发现大家都是用jekyll之类的工具生成的，大家可以去fork一个，然后修改一下做成自己的，挺实用的，节省时间。

比如这篇笔记，是用markdown写的，jekyll会帮你处理好模版引擎这些琐碎的事情。


<p id = "build"></p>
---

## 正文

---
接下来记一下搭建gitpage时遇到的问题
- 本地开发环境
1. 注意点：公司的Gitlab和Github可以共用一个rsa，rsa只是Github放在本地机器的标识，用来证明这台电脑以后都可以直接操作远程仓库。这是[整体流程](https://git-scm.com/book/zh/v1/%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A%E7%9A%84-Git-%E7%94%9F%E6%88%90-SSH-%E5%85%AC%E9%92%A5)。
- 建立gitpage仓库时的注意点
1. 如果你用的[默认的](https://pages.github.com/)方式搭建，那么gitpage仓库名为username.github.io，方式搭建，那么gitpage仓库名必须为username必须与你的Github账号完全一致。gh-pages的方式网上搜一下教程，很多。
2. 仓库中的文件名不允许和其他仓库名相同，这样会导致你这个目录下的资源404。


一些建议
1. 可以clone或者firk一份好看的gitpage，会节省很多时间。
2. 而且，git clone的话，建议找好就开始。因为文件会比较大。
3. 在你clone的时候，可以浏览[jekyllen](http://jekyllcn.com/)这个网站，先安装一下环境。操作很简单，没有几步，但是限于网速要很久。
4. 之后，你可以大致翻阅一下文档，看看是怎么用的，然后对照着fork过来的目录理解就可以了。
5. 等仓库clone到本地了，改一些个人的配置，例如首页图片、favicon、资源路径、_config.yml就能跑起来了。
6. 你如果直接fork的我这份模版，npm run watch就能在本地调好后上传了。
7. Year~


## 后记

可以去[原作者仓库](https://github.com/huxpro)那里点个赞，[给我点赞](https://github.com/wuhanjun/wuhanjun.github.io)我也很开心😄

—— 晗君 后记于 2019.03.09
