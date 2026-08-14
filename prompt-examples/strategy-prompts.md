# Strategy prompts

Use strategy prompts after research has produced a clear thesis. A good strategy prompt turns an idea into rules that can be backtested, dry-run, and reviewed.

## Thesis to strategy

```text
Convert this thesis into a rules-based strategy.

Market: [ASSET / VENUE]
Timeframe: [TIMEFRAME]
Thesis: [PASTE THESIS]
Risk limit: Maximum [X]% account risk per trade.

Define:
- Entry conditions
- Exit conditions
- Stop-loss logic
- Take-profit logic
- Position sizing
- No-trade conditions
- Market regime assumptions
- Backtest requirements
- RiskGuard requirements

Return the result as a strategy specification that can be implemented and tested.
```

## Momentum strategy

```text
Build a momentum strategy for [ASSET] using [TIMEFRAME] candles.

Rules:
- Enter only when trend and volume confirm.
- Avoid entries after overextended moves.
- Define a stop based on structure or volatility.
- Take profit using either fixed R multiple or trailing logic.
- Risk no more than [X]% per trade.
- Avoid trading during abnormal funding or illiquidity.

Include backtest assumptions and expected failure modes.
```

## Mean-reversion strategy

```text
Build a mean-reversion strategy for [ASSET].

Define:
- Conditions that identify overextension
- Entry trigger
- Mean target
- Stop-loss if reversion fails
- Maximum holding time
- Volatility filter
- No-trade conditions during trend breakout

Explain when this strategy should be paused.
```

## Breakout strategy

```text
Create a breakout strategy for [ASSET] on [TIMEFRAME].

Include:
- Range definition
- Breakout confirmation
- Volume or volatility filter
- False-breakout protection
- Entry method
- Stop placement
- Profit-taking plan
- Risk per trade
- Conditions where breakout trades should be avoided
```

## Hedge strategy

```text
Design a hedge strategy for a long-biased crypto portfolio.

Portfolio context:
- Main holdings: [LIST]
- Current exposure: [EXPOSURE]
- Max acceptable drawdown: [LIMIT]

Compare:
- Reducing spot exposure
- Short perps
- Options if available
- Cross-asset hedge
- Stablecoin rotation

Return a practical hedge plan with triggers, size, cost, and unwind conditions.
```

## Strategy improvement

```text
Review this strategy and improve it without overfitting.

Strategy rules:
[PASTE RULES]

Backtest summary:
[PASTE METRICS]

Identify:
- Biggest weakness
- Likely overfit parameters
- Missing risk controls
- Missing no-trade conditions
- One conservative improvement
- One aggressive improvement

Only recommend changes that can be tested clearly.
```

