# Seedance 2.0 视频提示词生成器 🎬

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://github.com/anthropics/claude-code)

专业的 Seedance 2.0 AI 视频提示词生成工具。根据用户需求生成结构化、可直接使用的视频提示词，充分利用即梦平台的多模态能力和高质量视频描述。

---

## ✨ 核心特性

### 🎯 严格工作流执行
- **决策树自动判断**：时长路由 → 素材路由 → 复杂度判断
- **强制输出规范**：每次输出包含执行路径声明
- **质量自检清单**：6项检查确保输出质量

### 📦 开箱即用
- **3 套模板**：简洁版 / 分镜版 / 多模态版
- **自动分段**：>15秒自动切分，提供衔接点
- **图片匹配**：无素材时自动推荐风格并生成提示词

### 📚 丰富参考库
- 7300+ 行参考文档
- 45+ 精选模板
- 10+ 种导演风格关键词

---

## 🚀 快速开始

### 方式一：命令行安装

```bash
# 使用 Claude Code CLI 安装
npx @anthropic-ai/claude-code skill add https://github.com/lmr1123/seedance-video-prompt
```

### 方式二：手动安装

```bash
# 克隆仓库
git clone https://github.com/lmr1123/seedance-video-prompt.git

# 复制到 skills 目录
cp -r seedance-video-prompt ~/.claude/skills/
```

---

## 📖 使用方法

### 1. 告诉我你的需求

**简单输入**：
- "帮我生成一个10秒的猫咪打盹视频"
- "做一个15秒的赛博朋克城市夜景"
- "胡金铨风格的客栈武打，竖屏10秒"

**详细输入**（可选）：
```
【视频主题】：猫咪在咖啡馆打盹
【视觉风格】：日系清新治愈
【时长】：10秒
【比例】：9:16
```

### 2. 我会自动处理

```
【本轮执行路径】
- 时长路由：单段生成
- 素材路由：无素材需生成图片
- 复杂度判断：简单
- 采用模板：模板A

【决策说明】
用户要求10秒≤15秒，单主体单动作故判断为简单，
无素材但主题为生活场景，输出简洁版提示词。
```

### 3. 获取完整提示词

我会输出可直接复制到即梦的：
- 完整提示词
- 声音设计方案
- 禁止项声明
- 如需素材：附带图片生成提示词

---

## 📁 项目结构

```
seedance-video-prompt/
├── SKILL.md              # 技能主文件（含完整工作流）
├── QUICKSTART.md         # 快速上手指南
├── README.md             # 本文档
├── LICENSE               # MIT 许可证
├── agents/
│   └── openai.yaml       # Agent 配置
└── references/           # 参考文档
    ├── official-manual.md      # 官方手册
    ├── personal-collection.md  # 精选模板
    ├── style-combinations.md  # 风格组合
    ├── beginner-qa-system.md   # 新手问答
    ├── film-theory-guide.md    # 影视理论
    ├── style-keywords.md      # 风格关键词
    ├── camera-movement.md     # 运镜手册
    └── prompt-examples.md     # 示例库
```

---

## 🛠️ 工作流决策树

```
【第一轮：时长路由】
├── ≤15秒 → 单段生成
└── >15秒 → 超长分段策略

【第二轮：素材路由】
├── 有素材 → 模板C（多模态参考）
├── 无素材需生成 → 图片风格匹配
└── 纯文本 → 判断复杂度

【第三轮：复杂度判断】
├── 简单（单主体+单动作）→ 模板A
├── 中等（多动作+风格化）→ 模板A/B
└── 复杂（多镜头切换）→ 模板B
```

---

## 📋 输出规范

### 默认输出格式

```
时长: X秒
画面比例: 16:9 / 9:16
风格: xxx

【本轮执行路径】
...

提示词:
...

声音设计:
- 配乐: xxx
- 音效: xxx

禁止:
- xxx

参考素材准备（如需要）:
- @图片1 [用途]
  图片生成提示词: xxx
```

### 多版本探索（用户要求时）

- **版本 A**：简洁描述版（模板A）
- **版本 B**：分镜脚本版（模板B）
- **版本 C**：创意风格版（强化风格）

---

## 💡 常见示例

### 示例 1：简单场景

**输入**：
> 猫咪在咖啡馆打盹，8秒

**输出路径**：
```
- 时长路由：单段生成
- 素材路由：无素材
- 复杂度：简单
- 模板：模板A
```

### 示例 2：有素材参考

**输入**：
> 参考@图1的男人形象，在@图2的电梯中，完全参考@视频1的运镜

**输出路径**：
```
- 时长路由：单段生成
- 素材路由：有素材
- 复杂度：中等
- 模板：模板C
```

### 示例 3：超长视频

**输入**：
> 做一段30秒的仙侠剑客出场

**输出路径**：
```
- 时长路由：超长分段（2段）
- 素材路由：无素材需生成
- 复杂度：复杂
- 模板：超长分段策略
```

---

## 🎨 风格速查

| 导演/风格 | 关键词 | 适用场景 |
|----------|--------|---------|
| **王家卫** | 慢快门、霓虹灯、黄绿色调 | 文艺、都市 |
| **韦斯·安德森** | 对称构图、糖果色、童话感 | 奇幻、广告 |
| **张艺谋** | 大色块、高饱和、仪式感 | 史诗、古装 |
| **赛博朋克** | 霓虹灯、紫蓝粉、雨天 | 科幻、夜景 |
| **胡金铨** | 水墨留白、东方意境、禅意、京剧身段、极简构图 | 武侠、古装、国风 |
| **诺兰** | IMAX、实景感、宏大场面 | 科幻、悬疑 |

---

## 📖 进阶文档

| 文档 | 说明 |
|------|------|
| [SKILL.md](SKILL.md) | 完整技术规格和工作流 |
| [QUICKSTART.md](QUICKSTART.md) | 3 步快速上手 |
| [references/](references/) | 详细参考文档 |

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

---

## 📄 许可证

MIT License - 详见 [LICENSE](LICENSE)

---

## 🙏 致谢

- [即梦 Seedance](https://jimeng.jianying.com/) - AI 视频生成平台
- 所有贡献者和案例提供者

---

**⭐ Star 本项目获取最新更新！**
