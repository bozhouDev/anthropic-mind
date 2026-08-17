# Anthropic Mind

一个 Claude Agent Skill。从 428 篇 Anthropic 公开材料里蒸馏出他们的判断框架，用来回答「这个取舍按 Anthropic 会怎么做」——给一个判断，带失效条件和出处。

仓库里同时保留了全部原始语料和蒸馏过程，任何一条结论都能查回原文。

## 目录结构

```
SKILL.md                入口：路由 + 8 条世界观模型 + 输出契约
references/
├── worldview.md        8 条世界观模型的完整证据与失效条件
├── gates.md            门禁：禁区、禁止话术、置信度分级
├── d-engineering.md    工程（agent / 工具 / 上下文 / 评估）
├── d-research.md       研究品味与安全方法
├── d-character.md      品格设计与价值冲突裁决
├── d-policy.md         时间表 / 政策 / 趋势判断
├── d-business.md       商业与组织
├── precedents.md       21 条决策先例 + 翻案清单
└── eval.md             30 题验收测试集

research/
├── 索引.md             427 篇原文索引
├── 00-canonical/       Claude's Constitution
├── 01-engineering/     工程博客 32
├── 02-research/        研究与可解释性 170
├── 03-news/            文化向长文 4
├── 05-essays/          个人长文与 Import AI 79
├── 06-podcasts/        播客与演讲 15
├── 07-youtube/         官方视频转录 55
├── 08-x/               X 长文与线程 71
└── distill/            10 份蒸馏中间产物
```

## 安装

```bash
git clone https://github.com/bozhouDev/anthropic-mind.git ~/.claude/skills/anthropic-mind
```

只要 skill 本体（284KB，不含语料）：

```bash
git clone --depth 1 --filter=blob:none --sparse https://github.com/bozhouDev/anthropic-mind.git ~/.claude/skills/anthropic-mind
cd ~/.claude/skills/anthropic-mind && git sparse-checkout set references
```

## 来源

`research/` 下的原始材料版权归 Anthropic 及各原作者所有，仅为研究与可复现性收录，详见 [research/NOTICE.md](research/NOTICE.md)。原创部分（`SKILL.md`、`references/`、`research/distill/`）以 MIT 发布。

语料截止 2026-08-16。
