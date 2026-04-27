# CODM 视觉工坊 | AAA Cinematic Prompt Studio

> **CODM 全模型提示词构建工具** — 支持 Seedance 2.0 / Nano Banana / Midjourney V7 三大模型，附带 CODM 百科 & COD 影库参考。

🌐 **在线体验**：[https://sawyercgi.github.io/codm-prompts-builder/](https://sawyercgi.github.io/codm-prompts-builder/)

---

## 功能概览

| 模块 | 说明 |
|------|------|
| 🎬 **Seedance 2.0** | 文生视频 · @角色引用 · 时间轴拆分 · 全局摄影风格 |
| 🍌 **Nano Banana** | Gemini 生图 · 摄影参数四件套 · 文字渲染 · 局部编辑 |
| 🎨 **Midjourney V7** | 气氛图 · 艺术家/电影参考 · --sref/--cref · 参数面板 |
| 📚 **CODM 百科** | 武器/连杀/技能/载具/地图 Wiki 卡片（Fandom API） |
| 🎬 **COD 影库** | 历代 Cinematic 预告片 YouTube 画廊 |

### 辅助功能
- 📊 **提示词质量评分**（S/A/B/C/D 五档，四维雷达）
- 🕘 **历史记录**（localStorage，最多 50 条）
- 📌 **片段收藏夹**（常用描述一键插入）
- 🎲 **随机灵感生成器**（1000 种角色×动作×场景组合）
- ⚖️ **A/B 对比视图**（当前 vs 上次保存）
- 🌐 **双语预览**（中文关键词自动标注英文对照）
- 💾 **自动草稿恢复**（刷新不丢失，24h 过期）
- 🔗 **分享链接**（URL Hash 编码，一键分享配置）
- 🛡️ **合规检测**（敏感词/IP/结构实时扫描）
- ⌨️ **快捷键**（10+ 组合，按 `?` 查看速查表）

---

## 本地运行

```bash
# 方法一：任意 HTTP 服务器
npx http-server -p 8080

# 方法二：Python
python -m http.server 8080

# 方法三：直接浏览器打开
# 双击 index.html 即可（部分功能如 Fandom API 需 HTTP 环境）
```

打开 `http://localhost:8080` 即可使用。

---

## 项目结构

```
codm-prompts-builder/
├── index.html          # 主页面（HTML + CSS + JS 单文件）
├── README.md           # 项目说明
├── CONTRIBUTING.md     # 贡献指南
├── LICENSE             # MIT 开源协议
└── .gitignore          # Git 忽略规则
```

> **为什么单文件？** GitHub Pages 零配置部署，无需构建步骤，任何人 clone 后直接打开即可使用。

---

## 技术栈

- **纯前端**：HTML5 + CSS3 + Vanilla JS（零依赖）
- **设计系统**：CSS 自定义属性（Linear/Vercel/Stripe 风格）
- **数据存储**：localStorage（历史/收藏/草稿）
- **外部 API**：Fandom Wiki API（百科图片加载）
- **字体**：Inter + Noto Sans SC + JetBrains Mono

---

## 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl+Enter` | 复制提示词 |
| `Ctrl+S` | 保存到历史 |
| `Ctrl+L` | 切换语言 EN/中文 |
| `Ctrl+H` | 历史面板 |
| `Ctrl+I` | 导入配置 |
| `Ctrl+G` | 随机灵感 |
| `Ctrl+1~5` | 切换模型 Tab |
| `Ctrl+Shift+R` | 重置全部 |
| `?` | 快捷键帮助 |
| `Esc` | 关闭弹窗 |

---

## 协作开发

详见 [CONTRIBUTING.md](./CONTRIBUTING.md)。

### 快速开始

```bash
# 1. Fork 仓库
# 2. Clone 到本地
git clone https://github.com/<你的用户名>/codm-prompts-builder.git
cd codm-prompts-builder

# 3. 创建分支
git checkout -b feature/你的功能名

# 4. 开发并提交
git add .
git commit -m "feat: 你的功能描述"

# 5. 推送并创建 PR
git push origin feature/你的功能名
```

---

## License

[MIT](./LICENSE)
