# NEXFDE — Enterprise AI Deployment

> **把 AI 从判断推进到生产**
>
> [nexfde.com](https://nexfde.com)

---

## 这个站点本身就是一个 AI 构建案例

NEXFDE 的官网不仅是品牌落地页，更是 **FDE-style AI Deployment 方法论的实际应用展示**。

### 它能告诉潜在客户什么？

| 你在站点上看到的 | 背后展示的能力 |
|-----------------|--------------|
| AI 可读的 llms.txt + JSON-LD @graph | 我们知道如何让 AI 理解业务 |
| robots.txt AI 爬虫精准控制 | 我们理解 AI 技术栈的每一层 |
| GEO 优化（豆包/DeepSeek/元宝/Kimi） | 我们知道怎么让内容被 AI 搜索引用 |
| 纯静态 HTML，push 即部署 | 我们追求极简、可维护的技术方案 |
| BUILDLOG.md 持续构建日志 | 我们有方法论、有纪律、有记录 |
| AI 透明度元数据 | 我们走在 EU AI Act 合规前沿 |

### 技术栈

- **前端**: 纯静态 HTML + CSS + JS（零框架依赖）
- **部署**: GitHub Pages + 自定义域名
- **AI 基础设施**: llms.txt / llms-full.txt / robots.txt / sitemap.xml / .well-known/ai
- **结构化数据**: JSON-LD @graph（Organization + Service + FAQPage + Article + BreadcrumbList）
- **GEO**: 针对豆包、DeepSeek、元宝、Kimi 四渠道优化
- **构建工具**: Claude Code (Anthropic)

### 构建理念

这个站点的构建过程遵循 NEXFDE 自身的方法论：

1. **Judgment（判断）**: 先确定品牌定位、目标受众、转化目标，再开始构建
2. **Pilot（试点）**: 先做一个完整可用的单页落地页，快速上线验证
3. **Rollout（上线）**: 持续迭代——AI 基础设施、GEO 优化、构建日志

### 项目结构

```
nexfde.com/
├── index.html              # 主落地页（13 区块，自包含）
├── llms.txt                # AI Agent 站点摘要
├── llms-full.txt           # 完整内容 Markdown
├── robots.txt              # AI 爬虫指令
├── sitemap.xml             # 站点地图
├── CLAUDE.md               # GEO 规则 + 构建指令
├── BUILDLOG.md             # 构建日志
├── README.md               # 本文件
├── .push-history.jsonl     # 推送追踪
├── CNAME                   # nexfde.com
├── .nojekyll               # 纯静态（非 Jekyll）
└── assets/
    ├── wechat-qr.png       # 微信联系二维码
    └── nexfde-og.png       # OG 社交分享图
```

### 品牌关系

- **NEXFDE** — 企业 AI 落地专项服务品牌
- **ActionThinker** — 母品牌，提供创始人与内容信任背书
- **OPClab** — 方法论实验室，提供实验验证背书

---

## 联系

- 邮箱: lu@NexFDE.com
- 微信: ActionThinker
- 母品牌: [actionthinker.com](https://actionthinker.com)

---

*本站点由 Claude (Anthropic) 辅助构建，采用 FDE-style AI Deployment 方法。每一次构建决策都记录在 BUILDLOG.md 中。*
