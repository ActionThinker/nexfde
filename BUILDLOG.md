# NEXFDE Build Log

> 每一次构建决策，都是 FDE 方法论的实际应用记录。

---

## 2026-07-03 — VIS 品牌重塑 v2.0: 深茶绿 + 铜色系统

**版本**: v2.0.0
**提交**: (待推送)

### 决策背景
v1.x 的深蓝 `#102A43` + 科技蓝 `#2F6FEB` 配色在市场上缺乏辨识度（"太普通"），且冷色调无法传达 FDE 服务的核心差异——**长期陪伴感**。

经过系统评估，选择 **深茶绿 `#1E3D32` + 铜色 `#C8853E`** 作为新 VIS 体系：
- 深茶绿：稳重、扎根、有阅历——像一棵陪企业长大的树
- 铜色：温暖、人性、信任感——不是卖工具，是做判断的人

### 具体变更

**VIS 系统重写:**
- 主色: `#102A43` → `#1E3D32` (深茶绿)
- 强调色: `#2F6FEB` → `#C8853E` (铜色)
- 背景: `#FFFFFF` → `#F5F2ED` (暖白，沉浸阅读)
- 分区交替: 奇偶区块用暖白 vs 浅灰绿 `#EDEAE4` 交替
- 线框: 冷灰 → `#D4CFC6` (暖灰线框)
- 辅助文字: `#5B6B7A` → `#6B7A73` (灰绿，不冷)
- 全站无蓝色系残留

**Logo 重塑:**
- NEXFDE → NEX(标准字重 深茶绿) + **FDE**(加粗 铜色)
- 副标 `FDE-style AI Deployment` 改为铜色
- 页脚 Logo 同样处理

**新增区块: 业务路线图**
- Phase 1 (铜色高亮): 个人 FDE 交付 — 进行中
- Phase 2 (灰绿): 标准化 SOP + 专家招募 — 筹备中
- Phase 3 (灰绿): FDE 协同交付网络 — 规划中
- 底部入口: "你是有 AI 能力的行业专家？了解加入 NEXFDE 交付网络 →"

**沉浸阅读设计:**
- 暖白背景取代纯白，长时间阅读不刺眼
- 区块交替背景色，形成视觉呼吸感
- 宽间距大留白，节奏明确
- 铜色仅用于 CTA / Logo / 关键词点缀，不全屏铺

### 方法论实践
这次变更本身遵循 FDE 三步方法：
1. **判断**: 分析当前配色问题 → 评估多组方案 → 选择深茶绿+铜色
2. **试点**: 完整重写 CSS 变量，验证所有区块在新配色下的一致性
3. **上线**: 一次性部署，观察用户反馈

### 为什么这样做
- SME 老板需要的不是"酷炫的科技公司"，而是"值得长期信任的伙伴"
- 蓝色在 AI/科技赛道同质化严重，深茶绿+铜色几乎无人使用
- 业务路线图区块为未来双边平台（获客+交付）预留入口
- 沉浸阅读设计降低认知负担，延长页面停留时间

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
