# Hermes Skills by tugou-cn

AI顾问工作流技能包，帮你快速处理客户AI应用的分析、优化、诊断任务。

## 安装方法

### 方式1：直接安装（推荐）

```bash
# 安装单个skill
hermes skill install https://github.com/Miles-api/hermes-skills/ai-effect-diagnosis

# 安装整个仓库的所有skills
hermes skill install https://github.com/Miles-api/hermes-skills
```

### 方式2：手动克隆

```bash
cd ~/.hermes/profiles/$(hermes config get profiles.active)/skills
git clone https://github.com/Miles-api/hermes-skills.git
```

## 可用Skills

### ai-effect-diagnosis

**用途**：分析客户AI应用使用数据，生成效果诊断报告

**典型场景**：
- LinkedIn获客工具效果下滑，不知道哪里出问题
- 客服AI回复质量需要优化
- 定期给客户出"本周AI效果分析"

**快速开始**：
```bash
# 1. 采集客户数据
tail -n 1000 /var/log/app.log > ~/ai_data.log

# 2. 跑诊断
hermes chat -m "用ai-effect-diagnosis分析 ~/ai_data.log"

# 3. Review后发客户
# （报告是初步分析，你需要改成可执行建议再发）
```

[查看完整文档](./ai-effect-diagnosis/SKILL.md)

---

## 贡献

欢迎提交新的skills或改进现有的：

```bash
# Fork这个仓库
# 创建新skill
mkdir my-new-skill
cd my-new-skill
cat > SKILL.md << 'EOF'
---
name: my-new-skill
description: 你的skill描述
version: 1.0.0
---

# 完整的skill文档...
EOF

# 提交PR
git add .
git commit -m "Add my-new-skill"
git push origin main
```

## License

MIT

## 作者

tugou-cn - 传统企业AI技术顾问
