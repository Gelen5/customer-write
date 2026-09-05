# 公众号排版组件库 —— 天蓝学堂·清新教招

> **使用说明**：本组件库为「天蓝学堂·清新教招（Sky Xuetang）」主题，面向公考培训机构发布的**教师 / 事业单位招聘报名公告类**——招聘单位招聘、岗位一览、报考条件、报名方式、岗位表下载（中公 / 华图转发的"某地招聘教师 X 人"、事业单位招聘等偏正式但清爽的报名帖）。所有组件使用**内联样式**。
>
> **设计风格**：亮天蓝 `#1E9EF0` 主色 + 白与浅蓝，清爽明快的"新招"感——顶部天空蓝标头（招聘单位 / 人数）、岗位一览卡、报考条件清单、报名方式分步、岗位表下载提示。比「考务蓝（考试安排）」更亮、更"招人"，比「政务蓝（机关公文）」更现代亲和。适合教师 / 事业单位 / 医护编 / 人才引进等公开招聘报名公告。
>
> **公众号平台限制须知**：
> - ❌ 不支持 `<style>`/`<script>`、CSS class/id/`<div>`、`position:fixed/absolute/sticky`、`float`、`@media`/`@keyframes`、`display:grid`、CSS 变量 `var(--x)`
> - ✅ 支持内联 `style`、`display:flex`（有限）、`border-radius`、`box-shadow`、`<section>/<p>/<span>/<strong>/<img>` 等基础标签
>
> **WeChat 兼容铁律**：
> - 装饰性空元素内部放 `<span leaf=""><br></span>` 占位
> - 不在 `<strong>` 上打 font-size/border；同一 `<p>` 只用一种字号；高亮挂外层 `<span>`
> - 禁用 position/absolute；强调用蓝下划线 / 左竖条 / 药丸标签，**不用四周虚线框**
> - 结构化无内容区域整块删除，不留空 section

---

## 设计变量速查表

```
主色（天蓝）：      #1E9EF0（标头 / 岗位 / 编号 / 下划线锚点）
主色浅底：          #E1F2FE（浅蓝底标签 / 提示）
主色更浅：          #F0F9FF（信息卡底）
标题色：            #152E45
正文色：            #33485E
辅助文字色：        #7A90A5
分割线 / 细线：     #D9ECFB
正文字号：          15px（不可改）
行高：              1.85
字间距：            0.3px
最大宽度：          677px
内容区边距：        0 14px
章节间距：          40px
```

字体栈：`-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif`

---

## 组件 1 全局容器

```html
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#33485E;line-height:1.85;letter-spacing:0.3px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 组件 2 招聘标头（本主题定调封面）

> 天空蓝渐变标头承载"招聘单位 + 招聘人数"徽章 + 主标题，像机构转发的招聘帖封头。明快正式。

```html
<section style="margin:6px 0 24px;">
  <section style="background-color:#1E9EF0;padding:20px 18px;text-align:center;border-radius:8px;">
    <section style="display:flex;justify-content:center;margin-bottom:10px;">
      <span style="display:inline-block;background-color:#FFFFFF;color:#0D86D6;font-size:12px;font-weight:800;padding:3px 12px;border-radius:20px;margin:0 4px;"><span leaf="">{{招聘单位}}</span></span>
      <span style="display:inline-block;background-color:rgba(255,255,255,0.22);color:#FFFFFF;font-size:12px;font-weight:700;padding:3px 12px;border-radius:20px;margin:0 4px;"><span leaf="">招聘 {{人数}} 人</span></span>
    </section>
    <p style="font-size:22px;color:#FFFFFF;font-weight:900;margin:0;line-height:1.5;letter-spacing:1px;">
      <span leaf="">{{公告主标题}}</span>
    </p>
  </section>
  <p style="font-size:13px;color:#7A90A5;text-align:center;margin:12px 0 0;letter-spacing:0.5px;">
    <span leaf="">{{报名截止 · 关键提醒一句}}</span>
  </p>
</section>
```

---

## 组件 3 章节标题（一、二、三…，天蓝大编号）

> 天蓝实底序号块 + 深色标题 + 细线。首章 `margin-top:4px`，后续章 `margin-top:40px`。

```html
<section style="margin-top:40px;margin-bottom:18px;">
  <section style="display:flex;align-items:center;border-bottom:1px solid #D9ECFB;padding-bottom:12px;">
    <span style="display:inline-block;background-color:#1E9EF0;color:#FFFFFF;font-size:16px;font-weight:800;padding:3px 12px;border-radius:4px;margin-right:12px;line-height:1.4;"><span leaf="">{{一}}</span></span>
    <h3 style="font-size:18px;font-weight:800;color:#152E45;margin:0;letter-spacing:0.5px;">
      <span leaf="">{{章节标题}}</span>
    </h3>
  </section>

  <!-- 本章节内容放这里 -->

</section>
```

---

## 组件 4 正文段落

> 每段标 1~3 个关键短语（岗位 / 人数 / 专业 / 截止），天蓝下划线。

```html
<p style="margin-bottom:20px;font-size:15px;line-height:1.85;text-align:justify;color:#33485E;letter-spacing:0.3px;">
  <span leaf="">{{前半句}}</span>
  <span style="border-bottom:2px solid #BFE0F8;font-weight:600;color:#0D86D6;"><span leaf="">{{关键短语}}</span></span>
  <span leaf="">{{后半句}}</span>
</p>
```

---

## 组件 5 强调（5 种）

### 5a. 天蓝加粗（默认）
```html
<strong style="color:#0D86D6;"><span leaf="">天蓝加粗强调</span></strong>
```

### 5b. 浅蓝底深蓝字标签（核心概念 / 专业名）
```html
<span style="background-color:#E1F2FE;color:#0D7AC0;padding:2px 7px;border-radius:3px;font-weight:700;"><span leaf="">幼儿教育 · 专技岗</span></span>
```

### 5c. 蓝下划线（正文默认标记）
```html
<span style="border-bottom:2px solid #BFE0F8;font-weight:600;color:#0D86D6;"><span leaf="">蓝下划线关键词</span></span>
```

### 5d. 行内代码 / 邮箱 / 关键词（灰底等宽）
```html
<span style="background-color:#F0F4F8;color:#152E45;padding:2px 6px;border-radius:3px;font-family:'SF Mono',Consolas,Monaco,monospace;font-size:14px;"><span leaf="">code</span></span>
```

### 5e. 名额锚点（招录人数，全篇 ≤3 处）
```html
<span style="color:#1E9EF0;font-weight:900;"><span leaf="">招录 {{N}} 人</span></span>
```

---

## 组件 6 关键时间提醒条（报名 / 截止）

```html
<section style="border-left:4px solid #1E9EF0;padding:14px 0 14px 20px;margin-bottom:22px;background-color:#F0F9FF;">
  <p style="font-size:14px;font-weight:700;color:#0D7AC0;margin:0;line-height:1.8;">
    <span leaf="">{{节点}}：{{报名起止 / 截止时间}}</span>
  </p>
</section>
```

---

## 组件 7 岗位一览卡（招聘岗位 / 人数 / 专业 / 条件）

> 招聘公告核心——岗位信息。用岗位卡，每卡一行：岗位名 + 人数 + 专业 + 其它条件。多岗位用多卡叠排。

```html
<section style="margin-bottom:22px;">
  <section style="background-color:#F0F9FF;border:1px solid #D9ECFB;border-radius:8px;padding:16px 14px;margin-bottom:10px;">
    <section style="display:flex;align-items:center;justify-content:space-between;margin-bottom:8px;">
      <p style="font-size:16px;font-weight:800;color:#152E45;margin:0;"><span leaf="">{{岗位名称}}</span></p>
      <span style="background-color:#1E9EF0;color:#fff;font-size:12px;font-weight:700;padding:2px 10px;border-radius:20px;"><span leaf="">招 {{N}} 人</span></span>
    </section>
    <p style="font-size:13px;color:#5B7085;margin:0;line-height:1.8;">
      <span leaf="">专业：</span><strong style="color:#0D7AC0;"><span leaf="">{{专业要求}}</span></strong>
      <span leaf="">　学历：</span><span style="border-bottom:2px solid #BFE0F8;font-weight:600;color:#0D86D6;"><span leaf="">{{学历要求}}</span></span>
    </p>
  </section>

  <section style="background-color:#F0F9FF;border:1px solid #D9ECFB;border-radius:8px;padding:16px 14px;">
    <section style="display:flex;align-items:center;justify-content:space-between;margin-bottom:8px;">
      <p style="font-size:16px;font-weight:800;color:#152E45;margin:0;"><span leaf="">{{岗位名称}}</span></p>
      <span style="background-color:#1E9EF0;color:#fff;font-size:12px;font-weight:700;padding:2px 10px;border-radius:20px;"><span leaf="">招 {{N}} 人</span></span>
    </section>
    <p style="font-size:13px;color:#5B7085;margin:0;line-height:1.8;">
      <span leaf="">专业：</span><strong style="color:#0D7AC0;"><span leaf="">{{专业要求}}</span></strong>
      <span leaf="">　学历：</span><span style="border-bottom:2px solid #BFE0F8;font-weight:600;color:#0D86D6;"><span leaf="">{{学历要求}}</span></span>
    </p>
  </section>
</section>
```

---

## 组件 8 报考条件清单（编号方块）

```html
<section style="margin-bottom:22px;">
  <section style="display:flex;align-items:flex-start;margin-bottom:12px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;background-color:#1E9EF0;color:#fff;font-size:13px;font-weight:700;border-radius:4px;flex-shrink:0;margin-top:2px;margin-right:12px;"><span leaf="">1</span></span>
    <p style="font-size:15px;color:#33485E;margin:0;line-height:1.8;flex:1;"><span leaf="">{{条件}}</span></p>
  </section>
  <section style="display:flex;align-items:flex-start;margin-bottom:12px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;background-color:#1E9EF0;color:#fff;font-size:13px;font-weight:700;border-radius:4px;flex-shrink:0;margin-top:2px;margin-right:12px;"><span leaf="">2</span></span>
    <p style="font-size:15px;color:#33485E;margin:0;line-height:1.8;flex:1;"><span leaf="">{{条件}}</span></p>
  </section>
</section>
```

---

## 组件 9 报名方式分步（在线 / 邮箱 / 现场）

```html
<section style="margin-bottom:22px;">
  <section style="display:flex;align-items:flex-start;margin-bottom:14px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:26px;height:26px;background-color:#1E9EF0;color:#fff;font-size:14px;font-weight:800;border-radius:50%;flex-shrink:0;margin-right:12px;"><span leaf="">1</span></span>
    <section style="flex:1;">
      <p style="font-size:15px;font-weight:700;color:#152E45;margin:0 0 4px;"><span leaf="">{{步骤名}}</span></p>
      <p style="font-size:14px;color:#5B7085;margin:0;line-height:1.8;"><span leaf="">{{说明，含网址/邮箱用 5d 灰底等宽标出}}</span></p>
    </section>
  </section>
  <section style="display:flex;align-items:flex-start;margin-bottom:14px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:26px;height:26px;background-color:#1E9EF0;color:#fff;font-size:14px;font-weight:800;border-radius:50%;flex-shrink:0;margin-right:12px;"><span leaf="">2</span></span>
    <section style="flex:1;">
      <p style="font-size:15px;font-weight:700;color:#152E45;margin:0 0 4px;"><span leaf="">{{步骤名}}</span></p>
      <p style="font-size:14px;color:#5B7085;margin:0;line-height:1.8;"><span leaf="">{{说明}}</span></p>
    </section>
  </section>
</section>
```

---

## 组件 10 招聘流程 / 时间表

```html
<section style="display:flex;margin-bottom:22px;">
  <section style="flex:1;background-color:#F0F9FF;border:1px solid #D9ECFB;border-radius:8px;padding:14px 10px;margin-right:6px;text-align:center;">
    <p style="font-size:11px;color:#7A90A5;margin:0 0 4px;"><span leaf="">{{环节}}</span></p>
    <p style="font-size:14px;font-weight:800;color:#152E45;margin:0;"><span leaf="">{{时间}}</span></p>
  </section>
  <section style="flex:1;background-color:#F0F9FF;border:1px solid #D9ECFB;border-radius:8px;padding:14px 10px;margin-right:6px;text-align:center;">
    <p style="font-size:11px;color:#7A90A5;margin:0 0 4px;"><span leaf="">{{环节}}</span></p>
    <p style="font-size:14px;font-weight:800;color:#152E45;margin:0;"><span leaf="">{{时间}}</span></p>
  </section>
  <section style="flex:1;background-color:#F0F9FF;border:1px solid #D9ECFB;border-radius:8px;padding:14px 10px;text-align:center;">
    <p style="font-size:11px;color:#7A90A5;margin:0 0 4px;"><span leaf="">{{环节}}</span></p>
    <p style="font-size:14px;font-weight:800;color:#152E45;margin:0;"><span leaf="">{{时间}}</span></p>
  </section>
</section>
```

---

## 组件 11 岗位表 / 附件下载提示

> 招聘公告末尾常见"见附件岗位表"。用浅蓝引导条突出下载 / 查看入口。

```html
<section style="border:1px solid #D9ECFB;background-color:#F0F9FF;border-radius:8px;padding:16px;margin-bottom:22px;text-align:center;">
  <p style="font-size:15px;font-weight:800;color:#0D7AC0;margin:0 0 6px;">
    <span leaf="">{{岗位表 / 报名表下载入口}}</span>
  </p>
  <p style="font-size:13px;color:#7A90A5;margin:0;">
    <span leaf="">后台回复 <span style="background-color:#1E9EF0;color:#fff;padding:2px 8px;border-radius:3px;font-weight:800;"><span leaf="">【{{数字}}】</span></span> 获取岗位一览表附件</span>
  </p>
</section>
```

---

## 组件 12 END 收尾

```html
<section style="margin-top:8px;">
  <section style="display:flex;align-items:center;justify-content:center;margin-bottom:24px;">
    <span style="height:1px;width:46px;background-color:#BFE0F8;margin-right:12px;"><span leaf=""><br></span></span>
    <span style="font-size:11px;color:#1E9EF0;letter-spacing:3px;font-weight:800;"><span leaf="">END · 编制上岸</span></span>
    <span style="height:1px;width:46px;background-color:#BFE0F8;margin-left:12px;"><span leaf=""><br></span></span>
  </section>
</section>
```

---

## 完整文章模板骨架

```html
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#33485E;line-height:1.85;letter-spacing:0.3px;overflow-x:hidden;">

  <!-- 1. 招聘标头（组件2，含单位/人数/报名截止，最前） -->
  <!-- 2. 前言一段（组件4，招聘概况） -->
  <!-- 3. 第一章节（组件3）→ 章内：正文4 + 岗位卡7 -->
  <!-- 4. 招聘岗位一览（组件7，岗位卡叠排） -->
  <!-- 5. 报考条件（组件8 清单） -->
  <!-- 6. 报名方式（组件9 分步）、招聘流程时间表（组件10） -->
  <!-- 7. 时间提醒（组件6，截止） -->
  <!-- 8. 岗位表下载引导（组件11） -->
  <!-- 9. END（组件12） -->

</section>
```

**骨架铁律**：招聘标头最前（单位 + 人数 + 截止）；岗位卡 / 报名分步是本主题骨架核心；正文每段 1~3 处蓝下划线；END 唯一。

---

## 视觉层级（3 层递进）

| 层级 | 样式 | 用途 | 频率 |
|------|------|------|------|
| **锚点层** | 天蓝标头 / 岗位卡人数徽章 + 人数锚点 | 标题、岗位、招录人数 | 全文锚点 ≤5 |
| **标记层** | 蓝下划线（默认）/ 浅蓝底标签 / 天蓝加粗 | 专业、学历、截止、岗位 | 每段 1~3 处 |
| **容器层** | 岗位卡、清单、报名分步、流程时间表、下载引导 | 招聘信息 | 按需 |

**克制原则**：
- 天蓝 `#1E9EF0` 为唯一主色，标头用浅渐变
- 底色纯白；浅蓝底 `#F0F9FF`/`#E1F2FE` 用于卡 / 标签 / 引导
- 不用四周虚线框；强调一律蓝下划线 / 左竖条 / 编号

---

## 文章类型 → 组件组合配方

| 文章类型 | 核心组件组合 | 点缀组件 |
|---|---|---|
| 教师/事业单位招聘报名 | 招聘标头2 + 岗位卡7 + 报名分步9 | 条件8、时间表10、引导11 |
| 招聘公告转发（单位+人数） | 招聘标头2 + 正文4 + 岗位卡7 | 条件8、时间表10 |
| 医疗/医护编招聘 | 招聘标头2 + 岗位卡7 + 条件8 | 时间表10、引导11 |
| 人才引进 / 高层次招聘 | 招聘标头2 + 正文4 + 条件8 + 待遇 | 岗位卡7、引导11 |
| 招聘流程 / 资格复审通知 | 招聘标头2 + 时间表10 + 条件8 | 报名分步9、引导11 |

所有类型共用：招聘标头 2 + 章节标题 3 + END 12。

---

## Markdown → 天蓝学堂·清新教招 映射规则

| Markdown 元素 | 对应组件 | 说明 |
|---|---|---|
| 文首标题 | 组件 2 招聘标头 | 单位徽章 + 人数 + 主标题 |
| `## 章节（一、二…）` | 组件 3 章节标题 | 天蓝"一/二/三"编号块 |
| `### 子标题` | 天蓝左竖条小标题 | 章内 |
| 普通段落 | 组件 4 正文 | 每段 1~3 处蓝下划线 |
| `**加粗**` | 组件 5a 天蓝加粗 | 默认 |
| `==高亮==` | 组件 5b 浅蓝底标签 | 专业 / 概念 |
| 行内 code / 网址 / 邮箱 / 关键词 | 组件 5d 灰底等宽 | |
| 报名 / 截止时间 | 组件 6 天蓝左竖时间提醒 | |
| 招聘岗位（多行） | 组件 7 岗位一览卡 | 岗位卡叠排 |
| 报考资格条件 | 组件 8 天蓝方块清单 | |
| 报名方式（多步） | 组件 9 圆形编号分步 | |
| 招聘流程时间 | 组件 10 三栏时间表 | |
| 招录人数锚点 | 组件 5e 天蓝加粗 | ≤3 |
| 岗位表 / 附件下载 | 组件 11 下载引导条 | |
| `---` | 章节间距由组件3 margin 承担 | |
| 文末 | 组件 12 END | |
