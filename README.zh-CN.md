# onchain-narrative-research-skill

[English](README.md) | [中文](README.zh-CN.md)

一个用于 AI 编码代理的加密链上研究 skill / instruction package。它帮助你把「晒单截图、钱包地址、代币、推文、公司/人物线索、项目叙事」整理成可检查的链上研究。

可与任何支持 skill / instruction files（技能/指令文件）的 AI 编码代理配合使用，包括 Claude Code、Codex CLI、Cursor、Windsurf、Cline 等。

它主要回答这些实际问题：

- 链上到底发生了什么？
- 钱包是不是真的赚钱？
- 这个代币最早的叙事来源是谁？
- 交易员是在故事发酵前买，还是大家都知道后才买？
- 哪些来源以后值得继续跟踪？
- 哪些规律可以变成提醒或机器人规则？

## 它适合分析什么？

- 晒单截图和交易员收益声明
- 公开钱包地址
- 代币发行和早期交易
- X 推文、创始人发言、公司公告
- 新叙事、新类目、第一个龙头币
- 项目源、发币源、信息源质量
- 半自动机器人或提醒规则

## 一个真实例子

这个 skill 来自一次真实研究。

我在 X 上看到一个 BSC meme 交易员的复盘。他说自己从 `5.8 BNB` 开始，连续打狗 127 天，累计盈利超过 120 万人民币。

我没有直接相信截图，而是做了这些事：

1. 找到公开 BSC 钱包地址。
2. 从 BscScan 下载交易 CSV。
3. 解析 BSC transaction receipt logs。
4. 还原 Four.meme 上的买卖事件。
5. 找出每个 token 的第一次买入时间。
6. 计算买入时 FDV 和池子状态。
7. 按买入节点分桶。
8. 最后发布成一个 GitHub Pages 研究报告。

示例报告：

<https://hahahakang.github.io/bsc-fourmeme-analysis/>

## 安装

### 让你的 AI 代理安装

把下面这句话发给你的 AI 编码代理：

```text
Clone https://github.com/hahahakang/onchain-narrative-research-skill，并把它安装成一个可复用的 skill / instruction file。
```

代理可以根据当前工具环境，把 `onchain-narrative-research/SKILL.md` 复制或软链接到对应的技能/指令目录。

### Codex / Codex CLI

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git
mkdir -p ~/.codex/skills
cp -R onchain-narrative-research-skill/onchain-narrative-research ~/.codex/skills/
```

然后重启 Codex。

### Claude Code

把 skill clone 到 Claude skills 目录：

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git ~/.claude/skills/onchain-narrative-research-skill
```

然后在 Claude Code 工作流中引用或调用这个 skill。

### Cursor

把它作为 Cursor rule 使用：

1. 创建规则文件，例如 `.cursor/rules/onchain-narrative-research.mdc`。
2. 粘贴 `onchain-narrative-research/SKILL.md` 的内容。
3. 如果需要更完整的方法论，把 `references/` 里的文件也放在附近，方便代理读取。

### Windsurf / Cline / 其他代理

如果你的代理支持 custom instructions、rules 或 skill files，把下面这个文件的内容加入对应位置：

```text
onchain-narrative-research/SKILL.md
```

建议同时保留 `references/` 文件夹，方便代理在需要时读取更详细的流程。

## 使用示例

```text
用 onchain-narrative-research 分析这个晒单截图和钱包地址。验证收益是否能在链上看到，找出他主要在哪个买入节点赚钱，并总结可复用规律。
```

```text
用 onchain-narrative-research 追踪这个 token 的叙事来源。找出最早的推文/人物/项目来源，整理社交传播和链上交易时间线，判断它是龙头还是跟风。
```

```text
用 onchain-narrative-research 把这个项目/创始人/公司线索整理成机器人提醒规则。包括来源质量、时间窗口、FDV/流动性过滤和风险排除条件。
```

## 工作流程

1. 明确线索是什么。
2. 保存原始证据。
3. 收集链上和社交数据。
4. 还原交易行为。
5. 追踪叙事源头和传播过程。
6. 判断来源质量和龙头 token。
7. 提炼成提醒或机器人规则。
8. 输出研究报告和风险说明。

## 仓库结构

```text
onchain-narrative-research/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── bot-signal-design.md
    ├── narrative-timeline.md
    └── source-library.md
```

文件说明：

- `SKILL.md`: skill 主流程
- `narrative-timeline.md`: 追踪叙事源头和发酵时间线
- `source-library.md`: 沉淀项目源、人物源、发币源
- `bot-signal-design.md`: 把研究结论转成提醒/机器人规则

## 设计原则

- 截图是线索，不是证据。
- 钱包地址是证据入口，不是神话。
- 叙事有时间线，谁先说、谁先买、谁放大，很重要。
- 第一个出现的 token 不一定是真龙头，要看流动性、成交量和传播。
- 机器人应该先做信息整理和提醒，再谈自动交易。

## 免责声明

这个项目只用于研究和教育，不构成投资建议，也不保证盈利。链上数据可能因为未平仓仓位、跨钱包转账、私下交易、税费、貔貅盘、非标准 token、假截图、跟单滑点或叙事发现延迟而产生误导。

请始终使用一手来源和自己的风险控制再次确认。

## License

MIT
