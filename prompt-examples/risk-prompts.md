# Risk prompts

Use risk prompts before sizing trades, running multiple strategies, or enabling live trading. Risk prompts should make Sidera conservative and explicit.

## Position sizing

```text
Design a position-sizing plan for this trade.

Account size: [AMOUNT]
Market: [ASSET]
Entry: [PRICE]
Stop: [PRICE]
Targets: [PRICE LEVELS]
Maximum risk: [X]% of account equity
Leverage limit: [LIMIT]

Calculate:
- Dollar risk
- Position size
- Risk/reward
- Maximum loss if stop is hit
- Slippage sensitivity
- Whether the trade fits the risk budget
```

## Portfolio stress test

```text
Stress test my portfolio under three scenarios:

1. BTC drops 5%.
2. BTC drops 10%.
3. BTC drops 20%.

Portfolio:
[PASTE POSITIONS]

Estimate:
- Approximate portfolio drawdown
- Largest contributors to loss
- Correlated exposures
- Positions to reduce first
- Whether any strategy should be paused
- Emergency RiskGuard rules to activate
```

## Multi-strategy risk plan

```text
Design a risk plan for running multiple strategies at once.

Strategies:
[LIST STRATEGIES]

Define:
- Per-strategy allocation
- Maximum total exposure
- Daily drawdown ceiling
- Correlation limits
- Venue exposure limits
- Leverage cap
- Emergency pause rules
- Alert thresholds
```

## Pre-live risk review

```text
Perform a pre-live risk review for this strategy.

Strategy:
[PASTE STRATEGY]

Backtest:
[PASTE METRICS]

Dry-run logs:
[PASTE SUMMARY]

Check:
- Max position size
- Per-trade risk
- Daily drawdown limit
- Stop-loss logic
- Leverage
- Venue risk
- Portfolio correlation
- Alert coverage

End with one of three decisions: not ready, minimum-size pilot, or approved for limited live test.
```

## RiskGuard configuration

```text
Recommend RiskGuard settings for this strategy.

Strategy type: [TYPE]
Market: [ASSET]
Timeframe: [TIMEFRAME]
Expected trade frequency: [FREQUENCY]
Account risk tolerance: [LOW / MEDIUM / HIGH]

Return:
- Max position size
- Max per-trade risk
- Daily drawdown stop
- Leverage cap
- Stop-loss requirement
- Slippage limit
- No-trade conditions
- Emergency pause rules
```

