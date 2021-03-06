---
title: Hexo--Build Blog
date: 2018-04-02 22:35:58
tags: Hexo
categories: 备忘
---

因为想拥有一个独属于自己的个人博客啊
<escape><!-- more --></escape>

### 1 安装部署hexo

1.  进入一个安全的目录，`cd ~/Desktop `
2.  在 GitHub 上新建一个空 repo，repo 名称是「你的GitHub用户名.github.io」
3.  安装 Hexo    `$ npm install -g hexo-cli`
4.   `$ hexo init myBlog` 新建一个网站
5.   `$ cd myBlog`
6.   `$ npm I`
7.   `$ hexo new `这时会看到一个 md 文件的路径
8.   `$ vi _config.yml`编辑网站配置
	* 把第 6 行的 title 改成你想要的名字
	* 把第 9 行的 author 改成你的名字
	* 把最后一行的 type 改成 type: git
	* 在最后一行后新增一行 `repo: 仓库地址` （仓库地址应为「你的GitHub用户.github.io」对应的仓库地址，仓库地址以  [git@github.com](mailto:git@github.com) 开头）
	* ⚠️repo后面有个空格。
9.   `$ npm install hexo-deployer-git —save`安装 git 部署插件
10.   `$ hexo deploy`
11.  进入「你的GitHub用户名.github.io」对应的 repo，打开` GitHub Pages `功能，如果已经打开了，直接点击即可预览链接博客

### 2 添加新的博客

1.  `$ hexo new` 添加博客md，这时会出现一个路径，复制显示的路径，打开编辑
2.  `$ hexo generate`生成静态文件
3.  `$ hexo deploy` 部署网站
4.  `hexo clean` 清除缓存文件 (db.json) 和 public 文件夹下已生成的静态文件

### 3 更换博客的主题

1.  进入喜欢的主题的 GitHub 首页
2.  复制它的 SSH 地址或 HTTPS 地址
3.  根据md文件提示下载
4.  将myBlo文件夹中中` _config.yml `的第 75 行改为 theme:  新下载的主题的文件夹名字
5.  `$ hexo generate`
6.  `$ hexo deploy`

### 4 上传博客源代码
注意⚠️：「你的Github用户名.github.io」上保存的只是你的博客，并没有保存「生成博客的程序代码」，所以需要再创建一个名为 `blog-generator `的空仓库，用来保存 `myBlog` 里面的「生成博客的程序代码」
。
1.  在 GitHub 创建 `blog-generator` 空仓库
![avatar](https://i.loli.net/2018/06/02/5b12ae9c43cee.png)

2.  按照截图中的命令执行即可，记住不要用 HTTPS 地址。
3. 这样你的博客发布在了「你的Github用户名.github.io」而「生成博客的程序代码」发布在了 `blog-generator`。所有数据万无一失。
	* 以后每次 `hexo deploy` 完之后，博客就会更新；然后还要 `add / commit /push` 一下「生成博客的程序代码」，以防万一。
	* 这个 `blog-generator `就是用来生成博客的程序，而「你的Github用户名.github.io」仓库就是你的博客页面。