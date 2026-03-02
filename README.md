# darkestni.github.io

个人博客网站 - 基于 Jekyll Chirpy 主题

## 项目简介

这是一个使用 Jekyll 和 Chirpy 主题构建的静态博客网站，托管在 GitHub Pages 上。

## 目录结构

```
.
├── _config.yml          # 站点配置文件
├── _tabs/               # 标签页
├── _posts/              # 博客文章
├── _data/               # 数据文件
├── _plugins/            # Jekyll 插件
├── assets/              # 静态资源 (CSS, JS, 图片)
├── tools/               # 工具脚本
└── index.html           # 首页
```

## 技术栈

- Jekyll
- Chirpy 主题
- GitHub Pages
- Liquid 模板引擎

## 本地开发

### 环境要求

- Ruby 2.7+
- Bundler

### 安装和运行

```bash
# 安装依赖
bundle install

# 本地预览
bundle exec jekyll serve

# 访问 http://localhost:4000
```

## 部署

本博客使用 GitHub Pages 自动部署，推送到 `main` 分支后会自动构建和发布。

## 自定义

- 修改 `_config.yml` 配置站点信息
- 在 `_posts/` 目录下添加 Markdown 格式的文章
- 在 `_tabs/` 目录下自定义标签页

## 许可证

MIT License

## 链接

- [主题文档](https://github.com/cotes2020/jekyll-theme-chirpy)
- [在线访问](https://darkestni.github.io)
