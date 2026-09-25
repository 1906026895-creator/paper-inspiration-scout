# Paper Inspiration Scout

一个同时支持 Codex 和 Claude Code 的单篇论文粗读 skill。它不追求逐段讲完全文，而是分轮产出三个结果：

1. **文章模型**：问题、核心想法、方法、证据与结论边界。
2. **灵感卡**：从论文动作中提炼可迁移的研究思路。
3. **最小验证方案**：用最低合理成本判断灵感是否值得继续投入。

适用于快速看懂论文、从文献寻找课题或实验灵感、判断是否值得精读，以及初步评估复现路线。逐句精读、系统综述和论文写作不属于本 skill 的主要范围。

## 目录结构

```text
paper-inspiration-scout/
├── SKILL.md
├── agents/
│   └── openai.yaml
├── references/
│   ├── experimental-studies.md
│   └── ml-ai4s.md
└── claude/
    └── paper-inspiration-scout/
        ├── SKILL.md
        └── references/
            ├── experimental-studies.md
            └── ml-ai4s.md
```

根目录是 Codex 包；`claude/paper-inspiration-scout/` 是可独立复制的 Claude Code 包。两者的 reference 都只在论文类型匹配时加载。

## 安装

### Codex

```bash
git clone https://github.com/1906026895-creator/paper-inspiration-scout.git ~/.codex/skills/paper-inspiration-scout
```

### Claude Code

```bash
git clone https://github.com/1906026895-creator/paper-inspiration-scout.git paper-inspiration-scout-repo
mkdir -p ~/.claude/skills
cp -R paper-inspiration-scout-repo/claude/paper-inspiration-scout ~/.claude/skills/
```

## 使用

### Codex

```text
请使用 $paper-inspiration-scout 粗读这篇论文，先给我粗读地图，再分轮建立文章模型、灵感卡和最小验证方案。
```

### Claude Code

```text
/paper-inspiration-scout 请粗读这篇论文，先给我粗读地图，再分轮建立文章模型、灵感卡和最小验证方案。
```

skill 首轮只给粗读地图。后续可以使用 `继续`、`深入`、`跳过`、`灵感`、`验证`、`复现`、`总结` 或 `暂停` 控制阅读路线。
