---
title: "Hello, World"
date: 2026-10-24
draft: false
summary: "The first post: why I started writing, and how this site is built."
tags: ["essay", "blog"]
categories: ["Life"]
showToc: true
---

Hi, welcome to my blog 👋

This is the first post. The idea behind it is simple: **turn notes, conversations, and half-formed thoughts into writing that can be searched and shared.**

## How this site is built

The site consists of three parts:

- [Hugo](https://gohugo.io/) — a static site generator written in Go, extremely fast to build
- [PaperMod](https://github.com/adityatelange/hugo-PaperMod) — a clean theme with dark mode and built-in search
- [GitHub Pages](https://pages.github.com/) — free static hosting, deployed automatically via GitHub Actions

Writing a post only requires Markdown, then pushing to GitHub:

```bash
git add .
git commit -m "post: hello, world"
git push
```

The build and deployment are handled automatically by GitHub Actions.

## Bilingual by default

The site supports Chinese and English. Each post consists of two files in the same directory:

```text
content/posts/
├── hello-world.zh.md
└── hello-world.en.md
```

Hugo treats them as two language versions of the same post, and a language switcher appears at the top of the page.

## What's next

I plan to write about:

- Technical notes and lessons learned
- Open-source project updates
- Books and everyday thoughts

If you're interested too, feel free to find me on [GitHub](https://github.com/zhenxuanpan). See you in the next post!
