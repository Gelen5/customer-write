# 暖纸阅读风 (warm-paper)

> 视觉定位：深度长文 / 书评 / 人物 / 思想类
> 关键词：沉静、耐读、纸张感、慢阅读
> 适合读者：愿意花 10 分钟读完一篇长文的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 温和、笃定、有学识感 |
| 节奏 | 缓慢均匀，一段一呼吸 |
| 配色 | 米白 + 墨褐 + 铜棕强调 |
| 字体 | 衬线优先（Songti / Georgia 回退） |
| 留白 | 大，段间距 24-28px |
| 装饰 | 极简：细线、居中圆点、小字标注 |

**与 minimal-elegant 的区别**：minimal-elegant 偏文艺与情绪（金、诗意 caption）；
warm-paper 偏**内容与论证**——更克制、更学术、装饰更少，让长文读三小时也不累。

---

## 二、Color Token

### 2.1 主色调

| Token | 值 | 用途 |
|-------|------|------|
| `--c-ink` | `#2A2520` | 标题、强调 |
| `--c-body` | `#4A423A` | 正文主色，暖褐 |
| `--c-muted` | `#7A7065` | 引言、次要说明 |
| `--c-faint` | `#A79C8E` | 日期、图注、页码 |
| `--c-line` | `#E6DFD3` | 细线、分隔 |
| `--c-paper` | `#FCFAF6` | 纸张底（块背景） |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调色

| Token | 值 | 用途 |
|-------|------|------|
| `--c-accent` | `#8C6A3F` | 唯一强调：章节序号、重点标记 |
| `--c-accent-tint` | `#FAF6EF` | 铜棕浅底：注释块 |

---

## 三、组件变体

### 3.1 首屏：刊头 + 衬线标题 + 引言

```html
<section style="margin:0 0 34px 0;text-align:center;">
  <p style="margin:0 0 18px 0;font-size:12px;color:#A79C8E;letter-spacing:4px;">长 文</p>
  <h1 style="margin:0 0 16px 0;font-size:23px;line-height:1.55;color:#2A2520;font-weight:bold;font-family:'Songti SC','STSong','Georgia',serif;letter-spacing:1px;">论专注的消失</h1>
  <section style="width:32px;height:1px;background:#8C6A3F;margin:0 auto 18px auto;"></section>
  <p style="margin:0;font-size:14px;line-height:1.85;color:#7A7065;">我们并不是失去了专注的能力，而是失去了允许自己不响应的权利。</p>
</section>
```

### 3.2 正文段落（宽行距、两端对齐）

```html
<p style="margin:0 0 26px 0;font-size:15px;line-height:2.0;color:#4A423A;text-align:justify;letter-spacing:0.3px;font-family:'Songti SC','STSong','Georgia',serif;">有一个细节值得留意：在智能手机普及之前，"回复慢"并不构成冒犯。一封信寄出，对方三天后回，是常态。而现在，一条消息发出十分钟没有回音，我们就会开始揣测。<strong style="color:#2A2520;">变化的不是我们的耐心，是响应被默认成了义务。</strong></p>
```

### 3.3 章节标题（居中序号 + 衬线标题）

```html
<section style="margin:44px 0 22px 0;text-align:center;">
  <p style="margin:0 0 8px 0;font-size:12px;color:#8C6A3F;letter-spacing:3px;">壹</p>
  <h2 style="margin:0;font-size:18px;line-height:1.6;color:#2A2520;font-weight:bold;font-family:'Songti SC','STSong','Georgia',serif;letter-spacing:1px;">响应如何变成义务</h2>
</section>
```

> 章节序号用中文数字（壹 贰 叁）或罗马数字（I II III），与衬线体气质一致。

### 3.4 分隔（居中圆点）

```html
<section style="margin:32px 0;text-align:center;">
  <p style="margin:0;font-size:12px;color:#A79C8E;letter-spacing:6px;">· · ·</p>
</section>
```

### 3.5 引用块（大字衬线）

```html
<section style="margin:34px 0;padding:0 8px;text-align:center;">
  <p style="margin:0 0 10px 0;font-size:17px;line-height:1.9;color:#2A2520;font-weight:bold;font-family:'Songti SC','STSong','Georgia',serif;letter-spacing:1px;">我们塑造了工具，<br/>此后工具塑造了我们。</p>
  <p style="margin:0;font-size:13px;color:#A79C8E;">—— 麦克卢汉（常被归于其名下）</p>
</section>
```

### 3.6 注释 / 补注块

```html
<section style="margin:26px 0;padding:18px 20px;background:#FAF6EF;border-left:2px solid #8C6A3F;">
  <p style="margin:0 0 6px 0;font-size:11px;color:#8C6A3F;letter-spacing:2px;font-weight:bold;">补注</p>
  <p style="margin:0;font-size:14px;line-height:1.85;color:#4A423A;">此处的"响应义务"指一种社会期待，而非任何明文规定。它之所以有效，恰恰因为它从未被写下来。</p>
</section>
```

### 3.7 要点（无符号，缩进对齐）

```html
<section style="margin:24px 0 30px 0;padding-left:16px;border-left:1px solid #E6DFD3;">
  <p style="margin:0 0 12px 0;font-size:15px;line-height:1.85;color:#4A423A;">其一，响应从选择变成了默认。</p>
  <p style="margin:0 0 12px 0;font-size:15px;line-height:1.85;color:#4A423A;">其二，沉默开始需要解释。</p>
  <p style="margin:0;font-size:15px;line-height:1.85;color:#4A423A;">其三，于是我们不再拥有完整的时间块。</p>
</section>
```

### 3.8 配图 + 图注（居中、去圆角）

```html
<section style="margin:30px 0;text-align:center;">
  <img src="IMAGE_URL" style="width:100%;display:block;" />
  <p style="margin:12px 0 0 0;font-size:12px;line-height:1.7;color:#A79C8E;letter-spacing:0.5px;">图：1990-2026 年"平均响应时长"的社会期待变化（示意）</p>
</section>
```

### 3.9 文末：署名 + 落款

```html
<section style="margin:52px 0 0 0;padding:26px 0 0 0;border-top:1px solid #E6DFD3;text-align:center;">
  <p style="margin:0 0 16px 0;font-size:15px;line-height:1.9;color:#4A423A;font-family:'Songti SC','STSong','Georgia',serif;">专注的敌人从来不是分心，<br/>而是"必须立刻回应"这件事本身。</p>
  <section style="width:24px;height:1px;background:#8C6A3F;margin:0 auto 16px auto;"></section>
  <p style="margin:0 0 4px 0;font-size:13px;color:#2A2520;font-weight:bold;">作者名</p>
  <p style="margin:0;font-size:12px;color:#A79C8E;">2026 年 9 月 · 于某个安静的下午</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[首屏：刊头 + 衬线标题 + 细线 + 引言]
（34px）
[正文 × 3]
（44px）
[章节 壹]
（22px）
[正文 × 3]
（32px）
[分隔圆点]
（34px）
[引用块]
（26px）
[补注块]
（52px）
[文末署名]
```

### 4.2 用字原则

1. **段长 100-180 字**：比一般风格略长，衬线适合连续阅读
2. **慎用粗体**：全篇不超过 3 处，多了会破坏纸感
3. **不堆叠组件**：两个组件之间至少隔一段正文
4. **引文必标出处**：不确定的出处写"（常被归于…）"，不编造
5. **不用 emoji**：本风格用标点和留白表达情绪

### 4.3 装饰预算

| 元素 | 全篇上限 |
|------|---------|
| 1px 细线 | 3 处（首屏、文末、要点左线） |
| 分隔圆点 | 2 处 |
| 浅底块 | 2 处 |
| 引用块 | 2 处 |
| 深色块 | 0 |
| SVG 信息图 | 0（与纸感冲突，用文字与表格替代） |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 深度长文、书评、思想类 | 快讯、教程、清单 |
| 人物特写、文化评论 | 强转化营销文 |
| 2000 字以上的内容 | 800 字以内的短文 |

---

## 五、质量门禁

- 首屏居中、信息单一，不放目录与标签墙
- 正文两端对齐 + 行高 2.0，段间距 24-28px
- 章节序号用中文/罗马数字，与衬线体一致
- 引文必须有出处，存疑须标注
- 全篇禁用 emoji 与深色块
