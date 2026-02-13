# Seedance 2.0 Video Prompt Generator 🎬

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code Skill](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://github.com/anthropics/claude-code)

专业的 Seedance 2.0 AI 视频提示词生成技能，帮助用户快速生成高质量的视频提示词。

## ✨ 特性

- 🎯 **3版本输出** - 每次生成简洁版/分镜版/创意版三个版本供选择
- 🔄 **迭代优化** - 支持多轮对话持续优化直到满意
- 📚 **丰富案例库** - 7300+行参考文档，45+精选模板
- 🎨 **风格关键词** - 导演风格/视觉风格/情绪氛围速查
- 📷 **运镜手册** - 完整的运镜类型和技巧参考
- 🎥 **影视理论** - 景别/蒙太奇/叙事/声音/色彩等专业知识
- ❌ **负面提示** - 支持指定不想要的元素

## 📦 安装

### 方法一：手动安装

```bash
# 克隆仓库
git clone https://github.com/lmr1123/seedance-video-prompt.git

# 复制到 Claude Code skills 目录
cp -r seedance-video-prompt ~/.claude/skills/
```

### 方法二：使用 Claude Code CLI

```bash
npx @anthropic-ai/claude-code skill add https://github.com/lmr1123/seedance-video-prompt
```

## 🚀 快速开始

### 在 Claude Code 中使用

1. 启动 Claude Code
2. 输入你的视频需求，例如：
   - "帮我生成一个15秒的短剧虐心片段"
   - "我想做一个产品广告，手机展示"
   - "生成一个赛博朋克风格的城市夜景"
3. 技能会自动生成 3 个版本的提示词供你选择

### 用户输入模板

```
【视频主题】：一句话描述你想表达的内容
【视觉风格】：电影风格/导演风格/色彩风格
【参考素材】：是否有图片/视频/音频参考
【运镜需求】：推拉摇移/一镜到底/快切等
【声音需求】：对白/旁白/音效/配乐风格
【时长要求】：4-15秒具体秒数
【负面需求】：不要出现什么元素
```

## 📁 项目结构

```
seedance-video-prompt/
├── SKILL.md                    # 技能主文件
├── README.md                   # 项目说明
├── LICENSE                     # MIT 许可证
├── agents/
│   └── openai.yaml            # OpenAI Agent 配置
└── references/                 # 参考文档目录
    ├── official-manual.md      # 官方使用手册 (116KB)
    ├── xiaoyunque-cases.md     # 小云雀实测案例库 (79KB)
    ├── personal-collection.md  # 个人收藏案例库 (162KB)
    ├── film-theory-guide.md    # 影视理论基础 (12KB)
    ├── style-keywords.md       # 风格关键词速查 (9KB)
    ├── camera-movement.md      # 运镜词汇手册 (10KB)
    ├── prompt-examples.md      # 提示词示例库 (10KB)
    ├── multimodal-capabilities.md  # 多模态能力列表
    └── platform-specs.md       # 平台规格限制
```

## 📚 参考文档

| 文档 | 说明 |
|------|------|
| [official-manual.md](references/official-manual.md) | 官方使用手册 - 参数规格、10大类实战案例 |
| [xiaoyunque-cases.md](references/xiaoyunque-cases.md) | 小云雀实测案例库 - 15+场景类型 |
| [personal-collection.md](references/personal-collection.md) | 个人收藏案例库 - 45+精选模板 |
| [film-theory-guide.md](references/film-theory-guide.md) | 影视理论基础 - 景别/蒙太奇/叙事等 |
| [style-keywords.md](references/style-keywords.md) | 风格关键词速查 - 导演风格/视觉风格 |
| [camera-movement.md](references/camera-movement.md) | 运镜词汇手册 - 运镜类型/角度视角 |
| [prompt-examples.md](references/prompt-examples.md) | 提示词示例库 - 各类型示例 |

## 🎯 输出格式

每次生成 3 个版本的提示词：

- **版本 A：简洁描述版** - 纯文字描述，适合快速上手
- **版本 B：分镜脚本版** - 带时间轴的分镜描述，控制更精准
- **版本 C：创意风格版** - 强化风格化表达，加入创意元素和特效

## 🔧 支持的场景模板

- 情感短剧（虐心/甜宠/爽剧/搞笑）
- 产品广告（高端/亲民/科技/温暖）
- 特效大片（武侠/科幻/魔幻/动作）
- 舞蹈/运动（跟拍/环绕/第一人称）
- 美食展示（制作过程/成品展示）

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 提交 Pull Request

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

## 🙏 致谢

- [即梦 Seedance](https://jimeng.jianying.com/) - 视频生成平台
- 所有贡献者和案例提供者

---

**Star ⭐ 本项目以获取最新更新！**
