# Onchain Narrative Research Skill

A Codex skill for turning crypto screenshots, wallets, token launches, founder posts, company narratives, and market rumors into verifiable onchain research.

This skill was born from a real research workflow: starting with a viral X post about a BSC meme trader's claimed profits, then verifying the wallet activity, decoding BSC receipt logs, reconstructing Four.meme trades, bucketing buys by FDV, and publishing the findings as a public GitHub Pages report.

## What It Does

Use this skill when you want to investigate:

- PnL screenshots and trader claims
- Public wallet addresses
- Token launch histories
- X posts, founder posts, and company announcements
- New meme/category leaders
- Narrative fermentation timelines
- Alpha source quality
- Bot-ready signal rules

The goal is not to blindly copy trades. The goal is to turn noisy leads into structured evidence:

- What happened onchain?
- Who or what started the story?
- Did the trader act before or after the narrative became obvious?
- Which FDV/liquidity/timing bucket created the edge?
- Which sources are worth tracking again?
- What could become an alert or bot rule after more validation?

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

## Install

Clone this repository and copy the skill folder into your Codex skills directory:

```bash
git clone https://github.com/hahahakang/onchain-narrative-research-skill.git
mkdir -p ~/.codex/skills
cp -R onchain-narrative-research-skill/onchain-narrative-research ~/.codex/skills/
```

Restart Codex after installation.

## Example Prompts

```text
Use onchain-narrative-research to investigate this PnL screenshot and wallet address. Verify whether the claimed profit is visible onchain, reconstruct the trader's buying buckets, and summarize the repeatable pattern.
```

```text
Use onchain-narrative-research to trace this token's narrative origin. Find the earliest source, map the social/onchain timeline, and identify whether it was the category leader or a copycat.
```

```text
Use onchain-narrative-research to turn this project/founder/company lead into a bot-ready signal hypothesis. Include source quality, time window, liquidity/FDV filters, and risk exclusions.
```

## Core Workflow

1. Frame the lead.
2. Preserve raw evidence.
3. Build the onchain and social data layer.
4. Reconstruct trading behavior.
5. Trace narrative origin and amplification.
6. Identify source quality and leader tokens.
7. Convert findings into signal hypotheses.
8. Publish a research artifact with caveats.

## Design Philosophy

Crypto markets often move on information speed and narrative formation. This skill treats information as a research object:

- screenshots are leads, not proof;
- wallets are evidence, not mythology;
- stories have timelines;
- first movers and true leaders should be separated from copycats;
- bots should start as research assistants before becoming execution engines.

## Disclaimer

This skill is for research and education only. It does not provide investment advice, trading recommendations, or guarantees of profit. Onchain data can be incomplete or misleading because of open positions, cross-wallet flows, private deals, taxes, honeypots, non-standard token mechanics, fake screenshots, copy-trader slippage, or delayed narrative discovery.

Always verify with primary sources and your own risk controls.

## License

MIT
