# Hexo 博客 SOP

## 1. 进入博客目录

```bash
cd ~/work/github.io/jorinzou.github.io/blog
```

作用：进入 Hexo 源码目录。

---

## 2. 写博客

```bash
npx hexo new "文章标题"
```

作用：新建文章，文件会生成到 `source/_posts/`。

编辑文章：

```bash
nano source/_posts/文章标题.md
```

示例：

```yaml
---
title: RAII 与智能指针
date: 2026-03-31 10:00:00
categories:
  - cpp
  - memory
tags:
  - raii
  - smart-pointer
---

正文内容
```

作用：写标题、分类、标签和正文。

---

## 3. 预览博客

```bash
npx hexo s
```

作用：本地预览，浏览器打开 `http://localhost:4000/`。

---

## 4. 生成博客

```bash
npx hexo clean
npx hexo g
```

作用：清理旧缓存，生成最新静态页面到 `public/`。

---

## 5. 发布博客

```bash
rsync -av --delete --exclude '.git/' --exclude 'blog/' public/ ../
cd ..
git add .
git commit -m "update blog"
git push
```

作用：
- 把 `public/` 同步到仓库根目录
- 提交到 GitHub
- GitHub Pages 自动发布

---

## 6. 分类页和标签页

创建分类页：

```bash
npx hexo new page categories
```

`source/categories/index.md` 内容：

```yaml
---
title: 分类
type: categories
---
```

创建标签页：

```bash
npx hexo new page tags
```

`source/tags/index.md` 内容：

```yaml
---
title: 标签
type: tags
---
```

作用：生成 `/categories/` 和 `/tags/` 页面。

---

## 7. 常用命令速查

```bash
npx hexo new "文章标题"   # 新建文章
npx hexo s              # 本地预览
npx hexo clean          # 清缓存
npx hexo g              # 生成静态文件
```
