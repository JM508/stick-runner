# stick-runner · 火柴人快跑（独立版）

横版无尽跑酷小游戏，全部画面用 Canvas 程序化绘制、音效用 WebAudio 实时合成，
不依赖任何图片 / 音频 / 字体资源（立绘与障碍贴图为可选增强）。

**本仓库是「Wow 娱乐小站」火柴人快跑的源仓库**：
push 到 `main` 后，GitHub Actions 会自动把游戏文件同步到
[wow 站点仓库](https://github.com/JM508/wow)（`static/` 目录），站点随后自动构建上线。

## 在线试玩

- 站内版（含云端排行榜 / 云存档 / 商店）：https://wow-d9s.pages.dev/runner/
- 独立版（本仓库 GitHub Pages，纯本地玩法）：https://jm508.github.io/stick-runner/

## 文件说明

| 文件 | 说明 |
| --- | --- |
| `index.html` | 独立版入口（本地钱包，离线可玩） |
| `runner.js` / `runner.css` | 游戏本体（物理 / 障碍 / 渲染 / HUD） |
| `skins.js` | 皮肤仓库 + 钱包 + 绘制（与商店共用） |
| `shop.js` / `shop.css` | 皮肤商店 |
| `img/*.webp` | 立绘与障碍贴图（加载失败自动回退矢量画法） |

## 同步机制

`.github/workflows/sync-to-wow.yml`：本仓库更新 → 自动复制
`runner.js / runner.css / skins.js / shop.js / shop.css / img/*`
到 wow 仓库的 `static/` 并提交 → Cloudflare Pages 自动构建。
注意：`cloud.js` / `rank.js`（云排行榜、云存档接入层）不属于本仓库，
请到 [wow 仓库](https://github.com/JM508/wow) 修改。
