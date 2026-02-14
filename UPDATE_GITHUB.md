# 更新本项目到 GitHub

## 一键执行（推荐）

```bash
cd ~/.claude/skills/seedance-video-prompt

# 方式1：SSH（有配置密钥）
git push origin main

# 方式2：HTTPS（需要Token）
git remote set-url origin https://github.com/lmr1123/seedance-video-prompt.git
git push origin main
```

---

## 完整流程（遇到冲突时）

```bash
cd ~/.claude/skills/seedance-video-prompt

# 1. 添加所有更改
git add -A

# 2. 写提交信息
git commit -m "$(cat <<'EOF'
feat: 更新说明

- 变更点1
- 变更点2

🤖 Generated with Claude Code
Co-Authored-By: Claude <noreply@anthropic.com>
EOF
)"

# 3. 拉取远程并rebase
git pull origin main --rebase

# 4. 推送到GitHub
git push origin main
```

---

## 快速提交模板

根据更新类型选择：

### 功能更新（feat）
```bash
git commit -m "feat: 新功能名称

- 新增xxx功能
- 优化xxx体验

🤖 Generated with Claude Code"
```

### 修复问题（fix）
```bash
git commit -m "fix: 问题描述

- 修复xxx问题
- 优化xxx逻辑

🤖 Generated with Claude Code"
```

### 文档更新（docs）
```bash
git commit -m "docs: 文档更新

- 更新README说明
- 完善xxx文档

🤖 Generated with Claude Code"
```

---

## 常用命令速查

| 命令 | 说明 |
|------|------|
| `git status` | 查看更改状态 |
| `git diff` | 查看未暂存的更改 |
| `git add -A` | 暂存所有更改 |
| `git log --oneline` | 查看提交历史 |
| `git push origin main` | 推送到GitHub |

---

## 故障排除

### 被拒绝（远程有更新）
```bash
git pull origin main --rebase
git push origin main
```

### 需要SSH
```bash
git remote set-url origin git@github.com:lmr1123/seedance-video-prompt.git
git push origin main
```

### 需要HTTPS Token
```bash
git remote set-url origin https://ghp_xxxxxxxxxxxx@github.com/lmr1123/seedance-video-prompt.git
git push origin main
```
