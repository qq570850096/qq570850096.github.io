# 致楚林 · 教师节清晏小站

一个带口令的祝福页，主题取“清晏”之意，带有轻柔的过渡动画与桂花样式的鼠标。

- 访问口令：`0214`
- 技术：纯静态 HTML（一个文件即可运行）；可直接用于 GitHub Pages。

## 本地查看

- 直接双击打开 `index.html` 即可（推荐 Chrome/Edge/Firefox）。
- 若浏览器限制本地资源，可起一个本地服务器：
  - Python: `python -m http.server 8000`
  - Node: `npx http-server -p 8000`
  然后访问 `http://localhost:8000`。

## GitHub Pages 部署（详细）

以下任选一种方式：

### 方式 A：项目页（推荐）
适合以 `https://<你的用户名>.github.io/<仓库名>/` 访问。

1. 新建仓库（例如 `chulin-teachers-day`）。
2. 推送本站代码：
   ```bash
   git init
   git add .
   git commit -m "feat: add chulin teachers' day site"
   git branch -M main
   git remote add origin https://github.com/<你的用户名>/chulin-teachers-day.git
   git push -u origin main
   ```
3. 开启 Pages：进入仓库 → Settings → Pages：
   - Source 选 `Deploy from a branch`
   - Branch 选 `main`，Folder 选 `/ (root)`
   - 保存后稍等，访问 `https://<你的用户名>.github.io/chulin-teachers-day/`

### 方式 B：个人主页仓库
适合部署到顶级域 `https://<你的用户名>.github.io`。

1. 创建仓库，名称必须为：`<你的用户名>.github.io`
2. 将本项目文件推送至该仓库 `main` 分支根目录。
3. 稍等片刻，访问你的主页地址验证。

### 可选：404 页面与 Jekyll
- 已提供 `404.html` 以适配 Pages 的错误路由。
- `.nojekyll` 用于禁用 Jekyll 处理（保持纯静态文件）。

## 自定义
- 文案：直接编辑 `index.html` 内文字。
- 口令：在 `index.html` 底部脚本里把 `'0214'` 改为你想要的数字或字符串。
- 鼠标形状：在 `index.html` 的 `body { cursor: ... }` 可替换为自己的图片（建议 24×24 或 32×32 的透明 PNG/SVG）。
- 配色与动画：同样在 `index.html` 的 `<style>` 中调整。

> 口令仅作仪式感与轻量遮挡，请勿用于真正的隐私保护。
