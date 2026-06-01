# Source Library Method

Use this when the goal is to accumulate high-quality alpha sources, project sources, launch sources, or category leaders.

## Source Objects

Represent each source as a durable object:

- `source_id`
- `source_type`: person, company, project, founder, official account, researcher, deployer, wallet, community, platform
- `name`
- `urls`
- `chain/ecosystem`
- `historical_hits`
- `false_positives`
- `average_lead_time`
- `typical_category`
- `confidence`
- `notes`

## Token/Project Objects

Represent each discovered token/project:

- `token_address`
- `chain`
- `symbol/name`
- `category`
- `narrative`
- `first_source`
- `first_public_timestamp`
- `deploy_timestamp`
- `first_liquidity_timestamp`
- `leader_or_copycat`
- `max_fdv`
- `source_quality`
- `research_status`

## Quality Signals

High-quality source patterns:

- repeatedly creates or reveals new categories;
- source appears before market attention, not after;
- linked to builders, companies, founders, labs, or official projects;
- historically leads to first tradeable tokens or leader tokens;
- low false-positive rate after risk filters;
- has a measurable lead time advantage.

Low-quality source patterns:

- only reposts already-pumped tokens;
- many copycat calls without original context;
- no consistent lead time;
- high bot engagement and low primary evidence;
- narratives that cannot be tied to primary sources.

## Leader Token Logic

When a new category appears, identify:

- first token by deploy time;
- first token with meaningful liquidity;
- first token with broad social attention;
- token with highest sustained volume;
- token with best holder distribution;
- token most directly tied to primary source.

The "first token" is not always the "leader token". Track both.

## Update Practice

After each research case:

1. Add source candidates.
2. Add token/project cases.
3. Record whether the source was early, late, or noisy.
4. Record whether the token was leader or copycat.
5. Convert repeatable observations into signal hypotheses.

## Community Research Workflow

For community use:

- let members submit screenshots, links, wallet addresses, and token addresses;
- require exact URLs and timestamps whenever possible;
- tag each submission as unverified, in-progress, verified, or rejected;
- publish research artifacts openly;
- keep raw evidence separate from conclusions;
- reward source quality, not just profit screenshots.
