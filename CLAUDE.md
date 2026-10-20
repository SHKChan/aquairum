# aquairum

像素水族箱：www.vibe-game.com/aquarium/。孵鱼卵、喂食、治病，照顾得好不好决定鱼长成什么样。

## 系列规范（先读）

本仓库是 Vibe Game 系列的一个游戏。部署、顶栏、版本号、存档键、语言、画风、文风这些跨仓库的规则，只写在 vibe-game 仓库的 `docs/GUIDE.md`，开始工作前先读完：

- 本地：`../vibe-game/docs/GUIDE.md`
- 线上：https://raw.githubusercontent.com/SHKChan/vibe-game/main/docs/GUIDE.md

两处都读不到时，先停下来问用户要这份规范，不要凭记忆或猜测去改跨仓库的东西。本文件只写本仓库的参数、玩法和例外；和 GUIDE 冲突时以 GUIDE 为准，除非下面明确写了“例外”。设计子代理（game / narrative / economy / level designer）在 vibe-game 的 `.claude/agents/`，需要时按 GUIDE 第十三节去读。

## 本仓库参数

| 项 | 值 |
|---|---|
| 网址 | https://www.vibe-game.com/aquarium/ |
| 路径 / Worker | `aquarium` |
| 生产分支 | `main`（推送即部署） |
| 打包 | `node tools/build.js` → `dist/aquarium/`；新增运行时文件要加进 `FILES` |
| 版本号 | `index.html` 的 `<meta name="vg:version">` |
| 存档键 | `aquarium.*` |

## 本游戏

- 全部代码在 `index.html` 一个文件里：`SP` 三种鱼（各有“照顾得好 / 疏于照顾”两种成年形态）、`GROW` 成长阈值、`OFFLINE_CAP` 离线最多补算 15 分钟、`MAX_FISH` 最多 6 条。
- 存档：`aquarium.save.v1`，结构改了就升到 v2。
- 注意仓库名是 `aquairum`（拼写历史原因），网址路径、Worker、存档前缀都是 `aquarium`，不要改。
- 界面文字在 `T` 里有中英两套，`LANG` 现在固定 `'zh'`（GUIDE：暂时只开中文）。
