# 迷你街机（Mini Arcade Hub）

一个聚合多款 HTML/CSS/JS 小游戏的轻量平台，只要把新的 HTML 文件加入仓库并在 `index.html` 的 `games` 数组中登记，即可自动显示并在线游玩。项目基于静态页面，可直接托管在 GitHub Pages。

## 收录游戏

- **Jumping Ball Runner**：节奏跑酷，追逐高分。
- **Lo-Fi Visualiser**：React 可视化 + 内置氛围音。
- **Mini Kart Dash**：三车道竞速挑战。
- **Retro Pixel Painter**：像素画编辑器，支持撤销/导出。
- **Typing Speed Race**：限时打字练习，带历史曲线。
- **Virtual Drum Kit**：十二键鼓垫，可录制回放。

## 目录结构

```text
.
├── index.html               # 游戏门户
├── jumping-ball-runner.html # 各独立游戏
├── lofi-visualiser.html
├── mario-kart.html
├── retro-pixel-painter.html
├── typing-speed-race.html
└── virtual-drum-kit.html
```

## 本地预览

1. 安装任意静态服务器（示例使用 Python 3 内置 http.server）。
2. 在项目根目录运行：

   ```bash
   python3 -m http.server 8080
   ```

3. 打开浏览器访问 `http://localhost:8080/`。

## 添加新游戏

1. 将新的 `*.html` 文件放到根目录。
2. 编辑 `index.html`，在 `const games = [...]` 中追加：

   ```js
   {
     id: "unique-id",
     title: "Game Title",
     description: "一句简介",
     tags: ["标签1", "标签2"],
     file: "your-game.html",
   }
   ```

3. 保存后重新加载页面即可看到新卡片；玩家可内置运行或在新标签页打开。

## 部署到 GitHub Pages

1. 初始化并推送到 GitHub：

   ```bash
   git init
   git add .
   git commit -m "init arcade"
   git branch -M main
   git remote add origin git@github.com:<user>/<repo>.git
   git push -u origin main
   ```

2. 在 GitHub 仓库 Settings → Pages：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`
   - Folder 选择 `/ (root)`
   - 点击 Save

3. 待状态变为 **Your site is live** 后，访问 `https://<user>.github.io/<repo>/` 即可在线游玩。

## 浏览器支持

现代 Chromium、Firefox、Safari 浏览器均可运行；推荐桌面端 Chrome 103+ 或 Safari 16+ 以获得最佳体验和音频支持。
