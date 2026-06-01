# onchain-narrative-research-skill

[English](README.md) | [中文](README.zh-CN.md)

An AI coding agent skill for turning crypto screenshots, wallets, tokens, posts, people, companies, and project narratives into clear onchain research.

Works with any AI coding agent that supports skill/instruction files, including Claude Code, Codex CLI, Cursor, Windsurf, Cline, and similar tools.

It helps answer practical questions:

- What actually happened onchain?
- Did the wallet really make money?
- Where did the token narrative start?
- Did the trader buy before or after the story became obvious?
- Which sources are worth tracking again?
- Which patterns can become alerts or bot rules?

## What Can It Analyze?

- PnL screenshots and trader claims
- Public wallet addresses
- Token launches and early trading
- X posts, founder posts, and company announcements
- New narratives, new categories, and first leader tokens
- Project sources, launch sources, and source quality
- Bot or alert rule design

## A Real Example

This skill came from a real research workflow.

I saw a BSC meme trader's post on X. The trader claimed to start with `5.8 BNB`, trade meme tokens for 127 days, and make more than 1.2 million RMB in cumulative profit.

Instead of trusting the screenshot, the workflow was:

1. Find the public BSC wallet.
2. Download transaction CSVs from BscScan.
3. Decode BSC transaction receipt logs.
4. Rebuild Four.meme buy and sell events.
5. Find each token's first buy time.
6. Calculate buy-time FDV and pool state.
7. Bucket entries by timing/FDV/liquidity.
8. Publish the result as a GitHub Pages research report.

Example report:

<https://hahahakang.github.io/bsc-fourmeme-analysis/>

## Installation

### Let Your Agent Install It

Paste this to your AI coding agent:

```text
Clone https://github.com/hahahakang/onchain-narrative-research-skill and install it as a reusable skill/instruction file.
```

The agent can copy or symlink `onchain-narrative-research/SKILL.md` into the right skill/instruction directory for your environment.

### Codex / Codex CLI

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git
mkdir -p ~/.codex/skills
cp -R onchain-narrative-research-skill/onchain-narrative-research ~/.codex/skills/
```

Then restart Codex.

### Claude Code

Clone the skill into your Claude skills directory:

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git ~/.claude/skills/onchain-narrative-research-skill
```

Then reference or invoke the skill in your Claude Code workflow.

### Cursor

Use the skill as a Cursor rule:

1. Create a rule file such as `.cursor/rules/onchain-narrative-research.mdc`.
2. Paste the contents of `onchain-narrative-research/SKILL.md`.
3. Add the reference files when your workflow needs deeper guidance.

### Windsurf / Cline / Other Agents

If your agent supports custom instructions, rules, or skill files, add the contents of:

```text
onchain-narrative-research/SKILL.md
```

Keep the `references/` folder nearby so the agent can load the detailed workflow guides when needed.

## Example Prompts

```text
Use onchain-narrative-research to investigate this PnL screenshot and wallet. Verify the onchain profit, reconstruct entry buckets, and summarize repeatable patterns.
```

```text
Use onchain-narrative-research to trace this token's narrative origin. Find the earliest source, build the social/onchain timeline, and decide whether it was a leader or a copycat.
```

```text
Use onchain-narrative-research to turn this founder/company/project lead into alert rules, including source quality, time window, FDV/liquidity filters, and risk exclusions.
```

## Workflow

1. Frame the lead.
2. Preserve raw evidence.
3. Build the onchain and social data layer.
4. Reconstruct trading behavior.
5. Trace narrative origin and amplification.
6. Identify source quality and leader tokens.
7. Convert findings into alert or bot rules.
8. Publish a research artifact with caveats.

## Repository Structure

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

## Principles

- Screenshots are leads, not proof.
- Wallets are evidence sources, not myths.
- Narratives have timelines: who said it first, who bought first, who amplified it.
- The first token is not always the leader. Liquidity, volume, and attention matter.
- Bots should start as research assistants before becoming trading executors.

## Disclaimer

This project is for research and education only. It is not investment advice and does not guarantee profit. Onchain data can be incomplete or misleading because of open positions, cross-wallet flows, private deals, taxes, honeypots, non-standard tokens, fake screenshots, copy-trader slippage, or delayed narrative discovery.

Always verify with primary sources and your own risk controls.

## License

MIT
