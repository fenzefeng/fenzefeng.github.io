# AGENTS.md - 项目上下文指南

## 项目概述

这是一个基于 **Jekyll** 构建的**个人学术主页/博客网站**，托管在 GitHub Pages 上。网站采用极简风格设计，主要用于展示个人信息、学术成果、获奖记录和博客文章。

- **网站地址**: https://fenzefeng.github.io
- **技术栈**: Jekyll + GitHub Pages
- **主题基础**: Minimal Mistakes 主题（经自定义修改）
- **模板来源**: 基于 Jason Ansel 的网站模板修改

## 目录结构

```
.
├── _config.yml          # Jekyll 配置文件（核心配置）
├── _includes/           # HTML 组件模板
│   ├── author-bio.html  # 作者信息侧边栏
│   ├── head.html        # HTML <head> 部分
│   ├── navigation.html  # 导航栏
│   ├── footer.html      # 页脚
│   └── scripts.html     # JavaScript 引用
├── _layouts/            # 页面布局模板
│   ├── default.html     # 默认布局
│   ├── page.html        # 页面布局（无标题）
│   ├── home.html        # 主页布局
│   └── post.html        # 博客文章布局
├── assets/              # 静态资源
│   ├── css/             # 样式文件（main.css 为主要样式）
│   ├── js/              # JavaScript 文件
│   ├── fonts/           # 字体文件
│   └── less/            # Less 样式源文件
├── images/              # 图片资源
│   ├── logo/            # 图标/logo
│   └── teams/           # 团队照片
├── blogs/               # 博客文章（Markdown 格式）
├── mypaper/             # 论文相关文件
│   ├── modeling/        # 建模竞赛论文
│   ├── poster/          # 海报
│   └── thesis/          # 毕业论文
├── file/                # 可下载文件（简历、作品集等）
├── backup/              # 备份文件
└── zh/                  # 中文页面
```

## 核心配置文件

### _config.yml
主要配置项：
- `title`: 网站标题（Fenze Feng）
- `url`: 网站地址（https://fenzefeng.github.io）
- `owner`: 个人信息（姓名、邮箱、GitHub、Google Scholar 等）
- `links`: 导航栏链接（About Me, Publications, Awards, Hobbies）
- `timezone`: 时区设置（China/Beijing）
- `google_verify`: Google 站长验证

## 页面说明

| 文件 | 用途 | 访问路径 |
|------|------|----------|
| `index.md` | 个人主页/关于我 | `/` |
| `publications.md` | 发表论文列表 | `/publications/` |
| `awards.md` | 获奖记录 | `/awards/` |
| `hobbies.md` | 兴趣爱好 | `/hobbies/` |
| `blogs.md` | 博客列表（当前注释掉） | `/blogs/` |
| `teams.md` | 团队介绍 | `/teams/` |

## 开发指南

### 本地运行

```bash
# 安装 Jekyll（需要 Ruby 环境）
gem install jekyll bundler

# 安装依赖
bundle install

# 本地预览
bundle exec jekyll serve

# 或简写
jekyll serve
```

### 添加新页面

1. 在根目录创建 `.md` 文件
2. 添加 front matter：
   ```yaml
   ---
   layout: page
   permalink: /your-page/index.html
   title: Your Title
   ---
   ```
3. 在 `_config.yml` 的 `links` 部分添加导航链接

### 修改个人信息

编辑 `_config.yml` 中的 `owner` 部分：
- `name`: 姓名
- `email`: 邮箱
- `github`: GitHub 用户名
- `scholar`: Google Scholar 链接
- `cv`: 简历 PDF 链接
- `portfolio`: 作品集 PDF 链接

### 添加博客文章

1. 在 `blogs/` 目录创建 `.md` 文件
2. 添加 front matter：
   ```yaml
   ---
   layout: post
   title: "文章标题"
   date: 2024-01-01
   ---
   ```
3. 相关图片放在 `blogs/文章名.assets/` 目录

## 样式系统

- **主样式表**: `assets/css/main.css`
- **响应式设计**: 支持不同屏幕尺寸（通过 media queries）
- **字体**: PT Sans Narrow, PT Serif（Google Fonts）
- **图标**: IcoMoon 自定义图标字体 + Academicons 学术图标

## 重要注意事项

1. **不要直接修改** `_layouts/default.html` 和 `_layouts/page.html` 中的复杂结构，除非熟悉 Jekyll/Liquid 模板语法
2. **图片路径**: 使用绝对路径 `{{ site.url }}/images/xxx` 或相对路径 `/images/xxx`
3. **注释掉的代码**: 博客功能当前被注释掉，可通过取消 `blogs.md` 和 `_config.yml` 中的注释恢复
4. **Google Analytics**: 已配置跟踪代码（G-T5N5JY1E21）
5. **访问统计**: 使用 counter.dev 进行简单访问统计

## 文件修改建议

### 安全修改（推荐）
- 修改 Markdown 内容文件（`index.md`, `awards.md`, `publications.md` 等）
- 更新 `_config.yml` 中的个人信息
- 添加/替换 `images/` 中的图片
- 添加新的博客文章

### 谨慎修改
- CSS 样式（`assets/css/main.css`）
- HTML 模板（`_includes/` 和 `_layouts/`）
- JavaScript 文件（`assets/js/`）

## 部署

网站通过 GitHub Pages 自动部署：
1. 提交更改到 GitHub 仓库
2. GitHub Pages 会自动构建并发布
3. 通常在几分钟内生效

## 参考资源

- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Liquid 模板语法](https://shopify.github.io/liquid/)
- [Minimal Mistakes 主题](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/)

---

*最后更新: 2026年3月6日*
