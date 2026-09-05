# 纯白留白风 (pure-whitespace)

> 视觉定位：观点 / 商业观察 / 方法论
> 关键词：高级、克制、呼吸感、无装饰
> 适合读者：职场人、管理者、追求质感阅读的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 冷静、笃定、不喧哗 |
| 节奏 | 慢起快落，大留白承载小文字量 |
| 配色 | 纯白 + 三级灰 + 单一靛蓝强调 |
| 字体 | 系统无衬线，标题加字距 |
| 留白 | 全文最大，块间距 32-40px |
| 装饰 | 几乎为零，只用 2px 短横线和留白分区 |

**核心主张**：不用边框、不用卡片、不用色块。层级靠**字号 + 灰度 + 留白**建立。
删掉任何一个组件，文章依然成立——这就是留白风合格的标志。

---

## 二、Color Token

### 2.1 主色调（Ink 三级灰）

| Token | 值 | 用途 |
|-------|------|------|
| `--c-ink` | `#111111` | 主标题、核心句 |
| `--c-body` | `#3F3F44` | 正文主色 |
| `--c-muted` | `#6B6B70` | 副标题、引言、次要说明 |
| `--c-faint` | `#9A9A9E` | 标签、日期、图注 |
| `--c-line` | `#E8E8E6` | 极细分隔线（慎用） |
| `--c-surface` | `#FAFAF9` | 极浅底（仅关键块使用） |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调色（单一）

| Token | 值 | 用途 |
|-------|------|------|
| `--c-accent` | `#1B3A6B` | 唯一强调：章节编号、核心句标记、链接 |
| `--c-accent-tint` | `#F3F5FA` | 极浅靛底：全文最多出现 1-2 次 |

> ⚠️ 反彩虹规则：全篇只允许这一种彩色。需要区分层级时用灰度，不用色相。

---

## 三、组件变体

### 3.1 首屏：标签 + 大标题 + 主张句

一个完整信息单元，不叠加目录、标签墙、第二张卡。

```html
<section style="margin:0 0 36px 0;padding:0;">
  <p style="margin:0 0 14px 0;font-size:12px;color:#9A9A9E;letter-spacing:3px;font-weight:bold;">OBSERVATION · 观察</p>
  <h1 style="margin:0 0 18px 0;font-size:24px;line-height:1.45;color:#111111;font-weight:bold;letter-spacing:0.5px;">为什么我们越来越难专注</h1>
  <p style="margin:0 0 22px 0;font-size:15px;line-height:1.85;color:#6B6B70;">注意力被切碎之后，深度思考变成了一种需要重新练习的能力。</p>
  <section style="width:36px;height:2px;background:#111111;"></section>
</section>
```

### 3.2 正文段落（无缩进、宽行距）

```html
<p style="margin:0 0 26px 0;font-size:15px;line-height:1.9;color:#3F3F44;text-align:left;">专注不是意志力问题，而是环境问题。你不需要更强的自律，你需要一个不会每八分钟打断你一次的工作流。<strong style="color:#111111;">把干扰移出视线，比说服自己忽略它有效得多。</strong></p>
```

> 本风格**不用首行缩进**，靠段间距分段。这是留白风与纸质风最大的区别。

### 3.3 章节标题（编号 + 标题，无分隔线）

```html
<section style="margin:44px 0 20px 0;">
  <p style="margin:0 0 8px 0;font-size:12px;color:#1B3A6B;font-weight:bold;letter-spacing:2px;">01</p>
  <h2 style="margin:0;font-size:19px;line-height:1.5;color:#111111;font-weight:bold;">注意力不是被偷走的，是让出去的</h2>
</section>
```

### 3.4 核心句（大字留白，不用框）

留白风的核心强调方式——把句子放大，而不是加框。

```html
<section style="margin:40px 0;padding:0;">
  <p style="margin:0;font-size:18px;line-height:1.8;color:#111111;font-weight:bold;letter-spacing:0.5px;">你以为你在管理时间，其实你只是在分配注意力。</p>
</section>
```

### 3.5 要点列表（无符号、无边框）

```html
<section style="margin:24px 0 32px 0;">
  <p style="margin:0 0 14px 0;font-size:15px;line-height:1.8;color:#3F3F44;"><span style="display:inline-block;width:14px;color:#1B3A6B;font-weight:bold;">—</span> 关闭所有非即时通讯的推送</p>
  <p style="margin:0 0 14px 0;font-size:15px;line-height:1.8;color:#3F3F44;"><span style="display:inline-block;width:14px;color:#1B3A6B;font-weight:bold;">—</span> 给深度工作留出固定时段，而不是等有空</p>
  <p style="margin:0;font-size:15px;line-height:1.8;color:#3F3F44;"><span style="display:inline-block;width:14px;color:#1B3A6B;font-weight:bold;">—</span> 把手机放在另一个房间，而不是静音</p>
</section>
```

### 3.6 数据块（大数字 + 说明，无卡片）

```html
<section style="margin:36px 0;padding:0;">
  <p style="margin:0 0 6px 0;font-size:34px;line-height:1.2;color:#111111;font-weight:bold;">47<span style="font-size:18px;">秒</span></p>
  <p style="margin:0 0 4px 0;font-size:14px;line-height:1.7;color:#3F3F44;font-weight:bold;">平均单次专注时长</p>
  <p style="margin:0;font-size:13px;line-height:1.7;color:#9A9A9E;">数据来源：加州大学欧文分校 Gloria Mark 团队研究</p>
</section>
```

### 3.7 唯一允许的浅底块（全文最多 1-2 次）

```html
<section style="background:#F3F5FA;padding:22px 24px;margin:32px 0;">
  <p style="margin:0 0 6px 0;font-size:12px;color:#1B3A6B;font-weight:bold;letter-spacing:2px;">结论</p>
  <p style="margin:0;font-size:15px;line-height:1.8;color:#3F3F44;">专注力是稀缺资源，把它投给真正重要的事。</p>
</section>
```

### 3.8 配图 + 图注（去装饰）

```html
<section style="margin:32px 0;">
  <img src="IMAGE_URL" style="width:100%;display:block;" />
  <p style="margin:10px 0 0 0;font-size:12px;line-height:1.6;color:#9A9A9E;">图：开放式办公区的干扰源分布，来源：XXX</p>
</section>
```

### 3.9 文末收束

```html
<section style="margin:56px 0 0 0;padding:24px 0 0 0;border-top:1px solid #E8E8E6;">
  <p style="margin:0 0 12px 0;font-size:14px;line-height:1.8;color:#6B6B70;">如果这篇对你有用，欢迎转发给同样需要安静的朋友。</p>
  <p style="margin:0;font-size:13px;color:#9A9A9E;">作者名 · 2026年9月</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[首屏：标签 + 大标题 + 主张句 + 短横线]
（36px）
[正文 × 2]
（44px）
[章节标题 01]
（20px）
[正文 × 2]
（40px）
[核心句 大字]
（36px）
[正文 × 2]
（32px）
[要点列表]
（36px）
[数据块]
（56px）
[文末收束]
```

### 4.2 用字原则

1. **一段一点**：每段只讲一件事，超过 120 字就拆
2. **核心句放大不加框**：本风格用字号制造强调，不用背景色
3. **粗体不超过 5 处**：粗体是稀缺资源
4. **不留空行**：用 margin 控制间距，不要空 `<p>`
5. **图片不设圆角**：留白风保持直角，圆角会削弱克制感

### 4.3 装饰预算（严格）

| 元素 | 全篇上限 |
|------|---------|
| 短横线（2px） | 1 处（首屏） |
| 浅底块 | 2 处 |
| 彩色文字 | 章节编号 + 链接 |
| 边框卡片 | 0 |
| 分隔线 | 1 处（文末上方） |
| SVG 信息图 | 0-1 个（须线条极简） |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 观点文、商业观察、书评 | 教程步骤（需要卡片承载） |
| 人物专访、方法论 | 多数据对比（需要图表） |
| 品牌调性文章 | 快讯、促销 |

---

## 五、质量门禁

- 首屏必须是一个完整信息单元，不放目录/标签墙
- 深色块数量：0（本风格禁用深色卡）
- 标题/核心句末行不得出现 2-3 字孤行，出现就改写
- 每 2-3 段正文必须有一个视觉停顿（核心句/要点/数据）
- 图片必须有图注，说明它证明了哪句话
