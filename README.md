# 我的博客 · GitHub Pages 静态博客

一个零成本、无服务器、无构建工具的静态博客，纯 HTML/CSS 实现，可直接部署到 GitHub Pages。

## 目录结构

```
my-blog/
├── index.html                  # 首页（文章列表）
├── about.html                  # 关于页
├── css/
│   └── style.css               # 全站样式（设计变量集中管理）
└── posts/
    ├── github-pages-guide.html # 教程：GitHub Pages 部署指南
    ├── how-to-write.html       # 教程：如何添加新文章
    └── hello-world.html        # 示例随笔
```

## 部署到 GitHub Pages（约 5 分钟）

### 1. 创建仓库

登录 [github.com](https://github.com)，点击右上角 **+** → **New repository**：

- 仓库名：`你的用户名.github.io`（如 `zhangsan.github.io`，可直接绑定 `https://你的用户名.github.io`）
- 可见性：Public
- 勾选 **Add a README file**

### 2. 上传本目录所有文件

**方式 A（网页上传，最简单）**：仓库页 → **Add file → Upload files** → 把 `index.html`、`about.html`、`css/`、`posts/` 全部拖入 → **Commit changes**。

**方式 B（Git 命令行）**：

```bash
git clone https://github.com/你的用户名/你的用户名.github.io.git
cd 你的用户名.github.io
# 将本目录的全部内容复制进该文件夹，然后：
git add .
git commit -m "feat: 发布博客"
git push origin main
```

### 3. 开启 Pages

仓库 → **Settings → Pages** → Source 选 **Deploy from a branch**，Branch 选 `main` + `/(root)` → **Save**。

1～2 分钟后访问 `https://你的用户名.github.io` 即可。

## 如何发布新文章

1. 复制 `posts/` 中任意一篇文章，重命名（如 `my-new-post.html`）
2. 修改 `<title>`、`<h1>`、日期标签和正文
3. 在 `index.html` 文章列表顶部添加对应条目
4. 提交推送，GitHub Pages 自动重新部署

## 可选进阶

- **自定义域名**：域名 DNS 加 CNAME 记录指向 `用户名.github.io`，仓库根目录添加 `CNAME` 文件
- **Jekyll / Hugo**：需要 Markdown 工作流时，可迁移到静态站点生成器（GitHub Pages 原生支持 Jekyll）
- **评论系统**：接入 Giscus（基于 GitHub Discussions，免费）
