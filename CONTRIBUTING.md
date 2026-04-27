# 贡献指南 | Contributing Guide

感谢你参与 **CODM 视觉工坊** 的开发！请在提交前阅读以下规范。

---

## 开发环境

- 纯前端项目，无需安装任何依赖
- 任意 HTTP 服务器即可本地运行（推荐 `npx http-server`）
- 建议使用 VS Code / CodeBuddy

---

## 分支规范

| 分支 | 用途 |
|------|------|
| `main` | 线上稳定版，GitHub Pages 自动部署 |
| `feature/*` | 新功能开发 |
| `fix/*` | Bug 修复 |
| `refactor/*` | 代码重构 |

**不要直接 push 到 main**，请通过 Pull Request 提交。

---

## 提交规范

使用 [Conventional Commits](https://www.conventionalcommits.org/) 格式：

```
feat: 新增随机灵感生成器
fix: 修复移动端 Tag 点击无响应
style: 优化 Section 折叠动画
refactor: 拆分敏感词检测逻辑
docs: 更新 README 功能列表
```

### 常用前缀

| 前缀 | 说明 |
|------|------|
| `feat` | 新功能 |
| `fix` | Bug 修复 |
| `style` | 样式/UI 调整（不影响逻辑） |
| `refactor` | 代码重构（不改功能） |
| `docs` | 文档变更 |
| `perf` | 性能优化 |
| `data` | 数据更新（武器库/百科等） |

---

## 代码规范

### CSS
- 使用 CSS 自定义属性（`var(--xxx)`），不硬编码颜色/间距
- 新组件样式放在对应的 `/* ============ XXX ============ */` 分隔注释块中
- 移动端适配写在 `@media` 块内

### JavaScript
- 所有状态存储在全局 `state` 对象中
- 新模型的 prompt 构建器写成独立函数 `buildXxx()`
- 新功能通过 monkey-patch `updatePrompt` 链式挂载
- `localStorage` key 统一前缀 `codm_prompt_`

### HTML
- 模型专属区域加 `model-only for-xxx` class
- Section 使用 `collapsed` class 控制展开/折叠
- Tag 使用 `data-val` 存英文值，`data-zh` 存中文标签

---

## 数据更新

### CODM 百科（武器/地图等）
- 数据在 `CODM_DB` 对象中
- 格式：`{ n: '显示名', w: 'Wiki页面Key' }`
- 图片通过 Fandom API 自动加载，无需手动配置

### COD 影库
- 数据在 `COD_CINEMA` 对象中
- 格式：`{ title: '标题', year: 年份, yt: 'YouTube视频ID' }`

### 敏感词库
- 在 `SENSITIVE_RULES` 对象中
- 分四级：`hardBan`（硬红线）/ `ipExplicit`（显性IP）/ `ipHidden`（隐性IP）/ `discomfort`（不适）

---

## PR 检查清单

提交 PR 前请确认：

- [ ] 本地 `http-server` 启动后页面无报错
- [ ] 三个模型 Tab 切换正常
- [ ] 移动端（Chrome DevTools 模拟）布局不错乱
- [ ] 新增的 Tag 有 `data-val` 和 `data-zh` 属性
- [ ] 合规检测不误报
- [ ] 快捷键不冲突

---

## 联系

有问题可在 GitHub Issues 中提出，或直接在 PR 中讨论。
