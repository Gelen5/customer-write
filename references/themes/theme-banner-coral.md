# 公众号排版组件库 —— 珊瑚招贴·火热招生

> **使用说明**：本组件库为「珊瑚招贴·火热招生（Coral Banner）」主题，面向公考培训机构**招生引流类公告**（开班招生、报名启动、线下宣讲、岗位热度提醒、讲座预约等「快来报名」的招贴风公告）。所有组件使用**内联样式**。
>
> **设计风格**：珊瑚橙红 `#E6392F` + 明黄点缀 `#FFB300`，明快热烈的"火热招贴"感——大号促销标签、加粗号召句、抢座 / 名额 / 截止标签、班次卡、扫码报名大按钮。比「榜上红（冲刺）」更活泼引流、比「绛红（高端）」更亲民促销，适合"本机构火热招生中"的日常招生贴。
>
> **公众号平台限制须知**：
> - ❌ 不支持 `<style>`/`<script>`、CSS class/id/`<div>`、`position:fixed/absolute/sticky`、`float`、`@media`/`@keyframes`、`display:grid`、CSS 变量 `var(--x)`
> - ✅ 支持内联 `style`、`display:flex`（有限）、`border-radius`、`box-shadow`、`<section>/<p>/<span>/<strong>/<img>` 等基础标签
>
> **WeChat 兼容铁律**：
> - 装饰性空元素内部放 `<span leaf=""><br></span>` 占位
> - 不在 `<strong>` 上打 font-size/border；同一 `<p>` 只用一种字号；高亮挂外层 `<span>`
> - 禁用 position/absolute；强调用珊瑚下划线 / 标签 / 号召句，**不用四周虚线框**
> - 结构化无内容区域整块删除，不留空 section

---

## 设计变量速查表

```
主色（珊瑚橙红）：  #E6392F（大标题 / 标签 / CTA / 下划线锚点）
主色浅底：          #FDE8E3（浅橙红底标签）
主色更浅：          #FFF4F0（信息卡底）
明黄（促销点睛）：  #FFB300（≤2 处，促销标签 / 特惠价）
标题色：            #261F1F
正文色：            #453B3A
辅助文字色：        #9A8F8D
分割线 / 细线：     #F5E4E0
正文字号：          15px（不可改）
行高：              1.85
字间距：            0.2px
最大宽度：          677px
内容区边距：        0 14px
章节间距：          38px
```

字体栈：`-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif`

---

## 组件 1 全局容器

```html
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#453B3A;line-height:1.85;letter-spacing:0.2px;overflow-x:hidden;">

  <!-- 所有组件放在这里 -->

</section>
```

---

## 组件 2 火热标题（本主题定调封面）

> 顶部斜切促销角标「火热招生」+ 珊瑚大标题 + 下方标签行（地点 / 时间 / 班型）。像一张亮眼招贴。

```html
<section style="margin:6px 0 24px;">
  <section style="display:flex;align-items:center;margin-bottom:12px;">
    <span style="display:inline-block;background-color:#FFB300;color:#3A2A00;font-size:12px;font-weight:800;padding:3px 10px;border-radius:3px 8px 8px 3px;letter-spacing:1px;margin-right:10px;"><span leaf="">火热招生</span></span>
    <span style="display:inline-block;background-color:#FFF4F0;border:1px solid #F5C9C0;color:#E6392F;font-size:12px;font-weight:700;padding:3px 10px;border-radius:20px;"><span leaf="">{{招生城市 · 班型}}</span></span>
  </section>
  <p style="font-size:26px;font-weight:900;color:#E6392F;margin:0 0 12px;line-height:1.4;letter-spacing:1px;">
    <span leaf="">{{招生大标题}}</span>
  </p>
  <p style="font-size:14px;color:#9A8F8D;margin:0;letter-spacing:0.5px;">
    <span leaf="">{{一句招生卖点 / 报名通道已开启}}</span>
  </p>
</section>
```

---

## 组件 3 章节标题（版块标题，珊瑚粗字）

> 版块用珊瑚粗字 + 底部短线，简洁招贴感，不做笨重色块。

```html
<section style="margin-top:38px;margin-bottom:18px;">
  <section style="display:flex;align-items:center;">
    <h3 style="font-size:20px;font-weight:900;color:#261F1F;margin:0;letter-spacing:0.5px;">
      <span leaf="">{{版块标题}}</span>
    </h3>
    <span style="width:8px;height:8px;background-color:#E6392F;border-radius:2px;margin-left:10px;"><span leaf=""><br></span></span>
  </section>
  <span style="display:block;height:3px;background-color:#E6392F;margin-top:8px;border-radius:2px;"><span leaf=""><br></span></span>
</section>
```

---

## 组件 4 正文段落

> 每段标 1~3 个关键短语（班型 / 名额 / 优惠 / 时间），珊瑚下划线。

```html
<p style="margin-bottom:18px;font-size:15px;line-height:1.85;text-align:justify;color:#453B3A;letter-spacing:0.2px;">
  <span leaf="">{{前半句}}</span>
  <span style="border-bottom:2px solid #F5A79B;font-weight:700;color:#D22F27;"><span leaf="">{{关键短语}}</span></span>
  <span leaf="">{{后半句}}</span>
</p>
```

---

## 组件 5 强调（5 种）

### 5a. 珊瑚加粗（默认）
```html
<strong style="color:#E6392F;"><span leaf="">珊瑚加粗强调</span></strong>
```

### 5b. 浅橙底标签（核心概念 / 班型名）
```html
<span style="background-color:#FDE8E3;color:#D22F27;padding:2px 8px;border-radius:3px;font-weight:700;"><span leaf="">全程班</span></span>
```

### 5c. 珊瑚下划线（正文默认标记）
```html
<span style="border-bottom:2px solid #F5A79B;font-weight:700;color:#D22F27;"><span leaf="">珊瑚下划线关键词</span></span>
```

### 5d. 行内代码 / 邮箱 / 关键词（灰底等宽）
```html
<span style="background-color:#F6F2F1;color:#453B3A;padding:2px 6px;border-radius:3px;font-family:'SF Mono',Consolas,Monaco,monospace;font-size:14px;"><span leaf="">code</span></span>
```

### 5e. 促销标签（特惠 / 限时，明黄 ≤2 处）
```html
<span style="background-color:#FFB300;color:#3A2A00;font-weight:900;padding:2px 8px;border-radius:3px;"><span leaf="">限时特惠</span></span>
```

---

## 组件 6 号召 / 提醒条（报名 / 截止）

```html
<section style="border-left:5px solid #E6392F;padding:14px 0 14px 20px;margin-bottom:20px;background-color:#FFF4F0;">
  <p style="font-size:16px;font-weight:800;color:#E6392F;margin:0;line-height:1.7;">
    <span leaf="">{{号召句 / 报名截止提醒}}</span>
  </p>
</section>
```

---

## 组件 7 名额 / 热度数据卡（报名人数、剩余名额）

> 招生贴常见「仅剩 N 席 / 已报名 X 人」。用明黄 + 珊瑚双色大数字。

```html
<section style="display:flex;margin-bottom:20px;">
  <section style="flex:1;background-color:#FFF4F0;border:1px solid #F8D9D1;padding:16px 10px;margin-right:8px;text-align:center;">
    <p style="font-size:28px;font-weight:900;color:#E6392F;margin:0 0 2px;line-height:1;"><span leaf="">{{数字}}</span></p>
    <p style="font-size:11px;color:#9A8F8D;margin:0;"><span leaf="">{{说明}}</span></p>
  </section>
  <section style="flex:1;background-color:#FFF8E6;border:1px solid #F5DEA8;padding:16px 10px;text-align:center;">
    <p style="font-size:28px;font-weight:900;color:#B8860B;margin:0 0 2px;line-height:1;"><span leaf="">{{数字}}</span></p>
    <p style="font-size:11px;color:#9A8F8D;margin:0;"><span leaf="">{{说明}}</span></p>
  </section>
</section>
```

---

## 组件 8 班型卡（招生班次）

> 班型卡两列：班名 + 价格 + 开班时间 + 报名小标签。珊瑚描边。

```html
<section style="display:flex;margin-bottom:20px;">
  <section style="flex:1;border:1px solid #F0C9C0;border-radius:8px;padding:16px 12px;margin-right:8px;background-color:#FFFFFF;">
    <p style="font-size:11px;color:#E6392F;font-weight:800;letter-spacing:1px;margin:0 0 6px;"><span leaf="">{{班型标签}}</span></p>
    <p style="font-size:17px;font-weight:900;color:#261F1F;margin:0 0 8px;"><span leaf="">{{班型名}}</span></p>
    <p style="font-size:13px;color:#9A8F8D;margin:0 0 10px;line-height:1.6;"><span leaf="">{{开班 / 学制}}</span></p>
    <p style="font-size:20px;font-weight:900;color:#E6392F;margin:0;"><span leaf="">{{价格}}</span></p>
  </section>
  <section style="flex:1;border:1px solid #F0C9C0;border-radius:8px;padding:16px 12px;background-color:#FFFFFF;">
    <p style="font-size:11px;color:#E6392F;font-weight:800;letter-spacing:1px;margin:0 0 6px;"><span leaf="">{{班型标签}}</span></p>
    <p style="font-size:17px;font-weight:900;color:#261F1F;margin:0 0 8px;"><span leaf="">{{班型名}}</span></p>
    <p style="font-size:13px;color:#9A8F8D;margin:0 0 10px;line-height:1.6;"><span leaf="">{{开班 / 学制}}</span></p>
    <p style="font-size:20px;font-weight:900;color:#E6392F;margin:0;"><span leaf="">{{价格}}</span></p>
  </section>
</section>
```

---

## 组件 9 报名步骤 / 流程（快速通道）

> 报名 / 咨询流程用横向编号块，招贴感强。

```html
<section style="margin-bottom:20px;">
  <section style="display:flex;align-items:flex-start;margin-bottom:10px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:26px;height:26px;background-color:#E6392F;color:#fff;font-size:14px;font-weight:800;border-radius:50%;flex-shrink:0;margin-right:12px;"><span leaf="">1</span></span>
    <p style="font-size:15px;color:#453B3A;margin:0;line-height:1.8;flex:1;"><span leaf="">{{步骤说明}}</span></p>
  </section>
  <section style="display:flex;align-items:flex-start;margin-bottom:10px;">
    <span style="display:inline-flex;align-items:center;justify-content:center;width:26px;height:26px;background-color:#E6392F;color:#fff;font-size:14px;font-weight:800;border-radius:50%;flex-shrink:0;margin-right:12px;"><span leaf="">2</span></span>
    <p style="font-size:15px;color:#453B3A;margin:0;line-height:1.8;flex:1;"><span leaf="">{{步骤说明}}</span></p>
  </section>
</section>
```

---

## 组件 10 扫码报名大按钮（招生引导，本主题招牌）

> 珊瑚实底大按钮视觉 + 下方扫码 / 关键词引导。招生贴收敛 CTA。

```html
<section style="border:1px solid #F0C9C0;background-color:#FFF4F0;border-radius:10px;padding:18px 16px;margin-bottom:22px;text-align:center;">
  <section style="display:inline-block;background-color:#E6392F;border-radius:22px;padding:10px 30px;margin-bottom:12px;">
    <p style="font-size:17px;color:#FFFFFF;font-weight:900;margin:0;letter-spacing:2px;"><span leaf="">立即报名占座</span></p>
  </section>
  <p style="font-size:13px;color:#9A8F8D;margin:0;line-height:1.7;">
    <span leaf="">长按识别二维码，或后台回复 <span style="background-color:#E6392F;color:#fff;padding:1px 7px;border-radius:3px;font-weight:800;"><span leaf="">【报名】</span></span> 获取报名通道</span>
  </p>
</section>
```

---

## 组件 11 扫码看公告 / 看岗位表（招考引流必备）

```html
<section style="border-top:1px dashed #E8D8D4;border-bottom:1px dashed #E8D8D4;padding:14px 0;margin-bottom:20px;text-align:center;">
  <p style="font-size:15px;font-weight:800;color:#E6392F;margin:0;">
    <span leaf="">后台回复关键词【{{数字}}】查看完整公告与岗位表</span>
  </p>
</section>
```

> 说明：本组件使用上下水平虚线（非四周虚线框），作招贴分隔线用，属主题允许的横向虚线装饰。

---

## 组件 12 END 收尾

```html
<section style="margin-top:8px;">
  <section style="text-align:center;margin-bottom:24px;">
    <span style="font-size:12px;color:#E6392F;letter-spacing:4px;font-weight:900;"><span leaf="">· 快来报名 · 名额有限 ·</span></span>
  </section>
</section>
```

---

## 完整文章模板骨架

```html
<section style="max-width:677px;margin:0 auto;background-color:#FFFFFF;font-family:-apple-system,BlinkMacSystemFont,'PingFang SC','Hiragino Sans GB','Microsoft YaHei',sans-serif;color:#453B3A;line-height:1.85;letter-spacing:0.2px;overflow-x:hidden;">

  <!-- 1. 火热标题（组件2，最前） -->
  <!-- 2. 一句话卖点正文（组件4） -->
  <!-- 3. 名额热度卡（组件7，可选） -->
  <!-- 4. 版块标题（组件3）→ 正文4 + 班型卡8 -->
  <!-- 5. 报名流程（组件9） -->
  <!-- 6. 号召提醒（组件6，截止/开班） -->
  <!-- 7. 扫码报名大按钮（组件10） -->
  <!-- 8. 扫码看公告（组件11，机构公告必备） -->
  <!-- 9. END（组件12） -->

</section>
```

**骨架铁律**：火热标题最前；版块用珊瑚粗字 + 渐变短线；班型卡两列；报名 / 看公告用珊瑚 CTA；正文每段 1~3 处珊瑚下划线；END 唯一。

---

## 视觉层级（3 层递进）

| 层级 | 样式 | 用途 | 频率 |
|------|------|------|------|
| **锚点层** | 珊瑚实底 CTA / 大数字 / 号召句 + 明黄标签（#FFB300 ≤2） | 报名按钮、名额、促销 | 全文锚点 ≤5；明黄 ≤2 |
| **标记层** | 珊瑚下划线（默认）/ 浅橙底标签 / 珊瑚加粗 | 班型、优惠、时间 | 每段 1~3 处 |
| **容器层** | 班型卡、流程编号、热度卡、CTA | 招生信息 | 按需 |

**克制原则**：
- 珊瑚橙红 `#E6392F` 是唯一主色，明黄 `#FFB300` 只用于促销点缀 ≤2 处
- 底色纯白；浅橙底 `#FFF4F0`/`#FDE8E3` 用于卡 / 标签；明黄浅底 `#FFF8E6` 仅热度卡
- 不用四周虚线框（横向虚线分隔的组件11属主题例外装饰）

---

## 文章类型 → 组件组合配方

| 文章类型 | 核心组件组合 | 点缀组件 |
|---|---|---|
| 开班招生 / 班型报名 | 火热标题2 + 班型卡8 + 报名按钮10 | 热度卡7、流程9 |
| 报名启动公告 | 火热标题2 + 正文4 + 流程9 + 号召6 | 报名按钮10 |
| 讲座 / 宣讲预约 | 火热标题2 + 正文4 + 时间信息 + 按钮10 | 号召6 |
| 招生预热 / 名额提醒 | 火热标题2 + 热度卡7 + 号召6 | 按钮10、促销5e |
| 招考公告引流（含看公告） | 火热标题2 + 正文4 + 扫码看公告11 | 号召6、按钮10 |

所有类型共用：火热标题 2 + 版块标题 3 + END 12。

---

## Markdown → 珊瑚招贴·火热招生 映射规则

| Markdown 元素 | 对应组件 | 说明 |
|---|---|---|
| 文首标题 | 组件 2 火热标题 | 促销角标 + 珊瑚大标题 |
| `## 版块标题` | 组件 3 珊瑚粗字版块标题 | 加渐变短线 |
| `### 子标题` | 珊瑚粗字小标题 | 章内 |
| 普通段落 | 组件 4 正文 | 每段 1~3 处珊瑚下划线 |
| `**加粗**` | 组件 5a 珊瑚加粗 | 默认 |
| `==高亮==` | 组件 5b 浅橙底标签 | 班型 / 概念 |
| 行内 code / 邮箱 / 关键词 | 组件 5d 灰底等宽 | |
| 报名 / 截止号召 | 组件 6 号召条 | |
| 名额 / 热度数字 | 组件 7 双色热度卡 | |
| 班型 / 课程价格 | 组件 8 班型卡 | 两列 |
| 报名步骤 | 组件 9 圆形编号流程 | |
| 特惠 / 限时 | 组件 5e 明黄促销标签 | ≤2 |
| 报名 CTA | 组件 10 珊瑚大按钮 | |
| 扫码看公告 / 岗位表 | 组件 11 横向虚线引导 | |
| `---` | 版块间距由组件3 margin 承担 | |
| 文末 | 组件 12 END | |
