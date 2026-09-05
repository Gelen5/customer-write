# 瑞士网格风 (swiss-grid)

> 视觉定位：结构化知识 / 教程 / 清单 / 拆解分析
> 关键词：秩序、清晰、可扫读、信息密度
> 适合读者：想要「看得懂、记得住、能照做」的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 理性、精确、不抒情 |
| 节奏 | 均匀，模块等距，节奏靠网格而非留白 |
| 配色 | 纯白 + 五级灰 + 克莱因蓝强调 |
| 字体 | 无衬线，小字号说明文字承担信息密度 |
| 留白 | 中等，靠细线分栏而非大空白 |
| 装饰 | 细横线分区、等宽编号、表格式对齐 |

**核心主张**：内容清晰 = 结构可见。
读者在任何位置都应该知道「我现在在第几部分、这部分讲什么、要点有几条」。
一切装饰都让位于**结构的可读性**。

---

## 二、Color Token

### 2.1 主色调（严格五级灰）

| Token | 值 | 用途 |
|-------|------|------|
| `--c-black` | `#000000` | 主标题、编号方块 |
| `--c-gray-800` | `#2B2B2B` | 小节标题 |
| `--c-gray-600` | `#5A5A5A` | 正文主色 |
| `--c-gray-400` | `#8C8C8C` | 说明文字、图注 |
| `--c-gray-200` | `#D8D8D8` | 细线、边框 |
| `--c-gray-100` | `#F2F2F2` | 表头底、编号底 |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调色

| Token | 值 | 用途 |
|-------|------|------|
| `--c-accent` | `#002FA7` | 唯一强调：编号、关键数据、链接 |
| `--c-accent-tint` | `#EDF1FC` | 克莱因蓝浅底：要点块 |

> 克莱因蓝饱和度高，只用在**小块面积**上（编号、数字、细线），不铺底。

---

## 三、组件变体

### 3.1 首屏：网格化标题区

标题区用一条顶线 + 元信息栏建立「文档感」。

```html
<section style="margin:0 0 4px 0;border-top:3px solid #000000;padding:14px 0 0 0;">
  <p style="margin:0 0 6px 0;font-size:11px;color:#002FA7;font-weight:bold;letter-spacing:2px;">GUIDE / 实操</p>
</section>
<section style="margin:0 0 26px 0;">
  <h1 style="margin:0 0 14px 0;font-size:23px;line-height:1.42;color:#000000;font-weight:bold;">用三个动作，把专注时间从 47 秒拉回 40 分钟</h1>
  <section style="border-top:1px solid #D8D8D8;padding:12px 0 0 0;display:flex;flex-wrap:wrap;gap:6px 0;">
    <p style="margin:0 16px 0 0;font-size:12px;color:#8C8C8C;">阅读时长 6 分钟</p>
    <p style="margin:0 16px 0 0;font-size:12px;color:#8C8C8C;">适用：远程 / 混合办公</p>
    <p style="margin:0;font-size:12px;color:#8C8C8C;">更新：2026.09</p>
  </section>
</section>
```

### 3.2 结构预览表（目录即结构）

瑞士网格风的标志性组件：用表格把文章结构说清楚。

```html
<section style="margin:0 0 32px 0;">
  <table style="width:100%;border-collapse:collapse;font-size:13px;">
    <tr>
      <td style="padding:10px 12px 10px 0;border-bottom:1px solid #D8D8D8;width:44px;color:#002FA7;font-weight:bold;vertical-align:top;">01</td>
      <td style="padding:10px 0;border-bottom:1px solid #D8D8D8;color:#2B2B2B;font-weight:bold;">诊断：你的注意力漏在哪里</td>
    </tr>
    <tr>
      <td style="padding:10px 12px 10px 0;border-bottom:1px solid #D8D8D8;color:#002FA7;font-weight:bold;vertical-align:top;">02</td>
      <td style="padding:10px 0;border-bottom:1px solid #D8D8D8;color:#2B2B2B;font-weight:bold;">改造：三个不靠自律的环境动作</td>
    </tr>
    <tr>
      <td style="padding:10px 12px 10px 0;color:#002FA7;font-weight:bold;vertical-align:top;">03</td>
      <td style="padding:10px 0;color:#2B2B2B;font-weight:bold;">维持：让专注变成默认状态</td>
    </tr>
  </table>
</section>
```

### 3.3 章节标题（编号块 + 标题 + 细线）

```html
<section style="margin:40px 0 16px 0;">
  <section style="display:flex;align-items:center;gap:10px;margin:0 0 10px 0;">
    <section style="flex-shrink:0;width:26px;height:26px;background:#000000;color:#FFFFFF;text-align:center;line-height:26px;font-size:12px;font-weight:bold;">01</section>
    <h2 style="margin:0;font-size:18px;line-height:1.5;color:#000000;font-weight:bold;">诊断：你的注意力漏在哪里</h2>
  </section>
  <section style="height:1px;background:#000000;width:100%;"></section>
</section>
```

### 3.4 正文段落

```html
<p style="margin:0 0 18px 0;font-size:15px;line-height:1.8;color:#5A5A5A;">先别急着改。花两天时间记录每一次打断的来源，你会发现问题不在手机本身，而在于你给它留了太多「顺手就能拿起来」的位置。<strong style="color:#000000;">能被顺手拿到的东西，一定会被顺手拿起。</strong></p>
```

### 3.5 要点卡（浅底 + 左细线，非圆角卡片）

```html
<section style="margin:20px 0;padding:16px 18px;background:#EDF1FC;border-left:2px solid #002FA7;">
  <p style="margin:0 0 6px 0;font-size:11px;color:#002FA7;font-weight:bold;letter-spacing:2px;">要点</p>
  <p style="margin:0;font-size:14px;line-height:1.75;color:#2B2B2B;">记录打断来源，比统计专注时长更有用——前者能定位问题，后者只能让你焦虑。</p>
</section>
```

### 3.6 步骤表（编号 + 动作 + 说明）

```html
<section style="margin:22px 0;">
  <table style="width:100%;border-collapse:collapse;">
    <tr>
      <td style="width:28px;padding:14px 10px 14px 0;border-top:1px solid #E4E4E4;vertical-align:top;color:#002FA7;font-weight:bold;font-size:14px;">1</td>
      <td style="padding:14px 0;border-top:1px solid #E4E4E4;vertical-align:top;">
        <p style="margin:0 0 4px 0;font-size:15px;line-height:1.6;color:#000000;font-weight:bold;">把手机移出臂展范围</p>
        <p style="margin:0;font-size:13px;line-height:1.7;color:#8C8C8C;">放在需要起身才能拿到的地方，增加物理成本</p>
      </td>
    </tr>
    <tr>
      <td style="width:28px;padding:14px 10px 14px 0;border-top:1px solid #E4E4E4;vertical-align:top;color:#002FA7;font-weight:bold;font-size:14px;">2</td>
      <td style="padding:14px 0;border-top:1px solid #E4E4E4;vertical-align:top;">
        <p style="margin:0 0 4px 0;font-size:15px;line-height:1.6;color:#000000;font-weight:bold;">固定深度工作时段</p>
        <p style="margin:0;font-size:13px;line-height:1.7;color:#8C8C8C;">写进日历并设为忙碌，比"等有空"可靠得多</p>
      </td>
    </tr>
    <tr>
      <td style="width:28px;padding:14px 10px 14px 0;border-top:1px solid #E4E4E4;border-bottom:1px solid #E4E4E4;vertical-align:top;color:#002FA7;font-weight:bold;font-size:14px;">3</td>
      <td style="padding:14px 0;border-top:1px solid #E4E4E4;border-bottom:1px solid #E4E4E4;vertical-align:top;">
        <p style="margin:0 0 4px 0;font-size:15px;line-height:1.6;color:#000000;font-weight:bold;">只保留即时通讯推送</p>
        <p style="margin:0;font-size:13px;line-height:1.7;color:#8C8C8C;">其余全部关闭，改为主动查看而非被动响应</p>
      </td>
    </tr>
  </table>
</section>
```

### 3.7 数据行（网格化指标）

```html
<section style="margin:26px 0;">
  <table style="width:100%;border-collapse:collapse;">
    <tr>
      <td style="width:33.33%;padding:16px 8px;background:#F2F2F2;text-align:center;border-right:2px solid #FFFFFF;">
        <p style="margin:0 0 4px 0;font-size:24px;line-height:1.2;color:#000000;font-weight:bold;">47<span style="font-size:13px;">s</span></p>
        <p style="margin:0;font-size:11px;color:#8C8C8C;">平均专注时长</p>
      </td>
      <td style="width:33.33%;padding:16px 8px;background:#F2F2F2;text-align:center;border-right:2px solid #FFFFFF;">
        <p style="margin:0 0 4px 0;font-size:24px;line-height:1.2;color:#000000;font-weight:bold;">23<span style="font-size:13px;">min</span></p>
        <p style="margin:0;font-size:11px;color:#8C8C8C;">打断后恢复耗时</p>
      </td>
      <td style="width:33.33%;padding:16px 8px;background:#F2F2F2;text-align:center;">
        <p style="margin:0 0 4px 0;font-size:24px;line-height:1.2;color:#002FA7;font-weight:bold;">3<span style="font-size:13px;">步</span></p>
        <p style="margin:0;font-size:11px;color:#8C8C8C;">本文可执行动作</p>
      </td>
    </tr>
  </table>
</section>
```

### 3.8 配图 + 图注

```html
<section style="margin:26px 0;">
  <img src="IMAGE_URL" style="width:100%;display:block;" />
  <p style="margin:8px 0 0 0;font-size:11px;line-height:1.6;color:#8C8C8C;">图 1：打断来源分布（N=120，自测数据）</p>
</section>
```

### 3.9 文末：要点回顾 + 元信息

```html
<section style="margin:44px 0 0 0;border-top:3px solid #000000;padding:18px 0 0 0;">
  <p style="margin:0 0 12px 0;font-size:11px;color:#002FA7;font-weight:bold;letter-spacing:2px;">SUMMARY</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.75;color:#2B2B2B;">01 · 记录打断来源，定位真正的漏洞</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.75;color:#2B2B2B;">02 · 用物理距离代替意志力</p>
  <p style="margin:0 0 20px 0;font-size:14px;line-height:1.75;color:#2B2B2B;">03 · 把专注写进日程，而不是等它发生</p>
  <p style="margin:0;font-size:11px;color:#8C8C8C;">作者名 · 2026.09.05</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[顶线 + 分类标签 + 大标题 + 元信息行]
（可选：结构预览表）
（40px）
[章节 01：编号块 + 标题 + 细线]
（16px）
[正文 × 2]
（20px）
[要点卡]
（22px）
[步骤表]
（26px）
[数据行]
（44px）
[文末：要点回顾]
```

### 4.2 用字原则

1. **左对齐，不用居中**：居中会破坏网格秩序（金句除外）
2. **说明文字降到 11-13px**：用小字号承载信息密度，主次靠字号而非颜色
3. **数字用等宽感**：编号统一两位（01、02），视觉更整
4. **圆角为 0**：瑞士网格保持直角，圆角会削弱精确感
5. **表格优先**：多条目内容优先用 table，对齐比圆角卡更清晰

### 4.3 装饰预算

| 元素 | 全篇上限 |
|------|---------|
| 3px 顶线 | 2 处（首屏、文末） |
| 1px 细线 | 每节 1 条 |
| 浅底块 | 3 处 |
| 彩色文字 | 编号 + 数字 + 标签 |
| 深色块 | 每节 1 个编号方块 |
| SVG 信息图 | 0-1 个（须对齐到网格） |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 教程、操作指南、清单 | 抒情散文、人物故事 |
| 拆解分析、评测对比 | 品牌调性文章 |
| 需要读者照做的文章 | 需要情绪共鸣的内容 |

---

## 五、质量门禁

- 首屏含：分类线 + 标题 + 元信息行；目录表可选但不得与元信息行同时堆叠成墙
- 全文左对齐，除金句外不居中
- 表格列宽必须用 width 显式声明，避免微信自动布局错位
- 编号统一两位数，数字不得单独成行尾
- 每个数据块必须标注来源或口径
