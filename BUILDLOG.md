# NEXFDE Build Log

> 每一次构建决策，都是 FDE 方法论的实际应用记录。
> 这不是开发日志——这是 NEXFDE 的知识资产和营销案例。

---

## 2026-07-02 — AI-Native 基础设施全面初始化

**版本**: v1.1.0
**提交**: `c0594eb`

### 决策背景
NEXFDE 站点不只是品牌落地页。它必须成为 FDE-style AI Deployment 方法的**活案例**。
用户在浏览网站时，不仅能看到"我们做什么"，还能从站点的构建方式中感受到"我们怎么做"。

### 具体变更

**AI-Native 基础设施（新增）:**
- `llms.txt` — AI Agent 站点摘要（Markdown 格式，完整站点结构 + 方法论关键词）
- `llms-full.txt` — 完整页面内容 Markdown 摘要（供 RAG 管道使用）
- `robots.txt` — AI 爬虫精准指令（允许搜索型 AI，禁止训练型 AI）
- `sitemap.xml` — 站点地图（含 lastmod 日期）
- `.well-known/ai` — AI 发现端点（JSON 格式，描述站点能力和 AI 透明度）
- `CLAUDE.md` — GEO 规则引擎 + 构建指令（8 条 GEO 规则 + AI 透明度规则 + 构建记录规则）
- `README.md` — 项目案例故事（展示站点作为 AI 构建案例的完整叙事）

**GEO 增强（修改 index.html）:**
- JSON-LD 从两个独立块升级为 @graph 模式（Organization + Service + FAQPage + Article + BreadcrumbList）
- 添加 AI 透明度元数据（ai-disclosure, ai-system, ai-operator）
- 修复 og:image（创建 assets/nexfde-og.png）
- 补充 twitter:image、hreflang、robots meta 标签
- 为所有 SVG 图标添加 aria-label
- 页脚添加 AI 构建标识

**Build Log 系统（新增）:**
- `BUILDLOG.md` — 本文件，按时间倒序记录每次构建决策
- `.push-history.jsonl` — 推送追踪（每次 git push 自动记录）
- index.html 嵌入构建版本元数据注释

### 方法论实践
本次构建严格遵循 NEXFDE 自身的三步方法：

1. **Judgment（判断）**: 分析站点当前状态 → 识别 AI/GEO 能力缺口 → 确定优先级
2. **Pilot（试点）**: 创建所有基础设施文件 → 增强 JSON-LD → 修复关键 SEO 问题
3. **Rollout（上线）**: 一次性推送所有变更 → 验证每个端点可访问 → 建立持续构建纪律

### 为什么这样做
- 客户问"你们真的懂 AI 落地吗？"——这个站点就是答案
- AI 搜索渠道（豆包/DeepSeek/元宝/Kimi）需要结构化数据才能引用我们
- EU AI Act Article 50 将于 2026-08-02 生效，AI 透明度合规宜早不宜迟
- 构建过程本身是有价值的知识资产——记录它，未来可以被引用、被学习、被营销

---

## 2026-07-02 (Earlier) — 初始落地页上线

**版本**: v1.0.0
**提交**: `1c0a195`

### 决策背景
NEXFDE 作为 ActionThinker 旗下的企业 AI 落地专项品牌，需要独立的在线存在。
选择纯静态 HTML（非 Jekyll/框架）的原因：最简部署、零构建步骤、极速加载。

### 具体变更
- 创建完整 13 区块单页落地页（nav, hero, pain points, value props, 3-step path, deliverables, service packages, why NEXFDE, endorsements, fit/not-fit, FAQ, CTA, footer）
- 设计系统：Deep Blue (#102A43) + Tech Blue (#2F6FEB)，Inter 字体
- GitHub Pages 部署 + nexfde.com 自定义域名
- 微信联系弹窗（QR 码 + 搜索 ActionThinker）
- 初始 JSON-LD: Service + FAQPage 双 Schema

### 方法论实践
这一步对应 FDE 方法论的 **Pilot（试点）** 阶段——先快速上线一个完整可用的版本，再逐步迭代。

### 经验教训
- Jekyll 构建在 GitHub Pages 上失败 → 切换到纯静态 HTML（`.nojekyll`），构建成功
- 经验：在 GitHub Pages 上，纯静态 HTML 比 Jekyll 更可靠、更快速
