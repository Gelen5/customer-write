# 主题组件库：琥珀速读·干货卡（amber-skim）

> 考试干货 / 干货清单向主题。设计核心：**结论前置 + 要点拆条**，让读者扫一眼就能吸收信息。
> **刻意克制色块**：不用大色块铺底，仅用琥珀色小结标签、细底线和极浅米色衬底区分层级，视觉安静、扫读速度快。

## 一、设计变量速查表

| 变量 | 值 | 用途 |
|------|-----|------|
| 主色 | `#B45309` 琥珀棕 | 小节标签、强调加粗、结论标记 |
| 浅底 | `#FDF6EC` 暖米 | 结论卡、速记卡衬底（极浅，仅局部） |
| 正文色 | `#40372C` | 正文 |
| 深字色 | `#2E2318` | 标题 |
| 弱字色 | `#A08A6E` | 导读、备注 |
| 分割线 | `#EADCC8` | 细分隔线 |
| 警示色 | `#B03A2E` | 避雷标记（仅文字+细线） |
| 字体 | system | 全局系统字体 |

**正文下划线 CSS（权威值）**：`border-bottom:2px solid #F3D5A3;font-weight:600;color:#2E2318;`

## 二、各组件完整 HTML

### 1. 封面标题卡（标签行 + 标题 + 导读）

```html
<section style="margin:0 0 20px 0;padding:18px 0 16px;border-bottom:2px solid #B45309;">
  <p style="margin:0 0 8px 0;"><span leaf="" style="display:inline-block;font-size:12px;letter-spacing:2px;color:#B45309;border:1px solid #EADCC8;border-radius:3px;padding:2px 8px;">干货速读 · QUICK NOTES</span></p>
  <section style="margin:0;padding:0;">
    <h3 style="margin:0;font-size:21px;line-height:1.5;color:#2E2318;font-weight:700;"><span leaf="">{{文章标题}}</span></h3>
  </section>
  <p style="margin:10px 0 0;font-size:13px;color:#A08A6E;"><span leaf="">{{一句话导读：本文讲什么、适合谁看}}</span></p>
</section>
```

### 2. 引言卡（极简，弱色竖排线）

```html
<section style="margin:0 0 20px;padding:4px 0 4px 14px;border-left:2px solid #EADCC8;">
  <p style="margin:0;font-size:15px;line-height:1.8;color:#40372C;"><span leaf="">{{引言金句}}</span></p>
</section>
```

### 3. 章节标题（琥珀小节标签 + 标题 + 细底线）

```html
<section style="margin:28px 0 14px;">
  <p style="margin:0 0 6px;"><span leaf="" style="display:inline-block;font-size:12px;font-weight:700;color:#FFFFFF;background-color:#B45309;border-radius:3px;padding:2px 8px;letter-spacing:1px;">0{{N}}</span></p>
  <section style="margin:0;padding:0 0 6px;border-bottom:1px solid #EADCC8;">
    <h3 style="margin:0;font-size:18px;line-height:1.5;color:#2E2318;font-weight:700;"><span leaf="">{{章节标题}}</span></h3>
  </section>
</section>
```

> 注：0N 标签是全文唯一的实色小块（约 20×22px），不算大面积色块；若想更素，可去掉 background-color 改为 `color:#B45309;border:1px solid #B45309;`。

### 4. 结论前置段（干货文核心：粗体结论行 + 说明）

```html
<section style="margin:0 0 14px;">
  <p style="margin:0 0 4px;font-size:15px;line-height:1.7;color:#2E2318;font-weight:700;"><span leaf="">{{结论一句话}}</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#40372C;text-align:justify;"><span leaf="">{{展开说明，关键词}}</span><span leaf="" style="border-bottom:2px solid #F3D5A3;font-weight:600;color:#2E2318;">{{关键词}}</span><span leaf="">{{续写}}</span></p>
</section>
```

### 5. 速记清单（可扫读的要点条）

```html
<section style="margin:0 0 14px;">
  <section style="margin:0 0 8px;padding:0;">
    <p style="margin:0;font-size:15px;line-height:1.8;color:#40372C;"><span leaf="" style="color:#B45309;font-weight:700;">▸ </span><span leaf="">{{要点标题：}}</span><span leaf="" style="border-bottom:2px solid #F3D5A3;font-weight:600;color:#2E2318;">{{要点关键词}}</span><span leaf="">{{要点说明}}</span></p>
  </section>
</section>
```

### 6. 速记卡（浅米底，考前可直接截图）

```html
<section style="margin:16px 0;padding:14px 16px;background-color:#FDF6EC;border-radius:6px;">
  <p style="margin:0 0 6px;font-size:13px;font-weight:700;color:#B45309;letter-spacing:2px;"><span leaf="">📌 速记卡</span></p>
  <p style="margin:0;font-size:14px;line-height:1.9;color:#2E2318;"><span leaf="">{{浓缩要点，每行一条，用「·」分隔}}</span></p>
</section>
```

### 7. 数字指标行（提分/正确率等关键数据）

```html
<section style="margin:14px 0;padding:12px 0;border-top:1px solid #EADCC8;border-bottom:1px solid #EADCC8;">
  <p style="margin:0;font-size:14px;line-height:1.9;color:#40372C;"><span leaf="">{{指标名}}　</span><span leaf="" style="font-size:20px;font-weight:700;color:#B45309;">{{数值}}</span><span leaf="" style="color:#A08A6E;">　{{备注说明}}</span></p>
</section>
```

### 8. 对比条（误区 vs 正解）

```html
<section style="margin:14px 0;">
  <section style="margin:0 0 8px;padding:0 0 0 12px;border-left:2px solid #B03A2E;">
    <p style="margin:0;font-size:14px;line-height:1.8;color:#40372C;"><span leaf="" style="font-weight:700;color:#B03A2E;">✕ 误区：</span><span leaf="">{{常见错误做法}}</span></p>
  </section>
  <section style="margin:0;padding:0 0 0 12px;border-left:2px solid #B45309;">
    <p style="margin:0;font-size:14px;line-height:1.8;color:#40372C;"><span leaf="" style="font-weight:700;color:#B45309;">✓ 正解：</span><span leaf="">{{正确做法}}</span></p>
  </section>
</section>
```

### 9. 步骤卡（操作流程）

```html
<section style="margin:12px 0;">
  <p style="margin:0 0 3px;font-size:14px;font-weight:700;color:#2E2318;"><span leaf="" style="color:#B45309;">{{N}}.</span><span leaf=""> {{步骤名}}</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#40372C;"><span leaf="">{{步骤说明}}</span></p>
</section>
```

### 10. 小贴士旁注

```html
<section style="margin:14px 0;padding:10px 14px;border:1px solid #EADCC8;border-radius:6px;">
  <p style="margin:0;font-size:14px;line-height:1.8;color:#40372C;"><span leaf="" style="color:#B45309;font-weight:700;">TIPS　</span><span leaf="">{{提示内容}}</span></p>
</section>
```

### 11. 尾部签名区

```html
<section style="margin:26px 0 0;padding:16px 0 4px;border-top:1px solid #EADCC8;">
  <p style="margin:0 0 6px;font-size:14px;line-height:1.8;color:#40372C;"><span leaf="">我是 </span><span leaf="" style="color:#B45309;font-weight:700;">{{作者名}}</span><span leaf="">，{{一句话简介}}。</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#A08A6E;"><span leaf="">如果你觉得今天这篇有收获，欢迎</span><span leaf="" style="color:#2E2318;font-weight:600;">点赞、在看、转发</span><span leaf="">三连，我们下篇见。</span></p>
</section>
```

## 三、完整文章模板骨架

```
封面标题卡 → 引言卡 → [章节标题 → (结论前置段 / 速记清单 / 对比条 / 步骤卡 / 速记卡 / 数字指标行 / 小贴士旁注)]×N → 尾部签名区
```

## 四、文章类型 → 组件组合配方表

| 文章类型 | 核心组件 | 点缀组件 |
|---------|---------|---------|
| 考试干货/方法清单 | 封面标题卡、章节标题、结论前置段、速记清单、速记卡、尾部签名区 | 小贴士旁注 |
| 学科干货（单科拆解） | 章节标题、结论前置段、步骤卡、对比条 | 数字指标行、速记卡 |
| 避坑指南 | 封面标题卡、章节标题、对比条、速记清单 | 速记卡 |
| 备考经验帖 | 封面标题卡、引言卡、章节标题、结论前置段、数字指标行、尾部签名区 | 速记清单 |

## 五、Markdown → 组件映射规则

| Markdown 元素 | 组件 |
|------|------|
| `# 标题` | 封面标题卡 |
| 开头 `> 引用` | 引言卡 |
| `## 标题` | 章节标题（0N 标签） |
| `### 标题` | 结论前置段的粗体结论行 |
| 段首核心结论 | 结论前置段 |
| `- 项` | 速记清单（▸ 引导） |
| `1. 项` | 步骤卡 |
| `**加粗**` | 主色加粗 `color:#B45309` |
| `==高亮==` | 粗体 + 下划线标记 |
| 数据/分数 | 数字指标行 |
| 误区/正解对照 | 对比条 |
| 考前浓缩要点 | 速记卡 |
| 补充提示 | 小贴士旁注 |
