# README

## 开始写周刊

### 0. 工具准备

1. 命令行终端，推荐 Warp
2. 编辑器，推荐 VSCode
3. Git
4. 其他命令行工具： HomeBrew, Go, Hugo

### 1. Clone 本仓库到本地

```shell
git clone https://github.com/hutusi/ai-weekly.git
```

### 2. 创建一篇周刊

进入本地目录：

```shell
cd ai-weekly
```

执行命令创建一篇新周刊：

```shell
hugo new content posts/2025-05-21-first-post.md 
```

该命令表示将在 content 目录下的 posts 子文件夹中建立一个名为 `2025-05-21-first-post.md` 的文本文件，`2025-05-21`是日期，可以修改为当前日期，`first-post`是周刊的名称，将用来做周刊的url.

### 3. 编辑周刊

使用 vscode 打开周刊工程：

```shell
code .
```

打开 `content/posts` 下的周刊文件，编辑周刊写作。可以修改头部的meta 内容，或保留：

```
---
date: '2025-05-21T09:22:19+08:00'
author: ["Hu Zhiyong"]
title: First Post
slug: first-post
summary: "Sample article."
tags: ["blog", "podcast"]
categories: ["blog"]
---
```


在 --- 下方另起一行写周刊内容即可，周刊文本采用 Markdown 格式。

### 4. 在本地调试周刊

在本地命令行终端上执行：

```shell
hugo server -D
```

如果有报错，需要根据报错信息fix bug. 如果没有报错，最后会出现如下字样：

```shell
Built in 35 ms
Environment: "development"
Serving pages from disk
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1) 
Press Ctrl+C to stop
```

这个时候根据提示打开浏览器，输入 `http://localhost:1313/` 或 `http://127.0.0.1:1313/` 即可查看周刊的效果，可以根据浏览器的效果来修改周刊，直到满意。

终止调式按 `Ctrl` + 'c' 键即可。

### 5. 提交周刊

编辑好后，在本地执行 Git 查看文件修改状态：

```shell
git status
```

可以看到有一个新增文件。将文件添加到Git 缓冲区：

```shell
git add .
```

然后提交到本地的Git 库历史，`add new post` 是这次提交的记录消息，用于追溯，可修改，表示这次新增或改了哪些东西。

```shell
git commit -m"add new post"
```

然后提交到 GitHub 上：

```shell
git push origin master
```

其中 origin 表示GitHub 上的仓库，master 表示当前工作的分支。

提交完之后，等待 GitHub Actions 的结果。在 `https://github.com/hutusi/ai-weekly/actions` 查看最新一次的 action 执行情况，如果有报错，点击进去查看原因并 fix bug. 如果执行成功，打开网址即可查看最新的周刊。