# Zhenxuan's Blog

一个基于 [Hugo](https://gohugo.io/) + [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 的中英双语个人博客，使用 GitHub Actions 自动部署到 GitHub Pages。

- 中文站点：<https://zhenxuanpan.github.io/>
- 英文站点：<https://zhenxuanpan.github.io/en/>

## 本地预览

需要 Hugo Extended（>= 0.158）。本仓库自带主题子模块，**首次克隆**时记得带上 `--recurse-submodules`：

```bash
git clone --recurse-submodules git@github.com:zhenxuanpan/zhenxuanpan.github.io.git
cd zhenxuanpan.github.io
hugo server -D
```

然后访问 <http://localhost:1313/>。

> 如果你的机器上还没有 Hugo，可参考[官方安装文档](https://gohugo.io/installation/)。本仓库使用 Hugo 0.168.0。

## 写一篇新文章

每篇文章由中英两个文件组成，**文件名相同、语言后缀不同**，Hugo 会自动把它们配对成同一篇文章的翻译版本：

```bash
hugo new content posts/my-new-post.zh.md
hugo new content posts/my-new-post.en.md
```

打开文件，修改开头 front matter 中的标题、摘要、标签等信息：

```toml
+++
date = '2026-10-24T21:00:00+08:00'
draft = false
title = '我的新文章'
summary = '一句话概括这篇文章。'
tags = ['随笔', '技术']
categories = ['生活']
+++
```

然后正常书写 Markdown 正文即可。只写中文版也可以，翻译版本不是必需的。

常用 front matter 选项：

| 字段 | 说明 |
| --- | --- |
| `draft = true` | 草稿，仅在 `hugo server -D` 时可见，不会部署 |
| `summary` | 列表页摘要 |
| `tags` / `categories` | 标签与分类 |
| `showToc = true` | 显示文章目录 |
| `cover.image` | 封面图片路径 |
| `hideMeta = true` | 隐藏日期/阅读时间等信息 |

## 发布

提交并推送到 `main` 分支即可：

```bash
git add .
git commit -m "post: 我的新文章"
git push
```

GitHub Actions 会自动构建并发布到 GitHub Pages，通常 1–2 分钟后生效。

## 首次部署说明

仓库已经在 `.github/workflows/hugo.yml` 中配置好自动部署。如果 Pages 还没有启用，请在仓库页面操作一次：

**Settings → Pages → Build and deployment → Source 选择 “GitHub Actions”**

之后每次推送都会自动重新部署。

## 自定义站点

大部分站点信息集中在根目录的 `hugo.toml`：

- 站点标题、作者：`title`、`params.author`
- 首页欢迎语：`languages.zh.params.homeInfoParams` / `languages.en.params.homeInfoParams`
- 社交链接：`languages.*.params.socialIcons`（支持 GitHub、X、知乎、B 站等图标）
- 导航菜单：`languages.*.menu.main`
- 深色/浅色模式：`params.defaultTheme`（`auto` / `light` / `dark`）

页面内容位于 `content/`：

- `content/about.zh.md` / `about.en.md`：关于页
- `content/posts/`：文章目录
- `content/search.*.md`、`content/archives.*.md`：搜索与归档页（一般不需要改）

## 目录结构

```text
.
├── .github/workflows/hugo.yml   # 自动部署
├── archetypes/                  # 新建文章的模板
├── content/                     # 所有 Markdown 内容
│   └── posts/
├── static/                      # 图标等静态资源
├── themes/PaperMod/             # 主题（git submodule）
├── hugo.toml                    # 站点配置
└── README.md
```

## 常用命令

```bash
hugo server -D              # 本地预览（含草稿）
hugo server --disableFastRender
hugo --gc --minify          # 生成静态站点到 public/
git submodule update --init --recursive   # 拉取主题
```

## 致谢

- [Hugo](https://gohugo.io/)
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod)（MIT License）
