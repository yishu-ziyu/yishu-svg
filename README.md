# 🎨 YiShu SVG - 智能教学动画生成器

> **用自然语言，让抽象概念动起来**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Powered by GLM](https://img.shields.io/badge/Powered%20by-GLM--4.7-green)](https://open.bigmodel.cn)

---

## 💡 项目初心

作为一名经济学自学者，我经常遇到这样的困境：

- 📉 **看不懂图像**：教科书上的供需曲线、效用函数，静态图片难以理解变化过程
- 🧮 **想象不出来**：边际成本、弹性系数，抽象概念难以在脑海中具象化
- ⏰ **制作成本高**：想做动画演示，但 AE、Manim 学习曲线太陡

**YiShu SVG 就是为了解决这个问题**：只需用自然语言描述你想看到的概念，AI 就能即时生成动态 SVG 动画，让抽象变具象，让静态变动态。

---

## ✨ 功能特性

| 功能                | 描述                                     |
| ------------------- | ---------------------------------------- |
| 🗣️ **自然语言输入** | 用中文描述想要的动画，无需编程           |
| 🎬 **即时生成 SVG** | 秒级生成带动画效果的矢量图形             |
| 🎨 **多种风格**     | Manim 科学风格、时间轴、极简、艺术风格   |
| 📐 **学科覆盖**     | 数学、物理、经济学、神经网络、历史时间轴 |
| 📝 **代码可编辑**   | 生成的 SVG 代码可查看、修改、复用        |
| 💾 **一键下载**     | 导出为 .svg 文件，无限放大不失真         |
| 🔌 **双 API 支持**  | 智谱 GLM-4.7 + NVIDIA NIM 双引擎         |

---

## 🚀 快速开始

### 在线使用（推荐）

直接打开 `index.html` 即可使用，无需安装任何依赖：

```bash
# 克隆仓库
git clone https://github.com/yishu-ziyu/yishu-svg.git

# 打开
open yishu-svg/index.html
# 或双击 index.html 在浏览器中打开
```

### 首次配置（可选）

项目已预配置 API Key，开箱即用。如需使用自己的 Key：

1. 点击右上角「⚙️ API 设置」
2. 选择 API 提供商（智谱 / NVIDIA）
3. 输入你的 API Key
4. 保存设置

---

## 📖 使用指南

### 基础用法

1. **选择风格**：顶部选择动画风格（Manim / 时间轴 / 极简 / 艺术）
2. **输入主题**：在左侧输入教学主题，如「供需曲线」
3. **添加描述**（可选）：详细描述动画效果
4. **点击生成**：等待 AI 生成动画（通常 5-15 秒）
5. **查看/下载**：预览动画，下载 SVG 文件

### 快捷模板

点击模板卡片快速填充：

| 模板          | 描述                          |
| ------------- | ----------------------------- |
| 📊 数学函数   | 二次函数 y = x²，动态绘制曲线 |
| 🧠 神经网络   | 展示 ANN 结构和数据流动       |
| ⚛️ 物理过程   | 动量守恒、碰撞动画            |
| 📅 历史时间轴 | 事件节点依次点亮              |

### 经济学示例

以下是一些经济学常用的 Prompt 示例：

```
📉 供需曲线
主题：微观经济学供需曲线
描述：展示向下倾斜的需求曲线和向上倾斜的供给曲线，两条曲线交于均衡点E，
     标注均衡价格P*和均衡数量Q*，曲线逐步绘制

📊 边际成本曲线
主题：边际成本与平均成本曲线
描述：U形的边际成本曲线和平均成本曲线，边际成本曲线穿过平均成本曲线最低点，
     动态标注交点

📈 GDP增长时间轴
主题：中国 GDP 增长历程
描述：横向时间轴从1980到2024，标注重要节点：
     1992改革开放、2001入WTO、2010超日本、2020第二经济体
```

---

## 🛠️ 技术架构

```
yishu-svg/
├── index.html              # 主应用（纯前端，开箱即用）
├── PRD.md                  # 产品需求文档
├── prompts/
│   └── svg-animator-system.md   # AI System Prompt
└── examples/
    ├── quadratic-function.svg   # 二次函数示例
    └── neural-network.svg       # 神经网络示例
```

### 支持的 API

| Provider   | 端点                       | 模型                                |
| ---------- | -------------------------- | ----------------------------------- |
| 智谱 AI    | `open.bigmodel.cn`         | glm-4.7-flash (免费)                |
| NVIDIA NIM | `integrate.api.nvidia.com` | z-ai/glm4.7, minimaxai/minimax-m2.1 |

---

## 📝 SVG 动画原理

生成的 SVG 使用以下技术实现动画：

```svg
<!-- CSS @keyframes 动画 -->
<style>
  @keyframes draw {
    from { stroke-dashoffset: 1000; }
    to { stroke-dashoffset: 0; }
  }
  .curve { animation: draw 3s ease-out forwards; }
</style>

<!-- SVG SMIL 动画 -->
<circle cx="100" cy="100" r="10">
  <animate attributeName="cx" from="100" to="500" dur="2s" />
</circle>
```

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

- 🐛 报告 Bug
- 💡 建议新功能
- 📚 分享你的使用案例

---

## 📄 License

[MIT License](LICENSE)

---

## 🙏 致谢

- [智谱 AI](https://open.bigmodel.cn) - GLM-4.7 模型支持
- [NVIDIA NIM](https://build.nvidia.com) - 模型 API 服务
- [TailwindCSS](https://tailwindcss.com) - UI 样式框架

---

**Made with ❤️ by YiShu · 让学习可视化**
