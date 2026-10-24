---
title: "你好，世界"
date: 2026-10-24
draft: false
summary: "博客的第一篇文章：为什么要开始写作，以及这个站点是如何搭建的。"
tags: ["随笔", "博客"]
categories: ["生活"]
showToc: true
---

你好，欢迎来到我的博客 👋

这是第一篇文章。搭建它的初衷很简单：**把散落在笔记、聊天记录和脑海里的东西，整理成可以被检索、被分享的文字。**

## 这个博客是怎么搭建的

这个站点由三部分组成：

- [Hugo](https://gohugo.io/)：用 Go 编写的静态网站生成器，构建速度非常快
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod)：简洁、支持深色模式和站内搜索的主题
- [GitHub Pages](https://pages.github.com/)：免费的静态站点托管，配合 GitHub Actions 自动部署

写作时只需要写 Markdown，然后推送到 GitHub：

```bash
git add .
git commit -m "post: 你好，世界"
git push
```

剩下的构建与发布工作会由 GitHub Actions 自动完成。

## 中英双语

站点支持中英文切换。每篇文章由两个文件组成，放在同一目录下：

```text
content/posts/
├── hello-world.zh.md
└── hello-world.en.md
```

Hugo 会把它们识别为同一篇文章的两个语言版本，阅读时可以在页面顶部切换语言。

## 接下来写什么

计划在这里记录：

- 技术笔记与踩坑经验
- 开源项目进展
- 读书与生活随笔

如果你也感兴趣，欢迎通过 [GitHub](https://github.com/zhenxuanpan) 找到我。我们下一篇文章见！
