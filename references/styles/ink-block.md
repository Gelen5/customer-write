# 墨块对比风 (ink-block)

> 视觉定位：强观点 / 品牌主张 / 短篇冲击
> 关键词：黑白、反差、决断、一眼记住
> 适合读者：被标题吸引、注意力只有 30 秒的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 强硬、直接、不留余地 |
| 节奏 | 黑白交替，深色块制造"停顿" |
| 配色 | 纯黑 + 纯白 + 三级灰，零彩色 |
| 字体 | 无衬线，粗字重 |
| 留白 | 极端：要么极紧，要么极松 |
| 装饰 | 只用色块反差，不用线条 |

**核心主张**：一篇文章只需要读者记住一件事。
用黑色块把那一件事"框"出来，其余全部留白。
这是六套主题里视觉冲击最强、也最容易过量的——深色块必须严格限量。

---

## 二、Color Token

### 2.1 主色调（纯黑白灰，无彩色）

| Token | 值 | 用途 |
|-------|------|------|
| `--c-black` | `#0E0E0E` | 深色块底、主标题 |
| `--c-ink` | `#1A1A1A` | 正文强调、小节标题 |
| `--c-body` | `#4D4D4D` | 正文主色 |
| `--c-muted` | `#8A8A8A` | 次要说明、图注 |
| `--c-line` | `#E0E0E0` | 极细线（几乎不用） |
| `--c-surface` | `#F5F5F5` | 浅灰底 |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调方式（不用彩色，用反白）

| Token | 值 | 用途 |
|-------|------|------|
| `--c-on-dark` | `#FFFFFF` | 深色块内主文字 |
| `--c-on-dark-dim` | `#B0B0B0` | 深色块内次要文字 |
| `--c-marker` | `#0E0E0E` | 行内重点底色（黑底白字，稀缺使用） |

> 唯一例外：如需单一信号色，使用 `#C8A15A`（旧金），仅用于 1 处。

---

## 三、组件变体

### 3.1 首屏：反白大块（本风格的识别资产）

标题直接放在纯黑块里，白字反白，冲击最强。

```html
<section style="background:#0E0E0E;padding:36px 26px;margin:0 0 32px 0;">
  <p style="margin:0 0 14px 0;font-size:11px;color:#8A8A8A;letter-spacing:3px;font-weight:bold;">MANIFESTO</p>
  <h1 style="margin:0 0 18px 0;font-size:26px;line-height:1.38;color:#FFFFFF;font-weight:bold;letter-spacing:0.5px;">你不需要更自律，<br/>你需要一个更狠的环境。</h1>
  <section style="width:40px;height:3px;background:#FFFFFF;margin:0 0 16px 0;"></section>
  <p style="margin:0;font-size:14px;line-height:1.75;color:#B0B0B0;">三个不需要意志力的改造动作，今天就能做完。</p>
</section>
```

### 3.2 正文段落（白底、较高对比）

```html
<p style="margin:0 0 24px 0;font-size:15px;line-height:1.85;color:#4D4D4D;">先说结论：靠意志力对抗推送通知，胜率接近于零。那些产品是几千人团队用 A/B 测试优化出来的，目标是让你多看一秒。<strong style="color:#1A1A1A;">你拿什么跟一个产业对抗？</strong></p>
```

### 3.3 核心断言块（深色块，全文最多 2 个）

```html
<section style="background:#0E0E0E;padding:26px 24px;margin:36px 0;">
  <p style="margin:0 0 10px 0;font-size:11px;color:#8A8A8A;letter-spacing:3px;font-weight:bold;">核心断言</p>
  <p style="margin:0;font-size:18px;line-height:1.75;color:#FFFFFF;font-weight:bold;">能被顺手拿到的东西，一定会被顺手拿起。</p>
</section>
```

### 3.4 小节标题（黑色方块 + 标题）

```html
<section style="margin:44px 0 18px 0;display:flex;align-items:center;gap:12px;">
  <section style="flex-shrink:0;width:6px;height:22px;background:#0E0E0E;"></section>
  <h2 style="margin:0;font-size:19px;line-height:1.5;color:#1A1A1A;font-weight:bold;">为什么自律这条路走不通</h2>
</section>
```

### 3.5 对比块（黑白两侧，不用彩色）

```html
<section style="margin:28px 0;display:flex;gap:10px;">
  <section style="flex:1;background:#F5F5F5;padding:18px 16px;">
    <p style="margin:0 0 8px 0;font-size:11px;color:#8A8A8A;letter-spacing:2px;font-weight:bold;">通常做法</p>
    <p style="margin:0;font-size:14px;line-height:1.7;color:#4D4D4D;">告诉自己"今天不看手机"，然后失败</p>
  </section>
  <section style="flex:1;background:#0E0E0E;padding:18px 16px;">
    <p style="margin:0 0 8px 0;font-size:11px;color:#8A8A8A;letter-spacing:2px;font-weight:bold;">有效做法</p>
    <p style="margin:0;font-size:14px;line-height:1.7;color:#FFFFFF;">把手机锁进另一个房间的抽屉</p>
  </section>
</section>
```

### 3.6 行内重点标记（黑底白字，稀缺）

```html
<p style="margin:0 0 24px 0;font-size:15px;line-height:1.85;color:#4D4D4D;">真正的差别在于<span style="background:#0E0E0E;color:#FFFFFF;padding:1px 6px;font-weight:bold;">物理距离</span>，而不是心理决心。</p>
```

> 全篇行内反白标记不超过 3 处。用多了就是噪音。

### 3.7 编号动作（黑底白字方块）

```html
<section style="margin:24px 0 30px 0;">
  <section style="display:flex;align-items:flex-start;margin:0 0 18px 0;">
    <section style="flex-shrink:0;width:26px;height:26px;background:#0E0E0E;color:#FFFFFF;text-align:center;line-height:26px;font-size:13px;font-weight:bold;">1</section>
    <p style="margin:0 0 0 12px;flex:1;font-size:15px;line-height:1.7;color:#1A1A1A;font-weight:bold;">手机放进另一个房间</p>
  </section>
  <section style="display:flex;align-items:flex-start;margin:0 0 18px 0;">
    <section style="flex-shrink:0;width:26px;height:26px;background:#0E0E0E;color:#FFFFFF;text-align:center;line-height:26px;font-size:13px;font-weight:bold;">2</section>
    <p style="margin:0 0 0 12px;flex:1;font-size:15px;line-height:1.7;color:#1A1A1A;font-weight:bold;">深度时段写进日历并设忙碌</p>
  </section>
  <section style="display:flex;align-items:flex-start;margin:0;">
    <section style="flex-shrink:0;width:26px;height:26px;background:#0E0E0E;color:#FFFFFF;text-align:center;line-height:26px;font-size:13px;font-weight:bold;">3</section>
    <p style="margin:0 0 0 12px;flex:1;font-size:15px;line-height:1.7;color:#1A1A1A;font-weight:bold;">关掉除通讯外全部推送</p>
  </section>
</section>
```

### 3.8 配图（去圆角、满幅）

```html
<section style="margin:30px 0;">
  <img src="IMAGE_URL" style="width:100%;display:block;" />
  <p style="margin:10px 0 0 0;font-size:12px;line-height:1.6;color:#8A8A8A;">图：物理距离与解锁频率的关系，来源：XXX</p>
</section>
```

### 3.9 文末：黑块收束

```html
<section style="background:#0E0E0E;padding:28px 24px;margin:44px 0 0 0;">
  <p style="margin:0 0 10px 0;font-size:11px;color:#8A8A8A;letter-spacing:3px;font-weight:bold;">记住这一句</p>
  <p style="margin:0;font-size:17px;line-height:1.75;color:#FFFFFF;font-weight:bold;">别再怪自己不够自律。把环境改好，专注会自己回来。</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[首屏：黑块大标题]
（32px）
[正文 × 2]
（36px）
[核心断言块（黑）]
（44px）
[小节：黑条 + 标题]
（18px）
[正文 × 2]
（28px）
[黑白对比块]
（24px）
[编号动作 × 3]
（44px）
[文末黑块]
```

### 4.2 用字原则

1. **深色块全篇 ≤ 3 个**（首屏、核心断言、文末）——超过就压抑
2. **两段黑块之间至少隔 3 段正文**，让读者喘口气
3. **行内反白标记 ≤ 3 处**
4. **不用圆角**：本风格保持直角，锐利感来自直角
5. **禁用彩色**：需要强调就用反白或加粗，不要引入第二种颜色

### 4.3 装饰预算（最严格）

| 元素 | 全篇上限 |
|------|---------|
| 深色块 | 3 个 |
| 行内反白标记 | 3 处 |
| 分隔线 | 0-1 条 |
| 浅灰底 | 1 处（对比块左侧） |
| 彩色 | 0 |
| SVG 信息图 | 0-1 个（须纯黑白） |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 强观点、宣言、品牌主张 | 长篇深度文（黑块撑不住） |
| 短篇冲击文、反常识 | 抒情、人物、故事 |
| 需要金句被截图的文章 | 数据密集型内容 |

---

## 五、质量门禁

- 深色块数量 ≤ 3，且彼此之间至少隔 3 段正文
- 首屏黑块内必须含：标签 + 标题 + 一句承诺，不叠加第二张卡
- 黑块内文字必须 ≥14px，白色正文不得使用 #8A8A8A 以下灰度
- 标题在 375px 宽度下不得出现 2-3 字孤行（黑块内尤其明显）
- 全篇零彩色；如出现第二种颜色，视为不合格
