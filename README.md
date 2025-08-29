## 本博客允许任何人提交PR
```
不能提交的内容：违反中华人民共和国法律的内容
```
````markdown
# 快速指南

## 📝 撰写文章

1. **创建新文章**
```bash
pnpm new-post <文件名>
````

2. **编辑文章**

* 修改 `src/content/posts/` 中的 Markdown 文件

3. **Frontmatter 示例**

```yaml
---
title: 我的文章标题
published: 2023-09-09
description: 文章描述，用于 SEO
image: ./cover.jpg
tags: [标签1, 标签2]
category: 分类
draft: false    # true 表示草稿
pinned: false   # true 表示置顶
lang: zh-CN     # 可选
---
```

---

## 🚀 部署方式

1. **克隆仓库**

```bash
git clone https://github.com/mhya123/Dreamily-Blog.git
```

2. **安装依赖**

```bash
npm install -g pnpm      # 如果未安装 pnpm
pnpm install
```

3. **配置站点信息**

* 编辑 `src/config.ts`，修改博客名称、主题色、横幅、社交链接等

4. **构建生产站点**

```bash
pnpm build
```

5. **本地预览（可选）**

```bash
pnpm preview
```

> 修改完成后，将更改提交到分支，并通过 Pull Request 提交到主仓库即可。
