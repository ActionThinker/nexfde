# CLAUDE.md — nexfde.com

> **NEXFDE**: Enterprise AI Deployment Practice
> **母品牌**: ActionThinker | **方法实验室**: OPClab
> **部署**: GitHub Pages（纯静态 HTML，push 即部署）

## 项目信息

- **站点**: nexfde.com v1.0
- **类型**: 单页落地页（纯静态 HTML + CSS + JS）
- **部署**: GitHub Pages（`ActionThinker/nexfde`），无构建步骤
- **设计系统**: Deep Blue (#102A43) + Tech Blue (#2F6FEB)，Inter 字体
- **AI 构建**: Claude (Anthropic) 辅助，FDE-style AI Deployment 方法

## 关键路径

| 路径 | 用途 |
|:---|:---|
| `index.html` | 主落地页（自包含 CSS/JS） |
| `assets/` | 静态资源（微信二维码、OG 图片） |
| `BUILDLOG.md` | 构建日志（每次迭代记录） |
| `.push-history.jsonl` | 推送历史（自动记录） |
| `CLAUDE.md` | GEO 规则 + 构建指令（本文件） |
| `llms.txt` | AI Agent 站点摘要 |
| `llms-full.txt` | 完整内容 Markdown 摘要 |

## 品牌约束（最高优先级）

1. **页面主角永远是 NEXFDE**，ActionThinker 和 OPClab 仅出现在 Hero 小字和背书区
2. **主 CTA**: 预约部署诊断 | **次 CTA**: 查看服务结构
3. **语气**: 直接、克制、有判断力、不夸张。不用"颠覆""革命""重新定义"
4. **视觉**: 科技极简 + 高端咨询感。不用紫色、不用霓虹、不用粒子动效

---

## GEO 自动化规则（每次修改页面强制执行）

> **目标渠道**: 豆包、DeepSeek、元宝、Kimi
> **核心原则**: AI 搜索不点链接，直接给答案。你的页面必须成为答案里被引用的那个来源。

### A. 页面标题
标题必须包含目标用户会搜索的问题或关键词。
格式: `[核心问题/关键词] | NEXFDE`
当前: `把 AI 从判断推进到生产 | NEXFDE` ✅

### B. 页面描述
描述是 AI 生成答案时的摘要来源，必须包含：做什么 + 为谁做 + 独特价值。
当前: `NEXFDE 以 FDE-style 方法帮助企业把 AI 从方向判断推进到真实业务流程上线。不是卖工具，也不是停在方案文档。` ✅

### C. 结构化数据（JSON-LD Schema）
每个页面必须包含 @graph 模式的 JSON-LD:
- Organization（含 sameAs, logo, contactPoint）
- Service（含 offers, provider 引用）
- FAQPage（至少 5 个 FAQ）
- Article（含 datePublished, dateModified）
- BreadcrumbList

### D. 内容结构
1. 页面必须有清晰的 H1/H2/H3 层级（AI 靠标题理解内容结构）
2. 每个 H2 段落必须能独立回答一个问题
3. 列表和表格优于大段文字（AI 更容易提取）
4. 关键术语首次出现时加 `<strong>` 标记

### E. 内部链接
链接锚文本必须是描述性的:
✅ `<a href="#method">FDE-style 三步方法论</a>`
❌ `<a href="#method">点击这里</a>`

### F. AI 基础设施检查清单
每次部署前检查:
- [ ] llms.txt 内容反映最新页面结构
- [ ] robots.txt AI 爬虫指令正确
- [ ] sitemap.xml 日期更新
- [ ] JSON-LD @graph 完整
- [ ] .well-known/ai 可访问
- [ ] BUILDLOG.md 记录本次变更

### G. 渠道差异化

| 渠道 | 针对性动作 |
|------|-----------|
| 豆包 | Hero 首段可被截取为短答案 |
| DeepSeek | FAQ Schema + 技术方法论标记 + 结构化深度 |
| 元宝 | 标题含"怎么做""为什么"问答词 |
| Kimi | 页面保持足够深度和结构化 |

### H. 构建记录规则
每次对站点做实质性修改后:
1. 更新 BUILDLOG.md（时间倒序，记录决策原因）
2. 更新 .push-history.jsonl（自动记录 push 事件）
3. 提交信息写"为什么"，不写"改了什么"
4. 版本号递增（MAJOR.MINOR.PATCH）

---

## AI 构建透明度

- 本站点由 Claude (Anthropic) 辅助构建
- 构建方法: FDE-style AI Deployment（本站方法论的实际应用）
- AI 参与范围: 代码生成、内容结构化、GEO 优化、JSON-LD Schema 设计
- 人类决策: 品牌定位、业务策略、文案审定、设计方向
- 透明度标记: index.html 含 `ai-disclosure` meta 标签，符合 EU AI Act Article 50

---

## 禁止操作

- ❌ 不要将 ActionThinker 或 OPClab 放到 Hero 主叙事中
- ❌ 不要使用紫色系、霓虹渐变、大面积纯黑背景
- ❌ 不要添加粒子、3D、复杂滚动动效
- ❌ 不要使用"颠覆""革命""重新定义"等夸张文案
- ❌ 不要在页面上使用 Jekyll 或任何构建框架（保持纯静态 HTML）
- ❌ 不要跳过 GEO 检查清单
- ❌ 不要跳过 BUILDLOG.md 记录
