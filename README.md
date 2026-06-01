# Onchain Narrative Research Skill

中文 / English

一个用于 Codex 的加密链上研究 skill。它帮助你把「晒单截图、钱包地址、代币、推文、公司/人物线索、项目叙事」整理成可检查的链上研究。

A Codex skill for turning crypto screenshots, wallets, tokens, posts, people, companies, and project narratives into clear onchain research.

---

## 这个项目解决什么问题？ / What problem does this solve?

加密社区里每天都有很多信息：

- 有人晒收益截图；
- 有人公开钱包地址；
- 有人说某个新币是龙头；
- 某个创始人、公司、项目负责人发了一条推文；
- 市场突然开始炒一个新概念。

这些信息可能是真的，也可能只是噪音。这个 skill 的作用是把它们拆开看：

- 链上到底发生了什么？
- 钱包是不是真的赚钱？
- 这个代币最早的叙事来源是谁？
- 交易员是在故事发酵前买，还是大家都知道后才买？
- 哪些来源以后值得继续跟踪？
- 哪些规律可以变成提醒或机器人规则？

Crypto has lots of noisy signals every day:

- profit screenshots;
- public wallets;
- new tokens claiming to be category leaders;
- founder/company/project posts;
- sudden new market narratives.

This skill helps turn those leads into evidence:

- What actually happened onchain?
- Did the wallet really make money?
- Where did the token narrative start?
- Did the trader buy before or after the story became obvious?
- Which sources are worth tracking again?
- Which patterns can become alerts or bot rules?

---

## 它适合用来分析什么？ / What can it analyze?

- 晒单截图和交易员收益声明 / PnL screenshots and trader claims
- 公开钱包地址 / Public wallet addresses
- 代币发行和早期交易 / Token launches and early trading
- X 推文、创始人发言、公司公告 / X posts, founder posts, company announcements
- 新叙事、新类目、第一个龙头币 / New narratives, new categories, first leader tokens
- 项目源、发币源、信息源质量 / Project sources, launch sources, source quality
- 半自动机器人或提醒规则 / Bot or alert rule design

---

## 一个真实例子 / A real example

这个 skill 来自一次真实研究。

我在 X 上看到一个 BSC meme 交易员的复盘。他说自己从 `5.8 BNB` 开始，连续打狗 127 天，累计盈利超过 120 万人民币。

我没有直接相信截图，而是做了这些事：

1. 找到公开 BSC 钱包地址；
2. 从 BscScan 下载交易 CSV；
3. 解析 BSC transaction receipt logs；
4. 还原 Four.meme 上的买卖事件；
5. 找出每个 token 的第一次买入时间；
6. 计算买入时 FDV 和池子状态；
7. 按买入节点分桶；
8. 最后发布成一个 GitHub Pages 研究报告。

That real workflow became this skill:

1. Start from a public claim.
2. Collect wallet and transaction data.
3. Decode onchain logs.
4. Rebuild buys and sells.
5. Bucket entries by FDV/liquidity/timing.
6. Trace the story behind the token.
7. Publish the result with caveats.

Example report:

<https://hahahakang.github.io/bsc-fourmeme-analysis/>

---

## 安装 / Install

Clone this repo and copy the skill folder into your Codex skills directory:

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git
mkdir -p ~/.codex/skills
cp -R onchain-narrative-research-skill/onchain-narrative-research ~/.codex/skills/
```

Then restart Codex.

---

## 如何使用 / How to use

中文示例：

```text
用 onchain-narrative-research 分析这个晒单截图和钱包地址。验证收益是否能在链上看到，找出他主要在哪个买入节点赚钱，并总结可复用规律。
```

```text
用 onchain-narrative-research 追踪这个 token 的叙事来源。找出最早的推文/人物/项目来源，整理社交传播和链上交易时间线，判断它是龙头还是跟风。
```

```text
用 onchain-narrative-research 把这个项目/创始人/公司线索整理成机器人提醒规则。包括来源质量、时间窗口、FDV/流动性过滤和风险排除条件。
```

English examples:

```text
Use onchain-narrative-research to investigate this PnL screenshot and wallet. Verify the onchain profit, reconstruct entry buckets, and summarize repeatable patterns.
```

```text
Use onchain-narrative-research to trace this token's narrative origin. Find the earliest source, build the social/onchain timeline, and decide whether it was a leader or a copycat.
```

```text
Use onchain-narrative-research to turn this founder/company/project lead into alert rules, including source quality, time window, FDV/liquidity filters, and risk exclusions.
```

---

## 工作流程 / Workflow

1. 明确线索是什么 / Frame the lead
2. 保存原始证据 / Preserve raw evidence
3. 收集链上和社交数据 / Build the onchain and social data layer
4. 还原交易行为 / Reconstruct trading behavior
5. 追踪叙事源头和传播过程 / Trace narrative origin and amplification
6. 判断来源质量和龙头 token / Identify source quality and leader tokens
7. 提炼成提醒或机器人规则 / Convert findings into alert or bot rules
8. 输出研究报告和风险说明 / Publish a research artifact with caveats

---

## 仓库结构 / Repository structure

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

---

## 设计原则 / Principles

中文：

- 截图是线索，不是证据。
- 钱包地址是证据入口，不是神话。
- 叙事有时间线，谁先说、谁先买、谁放大，很重要。
- 第一个出现的 token 不一定是真龙头，要看流动性、成交量和传播。
- 机器人应该先做信息整理和提醒，再谈自动交易。

English:

- Screenshots are leads, not proof.
- Wallets are evidence sources, not myths.
- Narratives have timelines: who said it first, who bought first, who amplified it.
- The first token is not always the leader. Liquidity, volume, and attention matter.
- Bots should start as research assistants before becoming trading executors.

---

## 免责声明 / Disclaimer

中文：

这个项目只用于研究和教育，不构成投资建议，也不保证盈利。链上数据可能因为未平仓仓位、跨钱包转账、私下交易、税费、貔貅盘、非标准 token、假截图、跟单滑点或叙事发现延迟而产生误导。

English:

This project is for research and education only. It is not investment advice and does not guarantee profit. Onchain data can be incomplete or misleading because of open positions, cross-wallet flows, private deals, taxes, honeypots, non-standard tokens, fake screenshots, copy-trader slippage, or delayed narrative discovery.

Always verify with primary sources and your own risk controls.

---

## License

MIT
