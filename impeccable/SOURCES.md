# 来源与适配说明

## 来源

- **上游项目**：[impeccable](https://github.com/pbakaus/impeccable)（作者 Paul Bakaus）
- **许可证**：Apache 2.0（本目录内的 `LICENSE` 为上游许可证原文，未做修改）
- **收录方式**：收录的是上游发布版内容，未修改源码。

## 为什么收录

这是目前公开的设计类 Agent Skill 中完成度最高的项目之一（24 个命令、59 条确定性检测规则、live 浏览器迭代），是研究"如何把设计方法论编码成 AI 工作流"的最佳样本，也是我这个库里自研 Skill 的重要设计参考。

## 我的使用与适配记录

- **使用方式**：作为 Kimi Code 的用户级 Skill 安装使用（`D:/design-skills/impeccable`），通过 `impeccable` 启动器命令运行。
- **在工作流中的位置**：负责 UI 质量层——用 `audit` / `critique` 命令检查自己作品集的界面质量（报告见 `../examples/`）；我的两个自研 Skill（jd-translator、case-forge）负责求职材料层。三层互补，不重叠。
- **适配内容**：未修改上游代码；仅按官方文档在自己的环境中完成安装与配置。
- **借鉴到我自研 Skill 的部分**：命令式路由表、"明确列出禁止项"的反模式清单写法。详见 case-forge/README 的"设计参考"一节。

## 许可证要点（Apache 2.0）

允许自由使用、修改与再分发，需保留许可证与版权声明。本目录已完整保留上游 LICENSE 与本说明。
