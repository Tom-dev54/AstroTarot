# AstroTarot

一个 React / Vite 写的玄学生活方式 Web App，包含塔罗、星座、八字速览、社区内容和本地心情记录。这个项目原本混在 `WordWizard` 的 Claude 分支和 GitHub Pages 部署里，现在已经独立出来，避免和加密货币分析器、背单词工具混淆。

## 功能

- 塔罗抽牌：支持牌阵、逆位、历史记录和牌面详情
- 星座页：太阳/月亮/上升星座、今日运势、星盘可视化
- 八字速览：根据年月日时生成简化五行与大运展示
- 紫微斗数展示：提供宫位和主星的视觉化排布
- 社区页：模拟话题、动态和评论交互
- 本地记录：使用 localStorage 保存引导状态、出生信息和记录
- AI 解读：可选接入 DeepSeek API 生成塔罗/星座解读

## 技术栈

- React 18
- Vite 5
- Tailwind CSS
- GitHub Pages

## 项目结构

```text
.
├── src/
│   ├── components/      # 通用组件、底部导航、弹层、星空背景等
│   ├── data/            # 塔罗、星座、八字和社区模拟数据
│   ├── pages/           # Home / Tarot / Astrology / Community / Library
│   └── utils/           # localStorage、DeepSeek、会员状态等工具
├── public/              # favicon 和 PWA manifest
├── .github/workflows/   # GitHub Pages 自动部署
├── package.json
└── README.md
```

## 本地运行

```bash
npm install
npm run dev
```

构建：

```bash
npm run build
```

预览：

```bash
npm run preview
```

## AI 解读配置

如果要启用 DeepSeek 解读，在本地创建 `.env.local`：

```text
VITE_DEEPSEEK_KEY=your_deepseek_api_key
```

注意：前端环境变量会进入浏览器包，不适合放长期密钥。正式产品应改成后端代理。

## GitHub Pages

仓库名为 `AstroTarot` 时，Vite 的 `base` 已配置为：

```js
base: '/AstroTarot/'
```

推送到 `master` 后，GitHub Actions 会构建并发布到 `gh-pages` 分支。

## 拆分说明

这个项目来自 `Tom-dev54/WordWizard` 的 `claude/github-integration-docs-QtgGv` 分支。原仓库现在只保留加密货币分析器；背单词工具已拆到 `WordWizard-Vocabulary`；星座/塔罗页面拆到本仓库。
