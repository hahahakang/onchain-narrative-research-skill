# Narrative Timeline Workflow

Use this when the task involves tracing a token's story source, a founder/company/person catalyst, a viral X post, or a new category leader.

## Timeline Layers

Build the timeline in these layers:

1. **Origin Event**
   - Original X post, article, product release, company announcement, founder quote, meme image, public incident, app launch, repo release, or onchain deployment.
   - Prefer original URL and exact timestamp.

2. **Tokenization Event**
   - Token deployment time.
   - Pair/pool creation time.
   - First buy/sell time.
   - First meaningful liquidity threshold.
   - First holder cluster.

3. **Amplification Event**
   - Early accounts interpreting the story.
   - Large accounts reposting.
   - Telegram/Discord/community spread.
   - Price/volume breakout windows.

4. **Market Structure Event**
   - First leader token.
   - Copycat wave.
   - Category rotation.
   - CEX/DEX listing, migration, or external pool creation.

5. **Decay Or Continuation**
   - Narrative exhaustion.
   - Second wave catalysts.
   - Founder/company follow-up.
   - New leader replacing first leader.

## Source Strength

Score each source qualitatively:

- **A: Primary creator**: company, founder, official account, the person/entity the story is about.
- **B: Early interpreter**: account that explains the story before broad market attention.
- **C: Fast deployer**: wallet/project that creates first tradeable token from the story.
- **D: Amplifier**: large account/community that makes late buyers notice.
- **E: Noise/copycat**: late post or low-originality repetition.

## Time Windows

Record these deltas:

- origin event -> token deploy;
- token deploy -> first liquidity;
- first liquidity -> trader's first buy;
- trader's first buy -> first amplifier;
- first amplifier -> price/volume breakout;
- leader token launch -> copycat wave.

Time delta is often the edge. A good report should say whether the trader acted before, during, or after public amplification.

## Questions To Answer

- Was the token born before the narrative was obvious?
- Did the trader buy before the first large amplifier?
- Was there a clear primary source, or only market-invented storytelling?
- Did a company/founder/person provide repeated follow-up catalysts?
- Was this the first token in a category, or just a later copycat?
- Did liquidity/volume confirm attention, or was price only thin-pool movement?

## Output Table

Use columns:

- timestamp_utc
- event_type
- source_url
- source_name
- entity/person/company/project
- token_address
- market_state
- interpretation
- confidence

## Caveats

Social search can miss deleted posts, private groups, edited posts, regional platforms, and screenshots without URLs. Mark those as missing evidence, not negative evidence.
