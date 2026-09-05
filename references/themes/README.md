# 内置主题引擎契约（原 gzh-design 排版引擎）

> 本文件是 **customer-write 排版节点 [7/8]** 与**内置主题引擎**（`references/themes/`）之间的对接协议。
> 排版时先读本文件，再按它调用主题库。**不要在排版节点自行设计样式。**
> 本 skill 已将原 gzh-design 排版引擎完整内置到 `references/themes/`，无需探测外部目录。

---

## 一、职责划分（一句话）

**视觉样式来自内置主题库，内容处理逻辑来自全链路管道。**

| 层 | 归属 | 来源文件 |
|----|------|---------|
| 配色、字体、圆角、阴影、组件 HTML | **主题引擎** | `references/themes/theme-{id}.md` + `common-components.md` |
| 首屏信息单元、装饰预算、断行纪律 | 管道 | `references/mobile-layout-quality.md` |
| 标题 / 图片 / 引用 的**处理规则** | 管道 | `references/mobile-layout-quality.md`、`components.md` |
| 标题 / 图片 / 引用 的**视觉呈现** | 主题引擎 | 所选主题库的对应组件 |
| 平台兼容红线 | 取交集，冲突从严 | 见第六节 |

---

## 二、主题引擎文件清单（全部内置，缺一即视为引擎损坏）

| 文件 | 作用 |
|------|------|
| `references/themes/theme-index.md` | **主题单一权威来源**，含全部主题 + 下划线 CSS；本 skill 只启用其中 4 套（禁用摸鱼绿 / 留白禅意，见第三节） |
| `references/themes/theme-{标识}.md` | 主题专属组件库 |
| `references/themes/common-components.md` | 通用增量库（代码块 / 图片·GIF / 小标签标题） |
| `references/themes/theme-generator.md` | 自定义主题生成流程 |
| `references/themes/format-normalize.md` | 非 Markdown 输入（docx/pdf/纯文本）归一化规则 |
| `scripts/validate_gzh_html.py` | 合规校验（ERROR 必须清零） |
| `scripts/wrap_preview.py` | 生成带「复制到公众号」按钮的预览页 |
| `scripts/component_lint.py` | 组件库反模式检查（新增主题时用） |

---

## 三、可用主题（4 套，禁用摸鱼绿 / 留白禅意）

> **以下为缓存，以 `references/themes/theme-index.md` 为唯一权威来源。**
> 每次排版前 Read 一次 theme-index.md；若内容与下表不一致，以 theme-index.md 为准并同步更新本表。
> 本 skill **只允许使用下面 4 套**。主题库里另有 摸鱼绿 `moyu-green`、留白禅意 `zen-whitespace` 两套，**已被本 skill 禁用**，不读取、不选用、不向用户展示。

| # | 主题 | 英文标识 | 主色 | 风格特点 | 适用场景 |
|---|------|---------|------|---------|---------|
| 1 | 红白色系 ⭐默认兜底 | `red-white` | `#DC2626` | 经典编辑风，编号章节 + 引言卡 + 签名区，红色克制点睛，有力量感 | 深度分析、观点、力量感话题 |
| 2 | 石墨极简风 | `graphite-minimal` | `#52525B` | 极简克制、留白理性、全灰阶，无彩色 | 设计、科技评论、专业观点、高端品牌 |
| 3 | 摸鱼票据风 | `moyu-ticket` | `#059669` | 票据 / 门票视觉隐喻，星级评分 + 编号 + 硬阴影卡片 | 测评、工具对比、创意评测 |
| 4 | 橄榄手记 | `olive-journal` | `#1e1f23`（配橙 `#ed7b2f`） | 编辑部内刊质感，分节形式多样，信息密度偏高 | 内刊手记、深度评测、案例复盘、系统性说明文档 |

> 已禁用：~~摸鱼绿 `moyu-green`~~、~~留白禅意 `zen-whitespace`~~——不向用户展示、不得选用。

---

## 四、调用契约（排版节点执行顺序）

### 4.0 选主题（自动选择，不向用户提问）

```
1. Read references/themes/theme-index.md
2. 依据文章题材，从第三节【可用主题（4 套）】里自动选定一套：
   - 题材明显契合某套的"适用场景"→ 选契合套
   - 无明显契合 → 默认兜底：红白色系 red-white
3. 用户在请求中已点名主题 → 采用点名主题（点名的若是已禁用主题：摸鱼绿 / 留白禅意，提示已禁用，改用兜底红白色系）
4. 记录主题中文名 + 英文标识，进入 4.1
```

**规则**：排版主题**一律自动选择，不向用户提问**。唯一例外是用户已在请求中点名某套可用主题。

### 4.1 读组件库（两份，缺一不可）

```
Read references/themes/theme-{标识}.md        # 主题专属：引言卡 / 章节标题 / 正文标记 / 签名
Read references/themes/common-components.md   # 通用：代码块 / 图片·GIF / 小标签标题
```

HTML **一律从这两份库里取，不要凭记忆手写**。

### 4.2 装配

```
1. 先读 references/mobile-layout-quality.md，写排版决策卡：
   - 首屏信息单元 / 装饰预算 / 证据型配图表 / 断行风险
2. 查主题库的「文章类型 → 组件组合配方」表，定本篇核心组件组合
3. 按主题库「完整文章模板骨架」装配
4. 元素处理沿用管道规则，视觉一律换成主题库组件：
   标题   → 主题库章节标题组件（编号变体按主题库；断行纪律按 mobile-layout-quality）
   图片   → common-components 2a/2b + 主题库图注组件
           · 必须带图注与证据角色（管道规则）
           · <img> 用 max-width:100%;height:auto;display:block;margin:0 auto
             ——不用 width:100%，避免小图被拉伸
   引用   → 主题库 quote 组件；主题库没有则用 common 3d 金句块并换主题色
   代码   → common 1a/1b，缩进只用全角空格，绝不用 white-space:pre
5. 一篇文章只用所选主题 + 通用库，不跨主题借组件
```

### 4.3 校验（强制）

```bash
python3 scripts/validate_gzh_html.py <产物.html>
```

- **ERROR 必须清零**；半角标点 WARNING 同样修到 0 再交付
- 另跑 `python3 scripts/layout_quality_check.py <产物.html>`，按 mobile-layout-quality.md 修 findings

### 4.4 交付

```bash
python3 scripts/wrap_preview.py <产物.html>   # 产出带「复制到公众号」按钮的预览页
```

产物命名：`{文件名}_排版_{主题中文名}({英文标识}).html`
产物格式：**纯 `<section>…</section>` 片段**，不包 doctype / html / head / body。

---

## 五、冲突裁决

| 冲突 | 裁决 |
|------|------|
| 主题库组件 vs 管道降级组件库同语义 | **用主题库版本**，保持该主题气质一致 |
| 主题库骨架 vs article-template.html | **用主题库骨架** |
| 主题库装饰多 vs mobile-layout-quality「强锚点 ≤5 处」 | 视觉细节从主题库，**数量与节奏受 mobile-layout-quality 约束** |
| 主题库虚线框 vs「不用虚线框」 | **主题库明确定义的虚线组件属该主题风格特征，照用**；主题库没定义的，一律用左竖条/药丸标签 |
| 排版风格 vs 微信平台红线 | 平台红线优先（见下） |

---

## 六、平台红线（两套规范取从严）

**禁止**：`<style>` / `<script>` / `<div>`、`class` / `id` 属性、`position` 任何值、`float`、`@media` / `@keyframes`、`display:grid`、CSS 变量、外部字体、SVG SMIL 动画、伪元素、`calc()`。
**必须**：样式全内联；**所有文字节点用 `<span leaf="">文字</span>` 包裹**（漏包裹会导致粘贴后样式整片丢失，是最高频致命错）；`<img>` 加 `display:block`。

---

## 七、微调规则

用户要求「稍微改一下」时：

1. **只在已选主题基础上做局部调整**，不换主题、不引入其它主题的组件
2. 可微调范围：间距、字号、圆角、某处组件的深浅变体、强调位置
3. **不可微调**：主色色相、主题标志性视觉隐喻（如票据风的票据造型）
   —— 这些变了就等于换主题，需重新走 4.0 重新选主题
4. 微调后重跑 4.3 校验

---

## 八、降级策略

| 情况 | 处理 |
|------|------|
| `references/themes/` 必需文件缺失 | 告知用户主题引擎不可用，回退 SKILL.md 降级路径模式 A/B，并说明样式将不一致 |
| Python 不可用 | 无法跑校验，交付时明确标注「未通过自动校验」，需人工检查 |
| 用户要的风格 4 套可用主题都不覆盖 | 走「自定义主题生成」流程（`references/themes/theme-generator.md`），生成并登记进 theme-index.md 后再回到 4.0 |
| 用户点名被禁用的主题（摸鱼绿 / 留白禅意） | 提示"该主题已禁用"，改用兜底 红白色系 `red-white` 并告知用户 |
| validate 报 ERROR | 回到 4.2 修，ERROR 清零前不得交付 |

> 本 skill 自带的 `references/styles/*.md`（10 套）**仅作为主题引擎不可用时的降级资源**，排版节点不得优先使用。
