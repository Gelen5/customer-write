# 青瓷轻卡风 (porcelain-blue)

> 视觉定位：知识科普 / 工具测评 / 清单 / 行业解读
> 关键词：清爽、亲和、好读、结构轻柔
> 适合读者：通勤路上、想轻松吸收信息的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 平和、友好、讲人话 |
| 节奏 | 轻快，卡片把内容切成小块 |
| 配色 | 白 + 淡青底 + 青瓷色强调 |
| 字体 | 无衬线，常规字重为主 |
| 留白 | 中等，卡片内部靠 padding 而非大外部留白 |
| 装饰 | 细边框轻卡、小圆角、淡色底 |

**核心主张**：降低阅读门槛。
用轻边框卡片把长内容切成"一口一块"的小份，读者随时能停、随时能继续。
比 swiss-grid 柔和，比 pure-whitespace 亲和——是**最不容易出错的日常款**。

---

## 二、Color Token

### 2.1 主色调

| Token | 值 | 用途 |
|-------|------|------|
| `--c-ink` | `#1E2A2B` | 主标题 |
| `--c-title` | `#2F3E3F` | 小节标题 |
| `--c-body` | `#4E5C5D` | 正文主色，微青灰 |
| `--c-muted` | `#869596` | 说明文字、图注 |
| `--c-line` | `#DCE8EA` | 卡片边框、细线 |
| `--c-surface` | `#F5F9FA` | 淡青底（卡片） |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调色

| Token | 值 | 用途 |
|-------|------|------|
| `--c-accent` | `#2F7F82` | 唯一强调：编号、关键词、图标条 |
| `--c-accent-soft` | `#E6F1F1` | 青瓷浅底：要点卡 |
| `--c-accent-deep` | `#1F5F62` | 深色文字变体（小字强调） |

---

## 三、组件变体

### 3.1 首屏：淡青底圆角卡

```html
<section style="background:#F5F9FA;border:1px solid #DCE8EA;border-radius:12px;padding:28px 22px;margin:0 0 26px 0;">
  <p style="margin:0 0 12px 0;font-size:12px;color:#2F7F82;font-weight:bold;letter-spacing:2px;">科普 · 注意力</p>
  <h1 style="margin:0 0 14px 0;font-size:23px;line-height:1.45;color:#1E2A2B;font-weight:bold;">为什么你一坐下就想摸手机？</h1>
  <p style="margin:0 0 18px 0;font-size:15px;line-height:1.8;color:#4E5C5D;">不是你意志薄弱，是大脑在按设计好的程序走。看完这篇，你会知道怎么绕过去。</p>
  <section style="display:flex;flex-wrap:wrap;gap:6px;">
    <span style="display:inline-block;padding:4px 12px;background:#E6F1F1;color:#1F5F62;font-size:12px;border-radius:14px;">阅读 6 分钟</span>
    <span style="display:inline-block;padding:4px 12px;background:#FFFFFF;color:#869596;font-size:12px;border-radius:14px;border:1px solid #DCE8EA;">无门槛</span>
  </section>
</section>
```

### 3.2 正文段落

```html
<p style="margin:0 0 20px 0;font-size:15px;line-height:1.85;color:#4E5C5D;">先说机制：大脑对"不确定奖励"特别上瘾。每次解锁手机，你都不知道会看到什么——可能是一条重要消息，也可能什么都没有。<strong style="color:#1E2A2B;">正是这种"可能"，让解锁这个动作变得难以停止。</strong></p>
```

### 3.3 章节标题（圆形编号 + 标题）

```html
<section style="margin:36px 0 16px 0;display:flex;align-items:center;gap:10px;">
  <section style="flex-shrink:0;width:26px;height:26px;background:#2F7F82;border-radius:50%;color:#FFFFFF;text-align:center;line-height:26px;font-size:12px;font-weight:bold;">1</section>
  <h2 style="margin:0;font-size:18px;line-height:1.5;color:#2F3E3F;font-weight:bold;">机制：不确定奖励如何钩住你</h2>
</section>
```

### 3.4 要点卡（淡青底 + 左色条，圆角）

```html
<section style="background:#E6F1F1;border-radius:10px;padding:16px 18px;margin:20px 0;border-left:3px solid #2F7F82;">
  <p style="margin:0;font-size:14px;line-height:1.8;color:#1F5F62;">关键点：不确定奖励比确定奖励更容易形成习惯——这和老虎机的原理是一样的。</p>
</section>
```

### 3.5 知识卡（细边框白卡）

```html
<section style="background:#FFFFFF;border:1px solid #DCE8EA;border-radius:10px;padding:18px 20px;margin:18px 0;">
  <p style="margin:0 0 8px 0;font-size:12px;color:#2F7F82;font-weight:bold;letter-spacing:1px;">补充 · 什么是可变奖励</p>
  <p style="margin:0;font-size:14px;line-height:1.8;color:#4E5C5D;">指奖励的出现时机、内容或强度不固定。相比每次都给同样回馈，可变奖励会让行为频率显著上升，且更难消退。</p>
</section>
```

### 3.6 清单卡（打勾感）

```html
<section style="background:#F5F9FA;border:1px solid #DCE8EA;border-radius:10px;padding:18px 20px;margin:20px 0;">
  <p style="margin:0 0 12px 0;font-size:12px;color:#2F7F82;font-weight:bold;letter-spacing:1px;">三个可执行的动作</p>
  <p style="margin:0 0 10px 0;font-size:14px;line-height:1.75;color:#4E5C5D;">✓ 给手机设一个"需要起身"的位置</p>
  <p style="margin:0 0 10px 0;font-size:14px;line-height:1.75;color:#4E5C5D;">✓ 把深度工作时段写进日历</p>
  <p style="margin:0;font-size:14px;line-height:1.75;color:#4E5C5D;">✓ 只保留即时通讯的推送权限</p>
</section>
```

### 3.7 数据三宫格

```html
<section style="margin:22px 0;display:flex;gap:8px;">
  <section style="flex:1;background:#F5F9FA;border:1px solid #DCE8EA;border-radius:10px;padding:16px 8px;text-align:center;">
    <p style="margin:0 0 4px 0;font-size:22px;line-height:1.2;color:#2F7F82;font-weight:bold;">47<span style="font-size:12px;">s</span></p>
    <p style="margin:0;font-size:11px;line-height:1.5;color:#869596;">平均专注时长</p>
  </section>
  <section style="flex:1;background:#F5F9FA;border:1px solid #DCE8EA;border-radius:10px;padding:16px 8px;text-align:center;">
    <p style="margin:0 0 4px 0;font-size:22px;line-height:1.2;color:#2F7F82;font-weight:bold;">23<span style="font-size:12px;">min</span></p>
    <p style="margin:0;font-size:11px;line-height:1.5;color:#869596;">恢复耗时</p>
  </section>
  <section style="flex:1;background:#F5F9FA;border:1px solid #DCE8EA;border-radius:10px;padding:16px 8px;text-align:center;">
    <p style="margin:0 0 4px 0;font-size:22px;line-height:1.2;color:#2F7F82;font-weight:bold;">58<span style="font-size:12px;">次</span></p>
    <p style="margin:0;font-size:11px;line-height:1.5;color:#869596;">日均解锁</p>
  </section>
</section>
```

### 3.8 配图 + 图注（圆角卡）

```html
<section style="margin:24px 0;">
  <img src="IMAGE_URL" style="width:100%;display:block;border-radius:10px;" />
  <p style="margin:8px 0 0 0;font-size:12px;line-height:1.6;color:#869596;">图：解锁频率日分布，来源：XXX</p>
</section>
```

### 3.9 文末：总结卡

```html
<section style="background:#F5F9FA;border:1px solid #DCE8EA;border-radius:12px;padding:22px 20px;margin:36px 0 0 0;">
  <p style="margin:0 0 12px 0;font-size:12px;color:#2F7F82;font-weight:bold;letter-spacing:2px;">小结</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.8;color:#4E5C5D;">1 · 摸手机不是意志问题，是机制问题</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.8;color:#4E5C5D;">2 · 物理距离比心理决心更有效</p>
  <p style="margin:0 0 16px 0;font-size:14px;line-height:1.8;color:#4E5C5D;">3 · 把专注写进日程，而不是等它发生</p>
  <p style="margin:0;font-size:12px;color:#869596;">作者名 · 2026.09.05</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[首屏：淡青圆角卡]
（26px）
[正文 × 2]
（36px）
[章节 1：圆形编号 + 标题]
（16px）
[正文 × 2]
（20px）
[要点卡]
（18px）
[知识卡]
（20px）
[清单卡]
（22px）
[数据三宫格]
（36px）
[文末总结卡]
```

### 4.2 用字原则

1. **卡片不套卡片**：一个 section 就是一层，最多嵌套 2 层
2. **每 2-3 段放一个卡**：长文靠卡片切块，不要连续 5 段纯文字
3. **圆角统一 10-12px**：不要混用 4px / 8px / 16px
4. **边框只用 1px #DCE8EA**：不要加深边框或加阴影
5. **编号用圆形**：本风格偏亲和，圆形比方角柔和

### 4.3 装饰预算

| 元素 | 全篇上限 |
|------|---------|
| 淡青底卡 | 4 个 |
| 细边框白卡 | 3 个 |
| 左色条要点卡 | 2 个 |
| 深色块 | 0（本风格不用深色卡） |
| 圆角 | 统一 10-12px |
| SVG 信息图 | 0-1 个（须用青瓷色系） |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 科普、工具测评、清单 | 强观点宣言（气场不足） |
| 行业解读、新手向内容 | 严肃商业分析 |
| 需要长期高频更新的号 | 追求极致质感的品牌文 |

---

## 五、质量门禁

- 首屏必须是一张完整卡，卡外不叠加目录/标签墙
- 卡片总数 ≤ 8，超过会让页面变成"卡片展览"
- 每 2-3 段正文必须有 1 个视觉组件，但不得连续 3 个卡片
- 圆形编号统一尺寸 26px，文字垂直居中用 line-height 而非 flex 高度
- 数据必须标注口径或来源
