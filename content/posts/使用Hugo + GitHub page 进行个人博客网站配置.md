---
created: 2026-10-22 22:38:55
modified: 2026-10-23 13:41:41
---
首先介绍下平台及需要的软件。
在windows系统上进行软件的安装与配置。所使用软件有Hugo和git，网页端使用GitHub。

首先安装Hugo，安装网址是 https://hugo.opendocs.io/installation/windows/ ，选择拓展版。
![[个人网站配置-6cf58aae87f762c27642d3e58f1d924d_MD5.png]]

在安装页面中有三种安装方式的对比，我们选择包管理器安装方法。
![[个人网站配置-fab11bb731583c7eba685d2bff4e0ecf_MD5.png]]

网站上展示了三种管理器，我们使用 WinGet 进行安装，因为这是win 10 系统自带的，只要有Microsoft Store 就有 WinGet。
![[个人网站配置-d68562202deab10db1cab59acc3f4809_MD5.png]]

在终端中选择 Windows PowerShell，使用 `winget --version` 查看 WinGet版本，确认有WinGet后。使用 `winget install Hugo.Hugo.Extended` 安装 Hugo 拓展版。
![[个人网站配置-e28e348c1acd24fc18d08cf946071a5e_MD5.png]]

输入 `hugo version` 查看 hugo 是否安装好，`hugo -h` 查看使用帮助。
![[个人网站配置-34551a55946bc2a1e3b622cdcfa47e8a_MD5.png]]

因为Hugo官方不建议使用 PowerShell 或 Windows PowerShell，接下来使用 git bash 进行配置 Hugo 创建网站。

没有 git bash 需要下载安装 git，下载地址：#https://git-scm.com/install/windows 。后续同步本地文章到 GitHub 时需使用 git，这是安装 git 的主要目的，git bash 只是顺便用下。

我选择在 D 盘进行 hugo 的配置，这部分内容对应 Hugo 的快速入门部分，网址是：#https://hugo.opendocs.io/getting-started/quick-start/

使用 
```
hugo new site AdrianGuo
```
在 `AdrianGuo` 目录中为项目创建目录结构，`AdrianGuo` 改为你自己想起的名称。接下来输入下列命令。
```bash
	cd AdrianGuo  // 进入项目目录
	git init      // 初始化 git 仓库
	git submodule add https://github.com/theNewDynamic/gohugo-theme-ananke.git themes/ananke     // 下载 ananke 主题
	echo "theme = 'ananke'" >> hugo.toml // 将使用主题写入配置文件
	hugo server   // 启动 hugo 服务器
```
![[个人网站配置-01d7bcc954e1e65949cc8e7d9c2c2fbd_MD5.png]]

复制 `http://localhost:1313` 网址进浏览器搜索栏，即可查看配置好的网页。按下 `Ctrl + C` 停止 Hugo 的开发服务器。
![[个人网站配置-58aa6dd36dab74944c66c3fe09571e45_MD5.png]]

这样一个单机版的网页就制作好了，接下来需要进行托管和部署到GitHub上。完成之后就是联网的网页，可供别人搜索与浏览。

![[attachments/使用Hugo + GitHub page 进行个人博客网站配置/使用Hugo + GitHub page 进行个人博客网站配置-a3e53b2a5580a098adcfb9a813f9cac2_MD5.jpeg]]

![[attachments/使用Hugo + GitHub page 进行个人博客网站配置/使用Hugo + GitHub page 进行个人博客网站配置-5b0291a0491d90b3e0bf76b18e64e688_MD5.jpeg]]

参考文章：
[^WinGet介绍]: [【保姆级喂饭教程】WinGet介绍、安装、命令及UniGetUI介绍、安装、使用教程](https://zhuanlan.zhihu.com/p/2063268645942431835)