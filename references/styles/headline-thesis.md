# 头条主张风 (headline-thesis)

> 视觉定位：观点冲击 / 热点解读 / 反常识立论
> 关键词：主题先行、一眼看懂、主张前置
> 适合读者：快速扫读、先看结论再决定读不读的人

---

## 一、视觉定位

| 维度 | 描述 |
|------|------|
| 语气 | 果断、有立场、不绕弯 |
| 节奏 | 首屏重击，正文轻快 |
| 配色 | 白 + 墨黑 + 砖红强调 |
| 字体 | 无衬线，标题超大字号 |
| 留白 | 首屏紧凑、正文宽松 |
| 装饰 | 主张条（左侧粗竖线）、大号章节数字 |

**核心主张**：把「这篇文章要说什么」放在读者第一眼能看到的位置。
标题之下不是引言，而是**一句话主张（Thesis）**——读者读完这一句就知道值不值得往下读。

---

## 二、Color Token

### 2.1 主色调

| Token | 值 | 用途 |
|-------|------|------|
| `--c-ink` | `#161514` | 主标题、正文强调 |
| `--c-body` | `#413E3A` | 正文主色，偏暖 |
| `--c-muted` | `#77726B` | 次要说明 |
| `--c-faint` | `#A9A49C` | 日期、图注 |
| `--c-line` | `#E7E3DC` | 分隔线、细边框 |
| `--c-surface` | `#FBF9F7` | 浅底（论据块） |
| `--c-bg` | `#FFFFFF` | 页面底色 |

### 2.2 强调色

| Token | 值 | 用途 |
|-------|------|------|
| `--c-accent` | `#B23A2E` | 唯一强调：主张条、章节数字、关键词 |
| `--c-accent-tint` | `#FDF4F2` | 砖红浅底：主张框、警示 |

---

## 三、组件变体

### 3.1 首屏：刊头 + 超大标题 + 主张条

主张条是本风格的识别资产——一条 3px 砖红竖线 + 一句完整主张。

```html
<section style="margin:0 0 28px 0;">
  <p style="margin:0 0 16px 0;font-size:12px;color:#A9A49C;letter-spacing:2px;font-weight:bold;">观点 · 2026年9月5日</p>
  <h1 style="margin:0 0 22px 0;font-size:27px;line-height:1.36;color:#161514;font-weight:bold;letter-spacing:0.5px;">专注力不是被手机偷走的，是被你主动让出去的。</h1>
  <section style="border-left:3px solid #B23A2E;padding:2px 0 2px 16px;margin:0;">
    <p style="margin:0;font-size:16px;line-height:1.75;color:#161514;font-weight:bold;">我们高估了意志力的作用，低估了环境设计的力量。</p>
  </section>
</section>
```

### 3.2 论据预告（三行要点，可选）

首屏之下可选放一组三行要点，告诉读者文章会证明什么。篇幅短的文章可省略。

```html
<section style="margin:0 0 32px 0;padding:20px 22px;background:#FBF9F7;">
  <p style="margin:0 0 10px 0;font-size:12px;color:#B23A2E;font-weight:bold;letter-spacing:2px;">本文会证明</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.7;color:#413E3A;">· 意志力在注意力争夺战中几乎无效</p>
  <p style="margin:0 0 8px 0;font-size:14px;line-height:1.7;color:#413E3A;">· 真正的变量是你允许了什么进入视野</p>
  <p style="margin:0;font-size:14px;line-height:1.7;color:#413E3A;">· 三个不依赖自律的环境改造动作</p>
</section>
```

### 3.3 正文段落

```html
<p style="margin:0 0 22px 0;font-size:15px;line-height:1.85;color:#413E3A;">先说一个不太舒服的事实：那些号称靠自律解决问题的人，往往只是环境恰好帮他们挡住了大部分干扰。<strong style="color:#161514;">你对抗的不是自己的欲望，是一整套为抢占注意力而设计的产品。</strong></p>
```

### 3.4 章节标题（大号数字 + 标题）

数字用超大字号低透明度，制造杂志内页感。

```html
<section style="margin:48px 0 18px 0;">
  <p style="margin:0 0 4px 0;font-size:30px;line-height:1;color:#B23A2E;font-weight:bold;opacity:0.22;">01</p>
  <h2 style="margin:0;font-size:19px;line-height:1.5;color:#161514;font-weight:bold;">意志力是个被高估的词</h2>
</section>
```

### 3.5 反常识标注块

用来放「你可能以为是 A，其实是 B」的判断。

```html
<section style="margin:28px 0;padding:18px 20px;background:#FDF4F2;">
  <p style="margin:0 0 6px 0;font-size:12px;color:#B23A2E;font-weight:bold;letter-spacing:2px;">反常识</p>
  <p style="margin:0;font-size:15px;line-height:1.8;color:#413E3A;">把手机调成静音没有用。真正有效的是把它放到你在座位上够不到的地方——增加一次起身的成本，就能砍掉八成的无意识解锁。</p>
</section>
```

### 3.6 金句（居中大字）

```html
<section style="margin:38px 0;padding:0;text-align:center;">
  <p style="margin:0;font-size:18px;line-height:1.8;color:#161514;font-weight:bold;">环境替你做的决定，比你替自己做得多得多。</p>
</section>
```

### 3.7 行动清单（编号 + 勾选感）

```html
<section style="margin:24px 0 30px 0;">
  <p style="margin:0 0 16px 0;font-size:12px;color:#B23A2E;font-weight:bold;letter-spacing:2px;">三个动作</p>
  <section style="display:flex;align-items:flex-start;margin:0 0 14px 0;">
    <section style="flex-shrink:0;width:22px;height:22px;background:#161514;color:#FFFFFF;text-align:center;line-height:22px;font-size:12px;font-weight:bold;">1</section>
    <p style="margin:0 0 0 10px;flex:1;font-size:15px;line-height:1.7;color:#413E3A;">工作时段把手机放进另一个房间</p>
  </section>
  <section style="display:flex;align-items:flex-start;margin:0 0 14px 0;">
    <section style="flex-shrink:0;width:22px;height:22px;background:#161514;color:#FFFFFF;text-align:center;line-height:22px;font-size:12px;font-weight:bold;">2</section>
    <p style="margin:0 0 0 10px;flex:1;font-size:15px;line-height:1.7;color:#413E3A;">给深度工作固定时段，写进日历</p>
  </section>
  <section style="display:flex;align-items:flex-start;margin:0;">
    <section style="flex-shrink:0;width:22px;height:22px;background:#161514;color:#FFFFFF;text-align:center;line-height:22px;font-size:12px;font-weight:bold;">3</section>
    <p style="margin:0 0 0 10px;flex:1;font-size:15px;line-height:1.7;color:#413E3A;">关闭除即时通讯外的全部推送</p>
  </section>
</section>
```

### 3.8 配图 + 图注

```html
<section style="margin:30px 0;">
  <img src="IMAGE_URL" style="width:100%;display:block;" />
  <p style="margin:10px 0 0 0;font-size:12px;line-height:1.6;color:#A9A49C;">图：切换任务后的注意力恢复曲线，来源：XXX</p>
</section>
```

### 3.9 文末：回到主张

头条主张风的结尾要**呼应开头的 Thesis**，形成闭环。

```html
<section style="margin:48px 0 0 0;padding:22px 0 0 0;border-top:2px solid #161514;">
  <p style="margin:0 0 12px 0;font-size:12px;color:#B23A2E;font-weight:bold;letter-spacing:2px;">回到开头</p>
  <p style="margin:0 0 16px 0;font-size:16px;line-height:1.75;color:#161514;font-weight:bold;">别再怪自己不够自律。把环境改好，专注会自己回来。</p>
  <p style="margin:0;font-size:13px;color:#A9A49C;">作者名 · 每周更新</p>
</section>
```

---

## 四、排版建议

### 4.1 节奏控制

```
[首屏：刊头 + 27px 标题 + 主张条]
（可选：论据预告）
（32px）
[正文 × 2]
（48px）
[章节 01：大数字 + 标题]
（18px）
[正文 × 2]
（28px）
[反常识块]
（38px）
[金句]
（24px）
[行动清单]
（48px）
[文末：回到主张]
```

### 4.2 用字原则

1. **主张句必须完整**：是一句有主谓宾的判断，不是半句话
2. **标题 24-28px**：本风格标题是全篇最大元素，不要缩水
3. **首屏不写铺垫**：不要「随着…的发展」「在当今社会」这类开场
4. **每节一个小标题**：小标题本身要带观点，不要写「什么是专注力」
5. **结尾回环**：必须呼应 Thesis，不能突然收掉

### 4.3 装饰预算

| 元素 | 全篇上限 |
|------|---------|
| 主张条（左侧竖线） | 1 处（首屏） |
| 砖红浅底块 | 2 处 |
| 大号章节数字 | 每节 1 个 |
| 深色块 | 3 个以内（编号方块） |
| 金句居中 | 2 处 |
| SVG 信息图 | 0-1 个 |

### 4.4 适合 / 不适合

| 适合 | 不适合 |
|------|--------|
| 观点文、热点解读、行业评论 | 抒情散文、人物故事 |
| 反常识立论、方法论 | 纯资讯快讯 |
| 需要强转化的文章 | 超长深度长文（主张撑不住） |

---

## 五、质量门禁

- 首屏必须含：刊头 + 主标题 + 完整主张句，且不叠加第二张卡
- 主张句必须自洽，读者读完第一屏就知道文章立场
- 大数字标题不得与小节标题抢视线，透明度控制在 0.2 左右
- 标题末行不得出现 2-3 字孤行；主张条内文字不得只高亮半句
- 结尾必须回环到首屏主张
