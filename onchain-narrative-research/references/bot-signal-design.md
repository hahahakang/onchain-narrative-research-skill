# Bot Signal Design

Use this when turning onchain/narrative research into alerts, scoring, or trading-bot rules.

## Principle

Do not automate a story after one case. Convert findings into hypotheses, then backtest or forward-test on multiple cases.

The bot should first reduce information noise. Execution automation comes later.

## Signal Components

Each signal should define:

- `trigger`: what starts evaluation;
- `source`: X account, company, founder, token deploy, wallet buy, pool creation;
- `time_window`: how long the edge likely lasts;
- `market_node`: FDV/liquidity/volume/holder condition;
- `source_score`: credibility and historical lead time;
- `chain_score`: onchain quality and risk;
- `narrative_score`: novelty, clarity, amplification potential;
- `execution_rule`: alert-only, manual confirm, semi-auto, auto;
- `risk_rule`: max size, skip conditions, exit triggers;
- `postmortem`: what to record after outcome.

## Early Meme/Launch Filters

Candidate filters:

- FDV bucket at first signal;
- pool BNB/ETH/SOL liquidity;
- buy/sell ratio in first minutes;
- unique buyers and wallet quality;
- deployer history;
- token tax/honeypot checks;
- holder concentration;
- time from narrative origin to deploy;
- time from deploy to first credible amplifier;
- whether token is first-in-category or copycat.

## Scoring Example

Use a conservative scoring model:

- Source quality: 0-25
- Narrative novelty: 0-20
- Time advantage: 0-20
- Onchain quality: 0-20
- Liquidity/execution quality: 0-10
- Risk penalty: -50 to 0

Actions:

- `0-39`: ignore;
- `40-59`: watchlist;
- `60-74`: alert human;
- `75+`: high-priority manual review.

Avoid immediate auto-buy until the scoring model has enough historical cases.

## Entry And Exit Hypotheses

For each discovered edge, write explicit hypotheses:

- "Buying before first large amplifier is profitable only when liquidity is above X and FDV below Y."
- "First-in-category tokens outperform copycats during the first N hours."
- "Founder/company primary-source tokens require a longer fermentation window than pure meme launches."
- "High-FDV chase after amplification is negative EV unless volume and liquidity expand."

## Bot Output

An alert should include:

- source link;
- token address;
- deploy time;
- liquidity and FDV;
- source score;
- narrative summary;
- similar historical cases;
- risk flags;
- suggested action: ignore/watch/review.

## Risk

Explicitly warn for:

- private group latency;
- source spoofing;
- fake official accounts;
- deleted/edited posts;
- honeypots and taxes;
- low liquidity slippage;
- MEV/sandwich risk;
- copy-trader crowding;
- wallet clustering that fakes demand.
