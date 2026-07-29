# XOLOme Website

XOLOme 响应式品牌官网（静态站点），支持桌面端与移动端。

## 线上地址

| 环境              | 地址                                   |
| ----------------- | -------------------------------------- |
| 正式站            | https://xueying.xolome.com/            |
| Cloudflare 预览站 | https://xolome-website-test.pages.dev/ |

正式站部署、SSH、权限等本机私有说明见根目录 `XOLOme 官网运维手册.md`（含凭据，已加入 `.gitignore`，不要提交）。

## Cloudflare Pages

- Project name: `xolome-website-test`
- Build command: `npm run build`
- Build output directory: `dist`
- Production branch: `main`

### GitHub Actions

仓库含 `.github/workflows/deploy-pages.yml`。推送 `main` 可部署到 Cloudflare Pages。

在仓库 Secrets 配置：

1. 创建 [Cloudflare API Token](https://dash.cloudflare.com/profile/api-tokens)（至少 **Account → Cloudflare Pages → Edit**）
2. GitHub → Settings → Secrets and variables → Actions
   - Name: `CLOUDFLARE_API_TOKEN`

推送 GitHub **不会**自动更新阿里云正式站。

## 本地命令

```powershell
npm run build
npm run preview
npm run deploy
```

## 目录结构

```text
.
|-- assets/
|   |-- images/
|   `-- video/
|-- css/
|   |-- site.min.css
|   `-- xolome-local-overrides.css
|-- js/
|   `-- app.js
|-- scripts/
|   `-- build-pages.mjs
|-- index.html
|-- robots.txt
|-- sitemap.xml
|-- _headers
|-- _redirects
|-- package.json
`-- wrangler.jsonc
```

本地样式覆盖写在 `css/xolome-local-overrides.css`，并在 `index.html` 中最后加载。

## 媒体规范

- 视频：H.264、`yuv420p`、`faststart`
- 展示图优先 WebP；二维码与 Logo 可保留原格式
- 单文件控制在 Cloudflare Pages 上传限制内

## 联系方式

- Email: INFO@xolome.com
- 正式站: https://xueying.xolome.com/
