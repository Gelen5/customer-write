# customer-write

微信公众号全链路内容 Agent（融合版）—— 由 **wechat-publisher-ultimate**（全链路创作管道）与 **gzh-design**（主题排版引擎）融合而成的独立 Skill，**排版引擎已内置，零外部依赖**。

## 一句话

从选题、写作、反AI、配图、排版到发布，一条龙搞定；排版直接内置 4 套主题组件库 + 通用增量库，产出可直接粘贴进公众号编辑器且样式不丢失的 HTML。

## 能力总览

| 模块 | 能力 |
|------|------|
| 8步全链路管道 | 环境检查 → 选题 → 框架+素材 → 写作 → 反AI+SEO → 视觉AI → 排版 → 发布 |
| 反AI（强制步骤） | 3层 humanness 评分（统计50% / 模式30% / 语义20%）+ 定向修复 + AI禁用词替换表 |
| 写作 | 7种人格 × 7种框架、范文 SICO 风格注入、维度随机化、内容增强4策略 |
| 排版（内置引擎） | 10套可用主题（红白/石墨/票据/橄榄/天蓝学堂/珊瑚招贴/考务蓝/墨蓝批注/琥珀速读/黛青复盘）+ 通用增量库、`<span leaf>` 防裂包裹、合规校验脚本、一键复制预览页 |
| 自定义主题 | theme-generator 流程：按描述/参考图生成新区块库并登记复用 |
| 输入归一化 | Markdown / Word(.docx) / PDF / 纯文本 均可进入排版 |
| 配图 | 9级 Fallback 链（SVG信息图 → 截图 → 网图base64 → AI生图 → 图库 → 占位） |
| 交付 | 双轨：零门槛「复制到公众号」预览页 + 微信 API 一键入库（草稿箱） |
| 扩展模式 | 小绿书 / 贴图号（tie-tu toolkit）、微信推荐质量门禁、学习飞轮 |

## 目录结构

```
customer-write/
├── SKILL.md                 # 主流程：8步管道 + 排版决策 + 命令
├── personas/                # 14 种写作人格配置（YAML）
├── prompts/                 # 排版/反AI提示词模板
├── references/              # 管道参考文件（组件库、移动端质量门禁、AI禁用词表等）
│   ├── themes/              # ★ 内置主题排版引擎（原 gzh-design）
│   │   ├── README.md        #   排版节点对接契约（必读）
│   │   ├── theme-index.md   #   主题单一权威来源
│   │   ├── theme-*.md       #   各主题组件库
│   │   ├── common-components.md  # 通用增量库（代码块/图片/小标签）
│   │   ├── theme-generator.md    # 自定义主题生成
│   │   └── format-normalize.md   # 非 Markdown 输入归一化
│   └── styles/              # 降级风格预设（仅引擎不可用时使用）
├── scripts/                 # Node（发布/渲染/配图）+ Python（校验/评分/预览）
├── toolkit/                 # 贴图号（tie-tu）独立工作流
├── assets/                  # 预览模板 / 示例文章 / 主题预览页
└── docs/                    # 主题总览文档
```

## 快速开始

1. 把本目录安装为 Skill（复制到 `~/.workbuddy/skills/` 或按宿主的 skill 安装方式注册）。
2. 对 Agent 说：
   - 「帮我写一篇关于 X 的公众号文章」→ 全自动 8 步管道
   - 「只排版这篇文章」→ 单步进入排版引擎
   - 「主题画廊」→ 查看可用主题
3. 排版产物：`{文件名}_排版_{主题名}.html` + `_预览.html`（浏览器打开 → 点「复制」→ 公众号编辑器粘贴）。

## API 入库（可选）

在公众号后台获取 AppID/AppSecret 写入 `.env`（参考 `.env.example`），并把本机公网 IP 加入白名单后，可一键进草稿箱。不做配置也可正常使用「复制预览」交付。

## 来源与致谢

融合自以下项目的能力精华：wewrite、md2wechat、wechat-publisher、kol-writer、gzh-design。各来源贡献详见 `SKILL.md` 开头表格。

## License

见 [LICENSE](LICENSE)。
