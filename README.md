# azblog · 阿泽Aza 的技术博客

一个**零依赖、零构建**的纯静态博客：`index.html` 单页 + `posts/` 下的文章页，丢进任意 Web 服务器就能跑。

## ✨ 特点

- **纯静态** — 没有框架、没有构建步骤，改完 HTML 直接刷新
- **GitHub 热力图** — 首页每次打开实时拉取 GitHub 贡献数据渲染，无需后端与构建
- **轻量** — 整站体积只有几十 KB
- **自适应** — 手机 / 平板 / 桌面都可读
- **深色阅读体验** — 长文排版针对屏幕阅读优化

## 📁 目录结构

```
azblog/
├── index.html                     # 首页（文章列表）
├── favicon.svg                    # 站点图标
└── posts/
    ├── azcode.html                # AzCode:让模型直接操作你自己的设备
    ├── azappapi.html              # AzappApi:一个服务端骨架,顺手长出了 AI 网关
    ├── azapplogin.html            # AzLogin:让两个站点共用一套账号
    ├── dbc.html                   # dbc:用 Kotlin 原生写一个 DeepSeek 安卓客户端
    ├── first-year-lessons.html    # 入行一年，我学到的几件事
    ├── ollama-qwen-local.html     # 用 Ollama 在本地跑 Qwen
    └── service-pressure.html      # 服务压力监控系统的由来
```

## 🚀 部署

### 方式一：自建服务器

把整个目录上传到 Web 根目录（如 `/var/www/html`），确保 Nginx / Apache 已开启静态文件服务即可。

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/azblog;
    index index.html;
    location / { try_files $uri $uri/ =404; }
}
```

### 方式二：GitHub Pages

在仓库 `Settings → Pages` 中选择分支与根目录，保存后即可通过 `https://<用户名>.github.io/azblog/` 访问。

### 方式三：本地预览

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

## ✍️ 写一篇新文章

1. 复制 `posts/` 下任意一篇 HTML 作为模板
2. 改标题与正文，保存为新的 `.html`
3. 在 `index.html` 的文章列表里加一条链接

## 📌 说明

本仓库已移除封面图等媒体文件，页面中的图片链接可能失效；如需完整效果请自行补充 `posts/` 与根目录下的图片资源。

## 📄 License

MIT
