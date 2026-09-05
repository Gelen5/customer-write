# 主题组件库：黛青复盘·时间轴（timeline-review）

> 备考经验帖 / 上岸复盘向主题。设计核心：用**阶段时间轴**讲清备考节奏，用**复盘表格感**呈现前后对比，叙事有骨架、读起来有推进感。
> **刻意克制色块**：黛青只出现在节点圆点、细线和编号上，节点之间留白呼吸，无大面积铺底。

## 一、设计变量速查表

| 变量 | 值 | 用途 |
|------|-----|------|
| 主色 | `#2E6E65` 黛青 | 节点圆点、编号、强调加粗、细线 |
| 浅底 | `#F1F6F4` 青灰白 | 引言卡、复盘卡衬底（极浅，仅局部） |
| 正文色 | `#37403D` | 正文 |
| 深字色 | `#1F332F` | 标题 |
| 弱字色 | `#8AA39D` | 时间标注、备注 |
| 分割线 | `#CFE3DE` | 细分隔线、时间轴竖线 |
| 警示色 | `#C0563B` 砖红 | 坑点标记（仅节点点+文字） |
| 字体 | system | 全局系统字体 |

**正文下划线 CSS（权威值）**：`border-bottom:2px solid #A9D3CA;font-weight:600;color:#1F332F;`

## 二、各组件完整 HTML

### 1. 封面标题卡（黛青顶线）

```html
<section style="margin:0 0 20px 0;padding:20px 18px;border-top:3px solid #2E6E65;background-color:#F1F6F4;">
  <p style="margin:0 0 8px 0;font-size:12px;letter-spacing:3px;color:#2E6E65;"><span leaf="">备考复盘 · REVIEW</span></p>
  <section style="margin:0;padding:0;">
    <h3 style="margin:0;font-size:21px;line-height:1.5;color:#1F332F;font-weight:700;"><span leaf="">{{文章标题}}</span></h3>
  </section>
  <p style="margin:10px 0 0;font-size:13px;color:#8AA39D;"><span leaf="">{{一句话导读}}</span></p>
</section>
```

### 2. 引言卡（浅底）

```html
<section style="margin:0 0 22px;padding:14px 16px;background-color:#F1F6F4;border-radius:6px;">
  <p style="margin:0;font-size:15px;line-height:1.8;color:#1F332F;"><span leaf="">{{引言金句，核心词加粗黛青}}</span></p>
</section>
```

### 3. 章节标题（节点编号式）

```html
<section style="margin:28px 0 14px;display:flex;align-items:baseline;">
  <p style="margin:0 10px 0 0;font-size:22px;font-weight:700;color:#2E6E65;line-height:1;"><span leaf="">0{{N}}</span></p>
  <section style="margin:0;flex:1;border-bottom:1px solid #CFE3DE;padding:0 0 8px;">
    <h3 style="margin:0;font-size:18px;line-height:1.4;color:#1F332F;font-weight:700;"><span leaf="">{{章节标题}}</span></h3>
  </section>
</section>
```

### 4. 正文段（关键词下划线）

```html
<p style="margin:0 0 14px;font-size:15px;line-height:1.85;color:#37403D;text-align:justify;"><span leaf="">{{正文}}</span><span leaf="" style="border-bottom:2px solid #A9D3CA;font-weight:600;color:#1F332F;">{{关键词}}</span><span leaf="">{{续写}}</span></p>
```

### 5. 阶段时间轴（核心组件：竖线 + 行内圆点 + 阶段卡）

> 注意：圆点用行内 `inline-block` 小圆实现，**不用 `position:absolute`**（平台红线）。

```html
<section style="margin:16px 0;">
  <section style="margin:0 0 18px;padding:0 0 0 14px;border-left:2px solid #CFE3DE;">
    <p style="margin:0 0 2px;font-size:13px;color:#8AA39D;letter-spacing:1px;"><span leaf="" style="display:inline-block;width:8px;height:8px;border-radius:50%;background-color:#2E6E65;margin-right:6px;"></span><span leaf="">{{阶段时间，如 第 1—5 周}}</span></p>
    <p style="margin:0 0 6px;font-size:15px;font-weight:700;color:#1F332F;"><span leaf="">{{阶段名}}</span></p>
    <p style="margin:0;font-size:14px;line-height:1.8;color:#37403D;"><span leaf="">{{阶段任务与做法，关键词}}</span><span leaf="" style="border-bottom:2px solid #A9D3CA;font-weight:600;color:#1F332F;">{{关键词}}</span><span leaf="">{{续写}}</span></p>
  </section>
</section>
```

### 6. 成绩对比卡（起点 → 终点）

```html
<section style="margin:16px 0;padding:14px 16px;background-color:#F1F6F4;border-radius:6px;">
  <p style="margin:0 0 8px;font-size:13px;font-weight:700;color:#2E6E65;letter-spacing:2px;"><span leaf="">成绩变化</span></p>
  <p style="margin:0 0 4px;font-size:14px;line-height:1.9;color:#37403D;"><span leaf="">{{科目}}：</span><span leaf="" style="color:#8AA39D;">{{起点}}</span><span leaf="" style="color:#2E6E65;font-weight:700;"> → {{终点}}</span></p>
  <p style="margin:0;font-size:14px;line-height:1.9;color:#37403D;"><span leaf="">{{科目}}：</span><span leaf="" style="color:#8AA39D;">{{起点}}</span><span leaf="" style="color:#2E6E65;font-weight:700;"> → {{终点}}</span></p>
</section>
```

### 7. 复盘小结条（阶段末尾"现在回头看"）

```html
<section style="margin:14px 0;padding:0 0 0 12px;border-left:3px solid #2E6E65;">
  <p style="margin:0;font-size:14px;line-height:1.8;color:#37403D;"><span leaf="" style="font-weight:700;color:#2E6E65;">复盘 · </span><span leaf="">{{该阶段现在回头看的一句话总结}}</span></p>
</section>
```

### 8. 坑点节点（时间轴变体，砖红点）

```html
<section style="margin:16px 0;">
  <section style="margin:0;padding:0 0 0 14px;border-left:2px solid #CFE3DE;">
    <p style="margin:0 0 4px;font-size:15px;font-weight:700;color:#C0563B;"><span leaf="" style="display:inline-block;width:8px;height:8px;border-radius:50%;background-color:#C0563B;margin-right:6px;"></span><span leaf="">坑 {{N}}：{{坑点名}}</span></p>
    <p style="margin:0;font-size:14px;line-height:1.8;color:#37403D;"><span leaf="">{{坑点经过与修正方法}}</span></p>
  </section>
</section>
```

### 9. 方法卡（做法拆解，编号细线）

```html
<section style="margin:12px 0;padding:10px 14px;border:1px solid #CFE3DE;border-radius:6px;">
  <p style="margin:0 0 4px;font-size:14px;font-weight:700;color:#1F332F;"><span leaf="" style="color:#2E6E65;">{{N}}　</span><span leaf="">{{方法名}}</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#37403D;"><span leaf="">{{方法说明}}</span></p>
</section>
```

### 10. 引用金句（细线上下夹）

```html
<section style="margin:22px 0;padding:14px 6px;border-top:1px solid #CFE3DE;border-bottom:1px solid #CFE3DE;">
  <p style="margin:0;font-size:15px;line-height:1.85;color:#1F332F;font-weight:600;text-align:center;"><span leaf="">{{金句正文}}</span></p>
</section>
```

### 11. 尾部签名区

```html
<section style="margin:26px 0 0;padding:16px 0 4px;border-top:1px solid #CFE3DE;">
  <p style="margin:0 0 6px;font-size:14px;line-height:1.8;color:#37403D;"><span leaf="">我是 </span><span leaf="" style="color:#2E6E65;font-weight:700;">{{作者名}}</span><span leaf="">，{{一句话简介}}。</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#8AA39D;"><span leaf="">如果你觉得今天这篇有收获，欢迎</span><span leaf="" style="color:#1F332F;font-weight:600;">点赞、在看、转发</span><span leaf="">三连，我们下篇见。</span></p>
</section>
```

## 三、完整文章模板骨架

```
封面标题卡 → 引言卡 → [章节标题 → (正文段 / 阶段时间轴 / 成绩对比卡 / 方法卡 / 复盘小结条 / 坑点节点)]×N → 引用金句（可选，1 处）→ 尾部签名区
```

## 四、文章类型 → 组件组合配方表

| 文章类型 | 核心组件 | 点缀组件 |
|---------|---------|---------|
| 备考经验帖（叙事复盘） | 封面标题卡、引言卡、章节标题、阶段时间轴、复盘小结条、尾部签名区 | 成绩对比卡、引用金句 |
| 上岸全过程复盘 | 封面标题卡、章节标题、成绩对比卡、阶段时间轴、正文段 | 坑点节点 |
| 避坑帖 | 封面标题卡、章节标题、坑点节点、正文段 | 复盘小结条 |
| 各科方法经验 | 章节标题、方法卡、正文段 | 复盘小结条 |

## 五、Markdown → 组件映射规则

| Markdown 元素 | 组件 |
|------|------|
| `# 标题` | 封面标题卡 |
| 开头 `> 引用` | 引言卡 |
| `## 标题` | 章节标题（0N 编号） |
| `### 标题` | 方法卡标题行 / 复盘小结条 |
| 正文段 | 正文段（每段 1–3 个关键词下划线） |
| `**加粗**` | 主色加粗 `color:#2E6E65` |
| `==高亮==` | 粗体 + 下划线标记 |
| `- 项`（按时间/阶段组织） | 阶段时间轴节点 |
| `- 项`（并列方法） | 方法卡 |
| 分数/成绩变化 | 成绩对比卡 |
| 坑点/教训 | 坑点节点（砖红） |
| 阶段总结句 | 复盘小结条 |
| 非开头 `> 引用` | 引用金句 |
