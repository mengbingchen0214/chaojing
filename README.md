# 临摹书架

手机端汉字书法临摹练字 PWA，离线可用，无需安装，无需后端。

## 功能

- **描红练字** — 半透明字帖底图 + 九宫格辅助线，手指或触控笔书写
- **三种笔型** — 钢笔、毛笔（速度感压感模拟）、铅笔
- **三种粗细** — 细 / 中 / 粗
- **撤销** — 最多 20 步
- **上下文条** — 显示当前字在全文中的位置，左右滑动切字
- **全文阅读** — 点任意字直接跳转练习
- **进度记忆** — 自动保存，关闭页面不丢失（localStorage）
- **自定义文本** — 粘贴任意文字即可生成练习书
- **完成页** — 全文练完后显示圆满页面
- **深色模式** — 一键切换，适合夜间练习
- **PWA** — 可添加到主屏幕，离线使用

## 内置字帖

- 《心经》全文 260 字

## 技术栈

纯原生，零依赖：

- HTML / CSS / JavaScript（单文件）
- Canvas API（双层画布：描红层 + 书写层）
- PointerEvents + TouchEvents（触控笔压感支持）
- localStorage（进度 & 自定义书本地持久化）
- Service Worker（离线缓存）
- Web App Manifest（PWA 安装）

## 本地运行

直接用任意 HTTP 服务器打开 `index.html`（Service Worker 需要 HTTP 环境）：

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

然后访问 `http://localhost:8080`。

## 部署

项目为纯静态文件，可直接部署到任意静态托管平台：

- [Cloudflare Pages](https://pages.cloudflare.com/) — 推荐，免费无限带宽
- GitHub Pages
- Netlify

## 文件结构

```
index.html      # 完整应用（HTML + CSS + JS 单文件）
manifest.json   # PWA 配置
sw.js           # Service Worker（离线缓存）
icon.svg        # 应用图标
```

## 数据说明

所有用户数据（练习进度、自定义书）仅存储在**用户自己的浏览器**中，不上传任何服务器。换设备或清除浏览器数据后会重置。
