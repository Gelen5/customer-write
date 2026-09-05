# 主题组件库：墨蓝批注·荧光笔记（ink-note）

> 备考经验帖 / 考试干货向主题。设计核心：像一本认真做批注的笔记——白纸底、墨蓝批注笔、荧光笔划重点。
> **刻意克制色块**：全文仅用细左条、下划线、荧光高亮和极浅灰蓝衬底建立层级，没有大面积色块。

## 一、设计变量速查表

| 变量 | 值 | 用途 |
|------|-----|------|
| 主色 | `#2F5A8F` 墨蓝 | 章节编号、批注标记、强调加粗 |
| 浅底 | `#F4F7FB` 纸灰蓝 | 引言卡、提示卡衬底（极浅，仅局部） |
| 强调色 | `#F5C518` 荧光黄 | 荧光笔半高亮、正文关键词下划线 |
| 正文色 | `#3A3F47` | 正文 |
| 深字色 | `#23324A` | 标题 |
| 分割线 | `#D8E2EE` | 细分隔线 |
| 警示色 | `#B4552D` | 坑点/避雷标记（仅细左条+文字色） |
| 字体 | system | 全局系统字体 |

**正文下划线 CSS（权威值）**：`border-bottom:2px solid #F5C518;font-weight:600;color:#23324A;`
**荧光高亮 CSS**：`background-color:#F9DF80;`

## 二、各组件完整 HTML

### 1. 封面标题卡（细线框，无色块）

```html
<section style="margin:0 0 20px 0;padding:22px 18px 18px;border-top:3px solid #2F5A8F;border-bottom:1px solid #D8E2EE;">
  <p style="margin:0 0 8px 0;font-size:12px;letter-spacing:3px;color:#2F5A8F;"><span leaf="">备考笔记 · STUDY NOTES</span></p>
  <section style="margin:0;padding:0;">
    <h3 style="margin:0;font-size:21px;line-height:1.5;color:#23324A;font-weight:700;"><span leaf="">{{文章标题}}</span></h3>
  </section>
  <p style="margin:10px 0 0;font-size:13px;color:#8A94A3;"><span leaf="">{{一句话导读}}</span></p>
</section>
```

### 2. 引言卡（浅底细左条）

```html
<section style="margin:0 0 20px;padding:14px 16px;background-color:#F4F7FB;border-left:3px solid #2F5A8F;border-radius:0 6px 6px 0;">
  <p style="margin:0;font-size:15px;line-height:1.8;color:#23324A;"><span leaf="">{{引言金句，核心词加荧光高亮}}</span></p>
</section>
```

### 3. 章节标题（墨蓝编号 + 荧光短条）

```html
<section style="margin:28px 0 14px;">
  <p style="margin:0 0 4px;font-size:13px;font-weight:700;color:#2F5A8F;letter-spacing:1px;"><span leaf="">0{{N}} / {{英文小标}}</span></p>
  <section style="margin:0;padding:0;">
    <h3 style="margin:0;font-size:18px;line-height:1.5;color:#23324A;font-weight:700;border-bottom:2px solid #F5C518;display:inline-block;padding-bottom:3px;"><span leaf="">{{章节标题}}</span></h3>
  </section>
</section>
```

### 4. 正文段（关键词下划线）

```html
<p style="margin:0 0 14px;font-size:15px;line-height:1.85;color:#3A3F47;text-align:justify;"><span leaf="">{{正文，关键词}}</span><span leaf="" style="border-bottom:2px solid #F5C518;font-weight:600;color:#23324A;">{{关键词}}</span><span leaf="">{{续写正文。}}</span></p>
```

### 5. 荧光笔强调句（段内或独立）

```html
<p style="margin:0 0 14px;font-size:15px;line-height:1.9;color:#3A3F47;text-align:justify;"><span leaf="" style="background-color:#F9DF80;font-weight:600;color:#23324A;">{{核心结论句}}</span></p>
```

### 6. 要点列表（圆点编号，无底色）

```html
<section style="margin:0 0 14px;">
  <section style="margin:0 0 9px;padding:0 0 0 14px;border-left:2px solid #D8E2EE;">
    <p style="margin:0;font-size:15px;line-height:1.8;color:#3A3F47;"><span leaf=""><strong style="color:#2F5A8F;">01</strong>　</span><span leaf="">{{要点标题：}}</span><span leaf="" style="border-bottom:2px solid #F5C518;font-weight:600;color:#23324A;">{{要点关键词}}</span><span leaf="">{{要点说明}}</span></p>
  </section>
</section>
```

### 7. 批注卡（提示/方法说明，浅底）

```html
<section style="margin:16px 0;padding:12px 14px;background-color:#F4F7FB;border-radius:6px;">
  <p style="margin:0 0 4px;font-size:13px;font-weight:700;color:#2F5A8F;"><span leaf="">✎ 批注</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#3A3F47;"><span leaf="">{{批注说明文字}}</span></p>
</section>
```

### 8. 坑点警示卡（细左条砖红，无大色块）

```html
<section style="margin:16px 0;padding:12px 14px;border-left:3px solid #B4552D;">
  <p style="margin:0 0 4px;font-size:13px;font-weight:700;color:#B4552D;"><span leaf="">⚠ 踩坑提醒</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#3A3F47;"><span leaf="">{{坑点描述与修正方法}}</span></p>
</section>
```

### 9. 引用金句（大引号留白式）

```html
<section style="margin:20px 0;padding:0 6px;">
  <p style="margin:0 0 2px;font-size:26px;line-height:1;color:#D8E2EE;font-weight:700;"><span leaf="">“</span></p>
  <p style="margin:0;font-size:15px;line-height:1.85;color:#23324A;font-weight:600;"><span leaf="">{{金句正文}}</span></p>
</section>
```

### 10. 阶段时间轴条（轻量横条，非大色块）

```html
<section style="margin:14px 0;padding:10px 14px;border:1px solid #D8E2EE;border-radius:6px;">
  <p style="margin:0;font-size:14px;line-height:1.8;color:#3A3F47;"><span leaf="" style="font-weight:700;color:#2F5A8F;">{{阶段名}}　</span><span leaf="">{{阶段时间}} · {{阶段一句话任务}}</span></p>
</section>
```

### 11. 数据对比行（模考/成绩进步）

```html
<section style="margin:14px 0;padding:12px 14px;border-top:1px dashed #D8E2EE;border-bottom:1px dashed #D8E2EE;">
  <p style="margin:0;font-size:14px;line-height:1.9;color:#3A3F47;"><span leaf="">{{项目}}：</span><span leaf="" style="color:#8A94A3;">{{起点数据}}</span><span leaf="" style="color:#2F5A8F;font-weight:700;"> → {{终点数据}}</span><span leaf="" style="color:#8A94A3;">（{{备注}}）</span></p>
</section>
```

### 12. 步骤卡（方法拆解）

```html
<section style="margin:12px 0;">
  <p style="margin:0 0 3px;font-size:14px;font-weight:700;color:#23324A;"><span leaf="">Step {{N}}　{{步骤名}}</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#3A3F47;padding:0 0 0 12px;border-left:2px solid #F5C518;"><span leaf="">{{步骤说明}}</span></p>
</section>
```

### 13. 尾部签名区

```html
<section style="margin:26px 0 0;padding:16px 0 4px;border-top:1px solid #D8E2EE;">
  <p style="margin:0 0 6px;font-size:14px;line-height:1.8;color:#3A3F47;"><span leaf="">我是 </span><span leaf="" style="color:#2F5A8F;font-weight:700;">{{作者名}}</span><span leaf="">，{{一句话简介}}。</span></p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#8A94A3;"><span leaf="">如果你觉得今天这篇有收获，欢迎</span><span leaf="" style="color:#23324A;font-weight:600;">点赞、在看、转发</span><span leaf="">三连，我们下篇见。</span></p>
</section>
```

## 三、完整文章模板骨架

```
封面标题卡 → 引言卡 → [章节标题 → (正文段 / 要点列表 / 荧光笔强调句 / 批注卡 / 坑点警示卡 / 步骤卡 / 阶段时间轴条 / 数据对比行)]×N → 引用金句（可选，1 处）→ 尾部签名区
```

## 四、文章类型 → 组件组合配方表

| 文章类型 | 核心组件 | 点缀组件 |
|---------|---------|---------|
| 备考经验帖 | 封面标题卡、引言卡、章节标题、正文段、批注卡、坑点警示卡、尾部签名区 | 数据对比行、引用金句 |
| 考试干货/方法拆解 | 封面标题卡、章节标题、步骤卡、要点列表、荧光笔强调句、尾部签名区 | 批注卡、要点列表 |
| 复盘/时间规划 | 封面标题卡、章节标题、阶段时间轴条、正文段、尾部签名区 | 数据对比行 |
| 学科经验（单科） | 章节标题、正文段、荧光笔强调句、批注卡 | 步骤卡 |

## 五、Markdown → 组件映射规则

| Markdown 元素 | 组件 |
|------|------|
| `# 标题` | 封面标题卡 |
| 开头 `> 引用` | 引言卡（核心词加荧光高亮） |
| `## 标题` | 章节标题（编号 01/02/03…） |
| `### 标题` | 步骤卡标题样式（Step N 或直接粗体小标题） |
| 正文段 | 正文段（每段 1–3 个关键词下划线） |
| `**加粗**` | 主色加粗 `color:#2F5A8F` |
| `==高亮==` / 核心结论 | 荧光高亮 |
| `~~文字~~` | 荧光笔半高亮 |
| `- 项` | 要点列表（01/02 编号 + 细左条） |
| `1. 项` | 步骤卡（Step N） |
| 非开头 `> 引用` | 引用金句 |
| 数据/分数变化句 | 数据对比行 |
| 坑点/避雷内容 | 坑点警示卡 |
| 补充说明/旁注 | 批注卡 |
