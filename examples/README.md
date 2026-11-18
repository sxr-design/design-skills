# 实战证据

用收录的 impeccable 对我自己的作品集（React + Vite + Tailwind 构建产物）做真实检测。

## 检测记录

- **日期**：2026-11-18
- **命令**：`npx impeccable detect <portfolio>/dist --json`
- **扫描对象**：`dist/index.html` + `dist/assets/*.css`（构建产物，即用户实际看到的页面）
- **退出码**：2（检测完成，发现 3 条 warning 级问题）
- **原始报告**：`portfolio-audit.json`

## 第二次检测：线上部署站点（未成功，留档）

- **命令**：`npx impeccable detect https://sxr-design.github.io/ --json`
- **结果**：导航超时（Navigation timeout 30000ms），4 次重试均失败（stderr 留档 `portfolio-site-audit-stderr.txt`，空结果 `portfolio-site-audit.json`）
- **原因**：GitHub Pages 在国内网络环境下的常见访问超时；对渲染型页面的 URL 扫描受网络质量影响大
- **处置**：以本地构建产物扫描为准（构建产物与线上部署同源，CSS/HTML 级规则检测结论一致）；CI 场景应部署在目标用户网络可达的托管服务上

## 发现的问题

| # | 规则 | 位置 | 内容 | 处置建议 |
|---|---|---|---|---|
| 1 | side-tab | index-*.css:2 | 卡片左侧 2px 彩色边框（AI 生成界面最常见的特征之一） | 换更弱的点缀或移除 |
| 2 | overused-font | index-*.css:2 | 使用 Inter（被 AI 生成界面用滥的字体） | 换成有性格的字体 |
| 3 | dark-glow | index.html | 暗背景上的彩色发光阴影（#1f412b） | 改用中性的 elevation 阴影 |

## 这份报告证明什么

1. **工具链是真实在用的**：不是收藏夹，是对自己作品跑出的真实结果——包括不好看的部分。
2. **检测可以脱离 AI 客户端独立运行**：59 条确定性规则不需要 LLM、不需要 API key，退出码可直接接入 CI。
3. **发现即待办**：以上 3 条是当前作品集的实际改进项。修复后重新运行同一命令即可生成修复前后的对比证据。

## 复现方式

```bash
git clone https://github.com/sxr-design/design-skills
cd <任意前端项目>
npx impeccable detect <构建产物目录> --json
```
