# Fireworks + IELTS Coach

一个烟花互动页面，包含打赏弹窗与雅思口语陪练（语音识别/合成、简易反馈）。

## 本地运行

1. 安装 Node.js。
2. 在项目根目录运行：
   ```
   node server.js
   ```
3. 打开浏览器访问 `http://localhost:8082/`（已自动跳转到 `fireworks.html`）。

## 永久对外分享（静态托管）

此项目是纯静态网页，推荐用静态托管服务，默认 HTTPS，语音功能可用。

### GitHub Pages（推荐）

1. 在 GitHub 上创建一个仓库（例如 `fireworks-coach`）。
2. 把本项目所有文件上传到仓库根目录（至少包含 `index.html`, `fireworks.html`, 以及你的收款码图片 `donate.jpg` 或 `donate.png`）。
3. 进入仓库设置（Settings → Pages）：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`，目录选 `/root`
4. 几分钟后将生成访问地址：
   - `https://<你的用户名>.github.io/<仓库名>/`（根路径会自动跳到页面）

> 如有自定义域名：DNS 添加 CNAME 指向 `<你的用户名>.github.io`，并在仓库 Pages 里设置自定义域名。

### Netlify / Vercel / Cloudflare Pages

- Netlify：登录后“Deploy site”→“Drag & Drop”上传整个文件夹，得到 `https://xxx.netlify.app/`。
- Vercel：用 GitHub 仓库一键部署，得到 `https://xxx.vercel.app/`。
- Cloudflare Pages：连接 GitHub 仓库自动构建，得到 `https://xxx.pages.dev/`。

## 打赏图片

- 将你的二维码图片命名为 `donate.png` 或 `donate.jpg`，放在与 `fireworks.html` 同级目录。
- 页面会优先加载 PNG，若失败自动回退到 JPG。

## 语音功能说明

- 语音识别与合成依赖浏览器的 Web Speech API，在 HTTPS（或 `localhost`）下可用。
- 如浏览器不支持识别，可用弹窗底部的文本输入框回答。

## 共享临时公网链接（可选）

若不想部署，临时分享可用 ngrok：

```powershell
ngrok config add-authtoken <你的_authtoken>
ngrok http 8082
```

使用输出的 `https://xxxxx.ngrok.io/` 链接分享（关闭进程后链接失效）。