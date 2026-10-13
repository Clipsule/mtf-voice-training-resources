# MTF 声音女性化训练资源

> 一个多语言、轻量化的资源导航站，汇集 MTF 声音女性化训练所需的手册、工具与社区链接。

## 📖 项目简介

本项目是一个**纯静态的资源导航页面**，旨在为 MTF（Male-to-Female）群体提供声音女性化训练的一站式入口。页面整理了来自社区的优质教程、声学分析工具和互助社群链接，并以中、日、英、韩四种语言呈现，降低不同语言使用者的信息获取门槛。

声音女性化训练是一个需要科学方法和持续练习的过程。这个导航站将分散在各处的核心资源集中到一处，帮助练习者更快找到正确的学习路径，避免在质量参差不齐的信息中迷失方向。

## ✨ 功能特性

- **多语言支持**：内置中文、English、日本語、한국어四种语言，点击即可切换，自动记忆用户偏好。
- **实时在线人数**：基于 WebRTC 的轻量级方案，页面侧边栏实时显示当前在线访客数。
- **响应式布局**：桌面端为左右双栏结构（侧边导航+内容区），移动端自动切换为单栏流式布局。
- **声学可视化装饰**：侧边栏内置动态声波律动指示器和星轨背景，呼应“声音训练”的主题。
- **分类清晰的资源卡片**：分为训练资料、辅助工具、友情链接、贡献者四大板块，每个资源都配有标签和操作按钮。
- **零后端依赖**：纯静态 HTML/CSS/JS，可直接部署到 Vercel、GitHub Pages 等平台。

## 🛠️ 技术栈

| 层面 | 技术选型 |
|---|---|
| 页面结构 | 原生 HTML5 |
| 样式 | 原生 CSS3（CSS 变量、Grid、Flexbox、渐变、动画） |
| 交互 | 原生 JavaScript（i18n 翻译字典、DOM 操作） |
| 在线统计 | [Oneline.js](https://github.com/ezshine/oneline.js)（基于 WebRTC 的 P2P 人数统计） |
| 部署 | Vercel（静态托管） |

## 🚀 快速开始

### 本地预览

```bash
# 克隆仓库
git clone https://github.com/Clipsule/mtf-voice-training-resources.git

# 进入目录
cd mtf-voice-training-resources

# 使用任意静态服务器启动，例如 Python 自带的 http.server
python -m http.server 8080
```

然后在浏览器中打开 `http://localhost:8080` 即可。

### 部署到 Vercel

1. 将仓库推送到 GitHub。
2. 在 Vercel 中导入该仓库。
3. Framework Preset 选择 **Other**，Build Command 和 Output Directory 留空。
4. 点击 Deploy，几分钟内即可上线。

## 📁 项目结构

```
mtf-voice-training-resources/
├── index.html          # 唯一的主页面（含全部样式、脚本、翻译字典）
├── README.md           # 本文件
└── vercel.json         # Vercel 部署配置（如有多语言路径需求）
```

项目刻意保持单文件结构，所有样式和脚本内联在 `index.html` 中，最大化部署便利性和可移植性。

## 🌐 多语言实现

页面采用**前端动态切换**方案，而非多文件路由。所有文案存放在 JavaScript 的 `translations` 对象中，按 `data-i18n` 属性索引。切换语言时只替换对应元素的 `textContent`，不刷新页面。

用户的语言选择通过 `localStorage` 持久化；首次访问时根据浏览器语言自动匹配。

## 📊 在线人数统计

页面使用 Oneline.js 实现实时在线人数显示。其原理是基于 WebRTC 在访客之间建立 P2P 连接，第一个进入的用户创建“房间”，后续访客自动加入，彼此同步在线计数。

> **注意**：该方案的免费公共信令服务支持**最多 50 个同时在线用户**。对于个人项目足够使用；如果未来并发量增长，可考虑自行部署 PeerServer 或迁移至 Supabase Presence。

## 🤝 贡献者

| 角色 | 贡献者 |
|---|---|
| 创作者 / 所有者 | [clipsule](https://github.com/clipsule) |
| 代码贡献 / 项目支持 | [mkpoli](https://github.com/mkpoli) |

## 📄 版权与声明

本页面由 **晴れ猫🏳️‍⚧️🍥** 整理发布。所有外部链接均指向第三方站点，其内容与更新由各站点自行维护。

练习时请量力而行，感到喉咙疼痛或声音沙哑就停下来休息，不要勉强硬撑。声音的改变以「月」为单位，坚持比强度更重要。

## 📌 相关链接

- 原始中文手册：[mtf-voice-training.vercel.app](https://mtf-voice-training.vercel.app/)
- 多语言版本手册：[mtf-voice-training-full-language.vercel.app](https://mtf-voice-training-full-language.vercel.app/)
- MTF Wiki：[mtf.wiki](https://mtf.wiki/zh-cn)
- 作者个人主页：[clipsule.github.io/Introduction](https://clipsule.github.io/Introduction/)
