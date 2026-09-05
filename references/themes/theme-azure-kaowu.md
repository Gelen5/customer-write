# 公众号排版组件库 —— 考务蓝·严谨考务

> **使用说明**：本组件库为「考务蓝·严谨考务（Azure Kaowu）」主题，面向公考培训机构发布的**考试考务类公告**——考试安排、笔试/面试通知、科目与大纲、分数线、准考证、考务流程（结构化、官方、清楚）。所有组件使用**内联样式**。
>
> **设计风格**：深钴蓝 `#2456D8` 主色 + 天蓝点缀，正式而清晰的"考务通知"感。顶部考务标头（考试名称 + 考务类型）、考试日程用「时间轴 / 流程线」、科目 / 大纲用清爽列表、分数线用数据卡、关键时间用蓝提示条。比「政务蓝（机关公文条款）」更聚焦"考试本身"——它不排招聘单位条款，专排"何时报名 / 考什么 / 怎么考 / 分数线多少"。
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
主色（钴蓝）：      #2456D8（标头 / 流程 / 编号 / 下划线锚点）
主色浅底：          #E8EFFC（浅蓝底标签 / 提示）
主色更浅：          #F4F8FE（信息卡底）
辅蓝（天蓝）：      #3E8EF7（点缀，流程 / 图标，≤3 处）
标题色：            #16233C
正文色：            #2E3A50
辅助文字色：        #7B8799
分割线 / 细线：     #DFE7F5
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
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#2E3A50;line-height:1.85;letter-spacing:0.3px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 组件 2 考务标头（本主题定调封面）

> 钴蓝细线顶 + 考务类型小标签（考务 / 笔试 / 面试 / 调剂）+ 主标题，下方关键时间行（报名 / 考试）。像考试院的一张考务单。

```html
<section style="margin:6px 0 26px;">
  <section style="display:flex;align-items:center;border-bottom:2px solid #2456D8;padding-bottom:14px;">
    <span style="display:inline-block;background-color:#2456D8;color:#fff;font-size:11px;font-weight:700;padding:3px 10px;border-radius:3px;letter-spacing:1px;margin-right:10px;"><span leaf="">{{考务类型}}</span></span>
    <span style="font-size:11px;color:#7B8799;letter-spacing:1px;"><span leaf="">{{发布机构 · 2026}}</span></span>
  </section>
  <p style="font-size:24px;font-weight:900;color:#16233C;margin:18px 0 10px;line-height:1.5;letter-spacing:0.5px;">
    <span leaf="">{{公告主标题}}</span>
  </p>
  <section style="background-color:#F4F8FE;border:1px solid #E8EFFC;border-radius:6px;padding:12px 14px;">
    <p style="font-size:13px;color:#2E3A50;margin:0;line-height:1.8;">
      <span leaf="">报名：</span><strong style="color:#2456D8;"><span leaf="">{{报名起止}}</span></strong>
      <span leaf="">　考试：</span><strong style="color:#2456D8;"><span leaf="">{{考试日期}}</span></strong>
    </p>
  </section>
</section>
```

---

## 组件 3 章节标题（一、二、三…，钴蓝大编号）

> 钴蓝实底序号块 + 深色标题 + 细线。首章 `margin-top:4px`，后续章 `margin-top:40px`。

```html
<section style="margin-top:40px;margin-bottom:18px;">
  <section style="display:flex;align-items:center;border-bottom:1px solid #DFE7F5;padding-bottom:12px;">
    <span style="display:inline-block;background-color:#2456D8;color:#FFFFFF;font-size:16px;font-weight:800;padding:3px 12px;border-radius:4px;margin-right:12px;line-height:1.4;"><span leaf="">{{一}}</span></span>
    <h3 style="font-size:18px;font-weight:800;color:#16233C;margin:0;letter-spacing:0.5px;">
      <span leaf="">{{章节标题}}</span>
    </h3>
  </section>

  <!-- 本章节内容放这里 -->

</section>
```

---

## 组件 4 正文段落

> 每段标 1~3 个关键短语（报名 / 科目 / 时间 / 分数线），蓝下划线。

```html
<p style="margin-bottom:20px;font-size:15px;line-height:1.85;text-align:justify;color:#2E3A50;letter-spacing:0.3px;">
  <span leaf="">{{前半句}}</span>
  <span style="border-bottom:2px solid #B8CCF7;font-weight:600;color:#2456D8;"><span leaf="">{{关键短语}}</span></span>
  <span leaf="">{{后半句}}</span>
</p>
```

---

## 组件 5 强调（5 种）

### 5a. 钴蓝加粗（默认）
```html
<strong style="color:#2456D8;"><span leaf="">钴蓝加粗强调</span></strong>
```

### 5b. 浅蓝底深蓝标签（核心概念 / 科目名）
```html
<span style="background-color:#E8EFFC;color:#1E4EC2;padding:2px 7px;border-radius:3px;font-weight:700;"><span leaf="">《公共基础知识》</span></span>
```

### 5c. 蓝下划线（正文默认标记）
```html
<span style="border-bottom:2px solid #B8CCF7;font-weight:600;color:#2456D8;"><span leaf="">蓝下划线关键词</span></span>
```

### 5d. 行内代码 / 邮箱 / 关键词（灰底等宽）
```html
<span style="background-color:#F1F4F9;color:#16233C;padding:2px 6px;border-radius:3px;font-family:'SF Mono',Consolas,Monaco,monospace;font-size:14px;"><span leaf="">code</span></span>
```

### 5e. 天蓝锚点（流程高亮，全篇 ≤3 处）
```html
<span style="color:#3E8EF7;font-weight:800;"><span leaf="">登录系统打印准考证</span></span>
```

---

## 组件 6 关键时间提醒条（报名 / 打印 / 截止）

```html
<section style="border-left:4px solid #2456D8;padding:14px 0 14px 20px;margin-bottom:22px;background-color:#F4F8FE;">
  <p style="font-size:14px;font-weight:700;color:#2456D8;margin:0;line-height:1.8;">
    <span leaf="">{{节点}}：{{关键时间}}</span>
  </p>
</section>
```

---

## 组件 7 考试日程 / 考务流程时间轴

> 考试最关键的是"时间链"（报名→缴费→准考证→笔试→面试→体检）。用钴蓝圆点 + 细线流程呈现。

```html
<section style="margin-bottom:22px;">
  <section style="display:flex;align-items:flex-start;">
    <section style="display:flex;flex-direction:column;align-items:center;margin-right:16px;flex-shrink:0;">
      <span style="width:12px;height:12px;background-color:#2456D8;border-radius:50%;margin-top:6px;"><span leaf=""><br></span></span>
      <span style="width:2px;flex:1;background-color:#B8CCF7;min-height:38px;"><span leaf=""><br></span></span>
    </section>
    <section style="padding-bottom:16px;flex:1;">
      <p style="font-size:12px;color:#3E8EF7;font-weight:700;margin:0 0 4px;letter-spacing:1px;"><span leaf="">{{时间}}</span></p>
      <p style="font-size:16px;font-weight:800;color:#16233C;margin:0 0 4px;"><span leaf="">{{阶段名}}</span></p>
      <p style="font-size:14px;color:#5B6B82;margin:0;line-height:1.7;"><span leaf="">{{阶段说明}}</span></p>
    </section>
  </section>

  <section style="display:flex;align-items:flex-start;">
    <section style="display:flex;flex-direction:column;align-items:center;margin-right:16px;flex-shrink:0;">
      <span style="width:12px;height:12px;background-color:#2456D8;border-radius:50%;margin-top:6px;"><span leaf=""><br></span></span>
    </section>
    <section style="padding-bottom:4px;flex:1;">
      <p style="font-size:12px;color:#3E8EF7;font-weight:700;margin:0 0 4px;letter-spacing:1px;"><span leaf="">{{时间}}</span></p>
      <p style="font-size:16px;font-weight:800;color:#16233C;margin:0 0 4px;"><span leaf="">{{阶段名}}</span></p>
      <p style="font-size:14px;color:#5B6B82;margin:0;line-height:1.7;"><span leaf="">{{阶段说明}}</span></p>
    </section>
  </section>
</section>
```

---

## 组件 8 报考条件 / 报考资格清单（编号方块）

```html
<section style="margin-bottom:22px;">
  <section style="display:flex;align-items:flex-start;margin-bottom:12px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;background-color:#2456D8;color:#fff;font-size:13px;font-weight:700;border-radius:4px;flex-shrink:0;margin-top:2px;margin-right:12px;"><span leaf="">1</span></span>
    <p style="font-size:15px;color:#2E3A50;margin:0;line-height:1.8;flex:1;"><span leaf="">{{条项内容}}</span></p>
  </section>
  <section style="display:flex;align-items:flex-start;margin-bottom:12px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:24px;height:24px;background-color:#2456D8;color:#fff;font-size:13px;font-weight:700;border-radius:4px;flex-shrink:0;margin-top:2px;margin-right:12px;"><span leaf="">2</span></span>
    <p style="font-size:15px;color:#2E3A50;margin:0;line-height:1.8;flex:1;"><span leaf="">{{条项内容}}</span></p>
  </section>
</section>
```

---

## 组件 9 科目 / 试卷结构（考试内容）

> 笔试科目、题量与占比，用"科目卡"横向 + 内行比例数据，最方便考生扫读。

```html
<section style="display:flex;margin-bottom:20px;">
  <section style="flex:1;background-color:#F4F8FE;border:1px solid #E8EFFC;border-radius:6px;padding:16px 12px;margin-right:8px;text-align:center;">
    <p style="font-size:11px;color:#7B8799;margin:0 0 4px;"><span leaf="">{{模块}}</span></p>
    <p style="font-size:15px;font-weight:800;color:#16233C;margin:0 0 4px;"><span leaf="">{{科目名}}</span></p>
    <p style="font-size:13px;color:#2456D8;font-weight:700;margin:0;"><span leaf="">{{题量 · 分值}}</span></p>
  </section>
  <section style="flex:1;background-color:#F4F8FE;border:1px solid #E8EFFC;border-radius:6px;padding:16px 12px;text-align:center;">
    <p style="font-size:11px;color:#7B8799;margin:0 0 4px;"><span leaf="">{{模块}}</span></p>
    <p style="font-size:15px;font-weight:800;color:#16233C;margin:0 0 4px;"><span leaf="">{{科目名}}</span></p>
    <p style="font-size:13px;color:#2456D8;font-weight:700;margin:0;"><span leaf="">{{题量 · 分值}}</span></p>
  </section>
</section>
```

---

## 组件 10 分数线 / 数据卡

> 进面分数线、合格线、通过比例用蓝底大数字数据卡。

```html
<section style="display:flex;margin-bottom:20px;">
  <section style="flex:1;background-color:#F4F8FE;border:1px solid #E8EFFC;padding:18px 10px;margin-right:8px;text-align:center;">
    <p style="font-size:30px;font-weight:900;color:#2456D8;margin:0 0 4px;line-height:1;"><span leaf="">{{数字}}</span></p>
    <p style="font-size:11px;color:#7B8799;margin:0;"><span leaf="">{{说明}}</span></p>
  </section>
  <section style="flex:1;background-color:#F4F8FE;border:1px solid #E8EFFC;padding:18px 10px;text-align:center;">
    <p style="font-size:30px;font-weight:900;color:#2456D8;margin:0 0 4px;line-height:1;"><span leaf="">{{数字}}</span></p>
    <p style="font-size:11px;color:#7B8799;margin:0;"><span leaf="">{{说明}}</span></p>
  </section>
</section>
```

---

## 组件 11 考试要求 / 纪律提示（携带证件、入场）

```html
<section style="border-left:4px solid #3E8EF7;padding:14px 0 14px 20px;margin-bottom:22px;">
  <p style="font-size:14px;font-weight:700;color:#1E4EC2;margin:0;line-height:1.85;">
    <span leaf="">{{考试要求 / 携带证件 / 纪律提醒}}</span>
  </p>
</section>
```

---

## 组件 12 扫码查成绩 / 看大纲引导

```html
<section style="border:1px solid #E8EFFC;background-color:#F4F8FE;border-radius:8px;padding:16px;margin-bottom:22px;text-align:center;">
  <p style="font-size:15px;font-weight:800;color:#2456D8;margin:0 0 6px;">
    <span leaf="">成绩公布 / 大纲下载提示</span>
  </p>
  <p style="font-size:13px;color:#5B6B82;margin:0;">
    <span leaf="">公众号后台回复 <span style="background-color:#2456D8;color:#fff;padding:2px 8px;border-radius:3px;font-weight:800;"><span leaf="">【{{数字}}】</span></span> 获取考务安排</span>
  </p>
</section>
```

---

## 组件 13 END 收尾

```html
<section style="margin-top:8px;">
  <section style="display:flex;align-items:center;justify-content:center;margin-bottom:24px;">
    <span style="height:1px;width:46px;background-color:#B8CCF7;margin-right:12px;"><span leaf=""><br></span></span>
    <span style="font-size:11px;color:#2456D8;letter-spacing:3px;font-weight:800;"><span leaf="">END · 预祝上岸</span></span>
    <span style="height:1px;width:46px;background-color:#B8CCF7;margin-left:12px;"><span leaf=""><br></span></span>
  </section>
</section>
```

---

## 完整文章模板骨架

```html
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#2E3A50;line-height:1.85;letter-spacing:0.3px;overflow-x:hidden;">

  <!-- 1. 考务标头（组件2，含报名/考试时间，最前） -->
  <!-- 2. 第一章节（组件3）→ 章内：正文4 + 时间提醒6 -->
  <!-- 3. 考试日程/流程时间轴（组件7） -->
  <!-- 4. 报考条件清单（组件8） -->
  <!-- 5. 科目/试卷结构（组件9）、分数线（组件10） -->
  <!-- 6. 考试纪律（组件11） -->
  <!-- 7. 扫码看安排引导（组件12） -->
  <!-- 8. END（组件13） -->

</section>
```

**骨架铁律**：考务标头最前（直给报名与考试时间）；考试时间链用时间轴；正文每段 1~3 处蓝下划线；END 唯一。此主题聚焦"考试安排"，不排单位招聘条款（那是政务蓝公文的场景）。

---

## 视觉层级（3 层递进）

| 层级 | 样式 | 用途 | 频率 |
|------|------|------|------|
| **锚点层** | 钴蓝标头 / 流程 / 编号 + 天蓝 #3E8EF7（≤3） | 标头、流程、打印准考证 | 全文锚点 ≤5 |
| **标记层** | 蓝下划线（默认）/ 浅蓝底标签 / 钴蓝加粗 | 科目、时间、分数线 | 每段 1~3 处 |
| **容器层** | 章节标题、时间轴、科目卡、数据卡、纪律条 | 考务信息 | 按需 |

**克制原则**：
- 钴蓝 `#2456D8` 为唯一主色，天蓝 `#3E8EF7` 仅点缀 ≤3 处
- 底色纯白；浅蓝底 `#F4F8FE`/`#E8EFFC` 用于卡 / 标签 / 提示
- 不用四周虚线框；强调一律蓝下划线 / 左竖条 / 编号方块

---

## 文章类型 → 组件组合配方

| 文章类型 | 核心组件组合 | 点缀组件 |
|---|---|---|
| 笔试/面试通知 | 考务标头2 + 正文4 + 时间轴7 + 纪律11 | 科目9、END13 |
| 考试大纲 / 科目说明 | 考务标头2 + 科目卡9 + 正文4 | 清单8、引导12 |
| 报名 / 缴费公告 | 考务标头2 + 时间提醒6 + 流程7 + 清单8 | 引导12 |
| 分数线 / 进面 / 调剂 | 考务标头2 + 分数线卡10 + 正文4 | 时间轴7、引导12 |
| 考务汇总（多科速递） | 考务标头2 + 多条时间轴7 + 时间提醒6 | 引导12 |

所有类型共用：考务标头 2 + 章节标题 3 + END 13。

---

## Markdown → 考务蓝·严谨考务 映射规则

| Markdown 元素 | 对应组件 | 说明 |
|---|---|---|
| 文首标题 | 组件 2 考务标头 | 考务类型 + 主标题 + 报名/考试时间 |
| `## 章节（一、二…）` | 组件 3 章节标题 | 钴蓝"一/二/三"编号块 |
| `### 子标题` | 钴蓝左竖条小标题 | 章内 |
| 普通段落 | 组件 4 正文 | 每段标 1~3 处蓝下划线 |
| `**加粗**` | 组件 5a 钴蓝加粗 | 默认 |
| `==高亮==` | 组件 5b 浅蓝底标签 | 科目 / 概念 |
| 行内 code / 邮箱 / 关键词 | 组件 5d 灰底等宽 | |
| 报名 / 打印 / 截止时间 | 组件 6 钴蓝左竖时间提醒 | |
| 考试日程（多步） | 组件 7 钴蓝圆点时间轴 | 时间链 |
| 报考资格条件 | 组件 8 钴蓝方块清单 | |
| 科目 / 试卷结构 | 组件 9 科目卡 | 两列 |
| 分数线 / 合格线 | 组件 10 蓝底数据卡 | |
| 考试要求 / 纪律 | 组件 11 天蓝左竖纪律条 | |
| 打印准考证锚点 | 组件 5e 天蓝加粗 | ≤3 |
| 扫码查成绩 / 看大纲 | 组件 12 引导条 | |
| `---` | 章节间距由组件3 margin 承担 | |
| 文末 | 组件 13 END | |
