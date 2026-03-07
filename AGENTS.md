# AGENTS.md - 项目上下文指南

## 项目概述

这是一个基于 **Jekyll** 构建的**个人学术主页/博客网站**，托管在 GitHub Pages 上。网站采用极简风格设计，主要用于展示个人信息、学术成果、获奖记录和博客文章。

- **网站地址**: https://fenzefeng.github.io
- **技术栈**: Jekyll + GitHub Pages
- **主题基础**: Minimal Mistakes 主题（经自定义修改）
- **模板来源**: 基于 Jason Ansel 的网站模板修改，由 Hanlin Cai 进一步开发
- **当前维护者**: Fenze Feng (冯奋泽)

## 个人信息概览

- **姓名**: Fenze Feng (冯奋泽)
- **教育背景**:
  - 山东大学 微电子专业 本科（2022年9月 - 2026年6月）
  - 上海交通大学 集成电路专业 研究生（2026年9月 - 至今）
- **研究方向**: 微电子、集成电路设计、电子设计自动化（EDA）、电迁移可靠性
- **邮箱**: 202200120030@mail.sdu.edu.cn
- **GitHub**: https://github.com/fenzefeng
- **Google Scholar**: https://scholar.google.com/citations?hl=zh-CN&user=sxocVP0AAAAJ

## 目录结构

```
.
├── _config.yml          # Jekyll 配置文件（核心配置）
├── _includes/           # HTML 组件模板
│   ├── author-bio.html  # 作者信息侧边栏
│   ├── head.html        # HTML <head> 部分（含 SEO、字体、图标等）
│   ├── navigation.html  # 导航栏
│   ├── footer.html      # 页脚
│   ├── scripts.html     # JavaScript 引用
│   ├── chrome-frame.html # IE 兼容提示
│   └── disqus.html      # Disqus 评论系统
├── _layouts/            # 页面布局模板
│   ├── default.html     # 默认布局（含 Google Analytics 和访问统计）
│   ├── page.html        # 页面布局（无标题）
│   ├── home.html        # 主页布局
│   ├── post.html        # 博客文章布局
│   └── post-index.html  # 博客列表布局
├── assets/              # 静态资源
│   ├── css/             # 样式文件（main.css 为主要样式，ie.css 为 IE 兼容）
│   ├── js/              # JavaScript 文件
│   ├── fonts/           # 字体文件（IcoMoon 图标字体）
│   └── less/            # Less 样式源文件（多种响应式断点）
├── images/              # 图片资源
│   ├── logo/            # 图标/logo
│   ├── teams/           # 团队照片
│   ├── fenze.jpeg       # 个人头像
│   └── travel-1.jpg     # 主页展示图片
├── blogs/               # 博客文章（Markdown 格式）
│   ├── *.assets/        # 各博客文章的配套图片目录
│   └── to-do-list/      # 待办事项子目录
├── mypaper/             # 论文相关文件
│   ├── modeling/        # 建模竞赛论文
│   ├── poster/          # 学术海报
│   └── thesis/          # 毕业论文
├── file/                # 可下载文件（简历、作品集等）
├── backup/              # 备份文件（历史版本的 CSS、页面等）
├── zh/                  # 中文页面（完整的中文版网站）
└── .idea/               # IntelliJ IDEA 配置文件
```

## 核心配置文件

### _config.yml
主要配置项：
- `title`: 网站标题（Fenze Feng）
- `url`: 网站地址（https://fenzefeng.github.io）
- `owner`: 个人信息
  - `name`: 姓名（Fenze Feng）
  - `email`: 邮箱（202200120030@mail.sdu.edu.cn）
  - `avatar`: 头像图片（fenze.jpeg）
  - `github`: GitHub 用户名（fenzefeng）
  - `scholar`: Google Scholar 链接
  - `cv`: 简历 PDF 链接
  - `portfolio`: 作品集 PDF 链接
- `links`: 导航栏链接（About Me, Publications, Awards, Hobbies）
- `timezone`: 时区设置（China/Beijing）
- `google_verify`: Google 站长验证（SkiyuGpJOKT74vv5GmXLvYXXDkXy4v8VWPtbelYz3Hs）
- `bing_verify`: 必应站长验证（73B0109F96BA6CDB0F7C0A5F13F5542A）
- `disqus.shortname`: Disqus 评论系统标识（lancecai）

## 页面说明

| 文件 | 用途 | 访问路径 | 状态 |
|------|------|----------|------|
| `index.md` | 个人主页/关于我（英文） | `/` | 活跃 |
| `zh/index.md` | 个人主页/关于我（中文） | `/zh/` | 活跃 |
| `publications.md` | 发表论文列表（英文） | `/publications/` | 活跃 |
| `zh/publications.md` | 发表论文列表（中文） | `/zh/publications/` | 活跃 |
| `awards.md` | 获奖记录（英文） | `/awards/` | 活跃 |
| `zh/awards.md` | 获奖记录（中文） | `/zh/awards/` | 活跃 |
| `hobbies.md` | 兴趣爱好（英文） | `/hobbies/` | 活跃 |
| `zh/hobbies.md` | 兴趣爱好（中文） | `/zh/hobbies/` | 活跃 |
| `blogs.md` | 博客列表 | `/blogs/` | **已注释掉** |
| `teams.md` | 团队介绍 | `/teams/` | **已注释掉** |

## 多语言支持

网站支持中英文双语：
- **英文版**: 根目录下的 `.md` 文件
- **中文版**: `zh/` 目录下的对应文件
- 语言切换通过导航栏或手动切换 URL 实现

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

# 指定端口运行
jekyll serve --port 4000
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
4. （可选）在 `zh/` 目录创建对应的中文版本

### 修改个人信息

编辑 `_config.yml` 中的 `owner` 部分：
- `name`: 姓名
- `email`: 邮箱
- `github`: GitHub 用户名
- `scholar`: Google Scholar 链接
- `cv`: 简历 PDF 链接（放在 `file/` 目录）
- `portfolio`: 作品集 PDF 链接（放在 `file/` 目录）

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
4. 在 `blogs.md` 中添加文章链接（需先取消注释）

## 样式系统

- **主样式表**: `assets/css/main.css`
- **响应式设计**: 支持不同屏幕尺寸（通过 media queries）
- **Less 源文件**: `assets/less/` 目录包含可编译的 Less 文件
  - `1382.less`, `2x.less`, `480.less`, `600.less`, `768.less`, `992.less`: 响应式断点
  - `variables.less`: 样式变量
  - `mixins.less`: Less 混合宏
- **字体**: PT Sans Narrow, PT Serif（Google Fonts）
- **学术图标**: Academicons（通过 CDN 加载）
- **自定义图标**: IcoMoon 图标字体（`assets/fonts/`）

## 分析统计

网站集成了以下统计和分析工具：

1. **Google Analytics 4**
   - 跟踪 ID: `G-T5N5JY1E21`
   - 位置: `_layouts/default.html`

2. **Counter.dev**
   - 用于简单的访问统计
   - 数据 ID: `4c8f7caa-2b55-46cd-a995-2c4633303773`
   - 时区偏移: +8 (UTC)

## 重要注意事项

1. **不要直接修改** `_layouts/default.html` 和 `_layouts/page.html` 中的复杂结构，除非熟悉 Jekyll/Liquid 模板语法
2. **图片路径**: 使用绝对路径 `{{ site.url }}/images/xxx` 或相对路径 `/images/xxx`
3. **注释掉的页面**: 
   - `blogs.md` 和 `teams.md` 当前被注释掉
   - 可通过取消注释恢复功能
   - 同时需要在 `_config.yml` 的 `links` 部分取消对应导航链接的注释
4. **Google Analytics**: 已配置跟踪代码（G-T5N5JY1E21）
5. **Disqus 评论**: 已配置（shortname: lancecai），主要用于博客页面

## 文件修改建议

### 安全修改（推荐）
- 修改 Markdown 内容文件（`index.md`, `awards.md`, `publications.md` 等）
- 更新 `_config.yml` 中的个人信息
- 添加/替换 `images/` 中的图片
- 添加新的博客文章
- 更新中英文版本的内容

### 谨慎修改
- CSS 样式（`assets/css/main.css`）
- HTML 模板（`_includes/` 和 `_layouts/`）
- JavaScript 文件（`assets/js/`）
- Less 源文件（`assets/less/`）

### 避免修改
- `backup/` 目录下的历史备份文件
- `.idea/` 目录下的 IDE 配置文件

## 内容管理

### 博客文章列表

当前 `blogs/` 目录包含以下文章：
- `18yrs.md` - 18岁生日纪念
- `19yrs.md` - 19岁生日纪念
- `20yrs.md` - 20岁生日纪念
- `21yrs.md` - 21岁生日纪念
- `22yrs.md` - 22岁生日纪念
- `24fall.md` - 24Fall申请记录
- `aaai-24.md` - AAAI 2024参会记录
- `cambridge.md` - 剑桥暑研经历
- `IoE.md` - 物联网相关
- `modeling.md` - 数学建模竞赛
- `star.md` - 星野学社实习
- `stop.md` - 暂停/反思文章
- `summer-res.md` - 暑期研究申请指南
- `team2023.md` - 团队介绍2023
- `to-do-list.md` - 待办事项
- `web.md` - 网站搭建指南

### 可下载文件

`file/` 目录包含：
- `Fenze Feng-Resume_CN2.pdf` - 中文简历
- `Fenze Feng-Portfolio.pdf` - 作品集
- `404.md` - 404错误页面

### 论文文件

`mypaper/` 目录包含：
- `modeling/` - 数学建模竞赛论文（2022-2023年）
- `poster/` - 学术海报
- `thesis/` - 毕业论文相关

## 部署

网站通过 GitHub Pages 自动部署：
1. 提交更改到 GitHub 仓库
2. GitHub Pages 会自动构建并发布
3. 通常在几分钟内生效

### 部署前检查清单
- [ ] 确认 `_config.yml` 中的 `url` 配置正确
- [ ] 检查所有图片路径是否正确
- [ ] 验证中英文页面内容一致性
- [ ] 测试本地预览无错误

## 故障排除

### 常见问题

1. **本地预览失败**
   - 检查 Ruby 和 Jekyll 是否正确安装
   - 运行 `bundle install` 安装依赖
   - 检查 `_config.yml` 语法是否正确

2. **图片无法显示**
   - 确认图片路径使用绝对路径 `{{ site.url }}/images/xxx`
   - 检查图片文件是否已提交到仓库

3. **样式未生效**
   - 清除浏览器缓存
   - 检查 `assets/css/main.css` 是否存在

4. **Google Analytics 未工作**
   - 确认跟踪 ID 正确
   - 检查是否在 `_layouts/default.html` 中正确配置

## 参考资源

- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [GitHub Pages 文档](https://docs.github.com/en/pages)
- [Liquid 模板语法](https://shopify.github.io/liquid/)
- [Minimal Mistakes 主题](https://mademistakes.com/work/minimal-mistakes-jekyll-theme/)
- [Academicons 学术图标](https://jpswalsh.github.io/academicons/)

## 更新日志

- **2026-03-07**: 更新 AGENTS.md，添加个人信息概览部分，更新教育背景和研究方向
- **2026-03-06**: 更新 AGENTS.md，添加多语言支持说明、博客文章列表、分析统计信息
- **2023-12-10**: 上次更新 `_config.yml`
- **2023-04-26**: 修改 `_layouts/default.html` 和 `_includes/head.html`

---

*最后更新: 2026年3月7日*
