# design-skills — 我的 AI 设计工具链

> English: My curated collection of agent skills for design work — two self-authored skills for job-hunting materials (JD clustering & portfolio case building), plus attributed copies of the best public design skills I actually use, with my adaptation notes and real audit evidence.

这个库回答一个问题：**一个产品设计师用 AI，工具链应该长什么样？**

## 为什么建这个库

2025 年起，AI 编码工具（Kimi Code、Claude Code、Codex 等）开始支持 Skill——写给 AI 看的专业工作流。设计师用 AI 的差距不在会不会聊天，而在**有没有把自己的方法论沉淀成 AI 可执行的流程**。

这个库是我的完整答案，分三层：

| 层 | 目录 | 解决什么 |
|---|---|---|
| **求职材料层（自研）** | `jd-translator/`、`case-forge/` | 多 JD 怎么聚类、简历要不要分版、项目素材怎么变成可信的作品集案例和面试叙事 |
| **UI 质量层（收录+适配）** | `impeccable/` | AI 生成界面的质量把关：59 条确定性规则 + 24 个设计命令 |
| **风格参照层（收录+策展）** | `awesome-design-md/` | 42 份知名产品的 DESIGN.md，作为"让 AI 按指定设计语言出图"的参照库 |

三层互补不重叠：参照层给 AI 风格，质量层给 AI 标准，求职层把我自己的工作变成证据。

## 使用场景

- **日常设计工作**：从 `awesome-design-md/` 复制一份 DESIGN.md 进项目 → 让 AI 生成符合该风格的界面 → 用 `impeccable audit` 验收。
- **求职季**：用 `jd-translator` 分析目标岗位、决定简历策略 → 用 `case-forge` 把项目素材锻造成作品集案例 → 用 `impeccable` 给作品集本身做质量体检。
- **学习 Skill 设计**：三个不同类型的 Skill（自研工作流型、收录命令型、收录数据集型）放一起，可以看出 Agent Skill 这个形态的能力边界。

## 目录结构

```text
design-skills/
├── README.md                 ← 本文件
├── jd-translator/            ← 自研：JD 聚类与简历分版（MIT，独立仓库 sxr-design/jd-translator）
├── case-forge/               ← 自研：作品集案例锻造与面试叙事（MIT，独立仓库 sxr-design/case-forge）
├── impeccable/               ← 收录：UI 质量 Skill（Apache 2.0，附 SOURCES.md 适配说明）
├── awesome-design-md/        ← 收录：42 份 DESIGN.md 策展（MIT，附 CURATION.md 挑选理由）
└── examples/                 ← 实战证据：impeccable 对我自己作品集的检测报告
```

## 来源与许可证

| 目录 | 作者 | 许可证 | 说明 |
|---|---|---|---|
| jd-translator | sxr-design（我） | MIT | 原创 |
| case-forge | sxr-design（我） | MIT | 原创 |
| impeccable | Paul Bakaus | Apache 2.0 | 收录发布版，未改代码，见目录内 SOURCES.md |
| awesome-design-md | VoltAgent | MIT | 收录发布版，未改原文，见目录内 CURATION.md |

所有第三方内容均按许可证要求保留 LICENSE 并注明来源。收录不等于原创——哪部分是我做的、哪部分是我选的、哪部分是我用的，都写清楚。

## 我的适配记录

- **impeccable**：安装为 Kimi Code 用户级 Skill，用于 UI 质量检查；我的两个自研 Skill 借鉴了它的命令路由和反模式清单写法。实战报告见 `examples/`。
- **awesome-design-md**：从上游 84 份中按四条标准保留 42 份实际使用的（行业相关、辨识度、规范完整度、参照多样性），挑选理由见目录内 CURATION.md。
- **自研部分**：jd-translator 与 case-forge 互为上下游，组成"JD → 简历 → 作品集 → 面试"的完整求职材料管线；各自独立仓库持续维护。

## 许可

各子目录内容分别遵循其自带许可证；本 README 及我的原创说明文件以 MIT 许可共享。
