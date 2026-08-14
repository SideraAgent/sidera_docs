# Strategy Forge

Strategy Forge converts trading ideas into executable strategy logic. It is designed for traders who can describe what they want in plain English, but do not want to manually write, test, and deploy every line of code.

## What Strategy Forge does

Strategy Forge can help with:

- Translating natural-language rules into code.
- Creating strategy metadata.
- Running backtests.
- Iterating on strategy logic.
- Comparing results.
- Preparing strategies for live deployment.
- Importing existing code through a Strategy SDK where available.

## Strategy request format

The best Strategy Forge prompts include six elements:

| Element | Example |
| --- | --- |
| Market | SOL perpetuals on Hyperliquid. |
| Timeframe | 4-hour candles. |
| Entry rule | Enter long when price breaks above the 20-period moving average and volume expands. |
| Exit rule | Take profit at 2R or exit when momentum weakens. |
| Risk rule | Risk no more than 1% of account equity per trade. |
| No-trade rule | Avoid trading during extreme funding spikes or low liquidity. |

Example:

```text
Build a 4-hour SOL momentum strategy. Enter long when price closes above the 20-period moving average with volume expansion. Risk 1% per trade, stop below the last swing low, take profit at 2R, and avoid entries when funding is extremely positive.
```

## Backtesting

After strategy generation, run a backtest before deployment.

Review:

- Number of trades.
- Win rate.
- Profit factor.
- Maximum drawdown.
- Average win and average loss.
- Worst losing streak.
- Performance after fees and slippage.
- Performance across bull, bear, and sideways regimes.

{% hint style="warning" %}
A profitable backtest does not guarantee future performance. It only shows how the rules behaved on historical data under the chosen assumptions.
{% endhint %}

## Iteration process

Use a disciplined iteration loop:

1. Define the first version.
2. Run a baseline backtest.
3. Identify the main weakness.
4. Change one variable at a time.
5. Compare the new version against the baseline.
6. Reject changes that improve returns but create unacceptable drawdown or overfitting risk.
7. Promote only stable versions to dry-run or live testing.

## Deployment readiness

A strategy is not ready for live trading until it has:

- Clear entry and exit rules.
- A stop-loss or equivalent risk exit.
- Defined position sizing.
- Realistic fee and slippage assumptions.
- Acceptable drawdown.
- Enough trade samples to be meaningful.
- RiskGuard limits configured.
- Monitoring and intervention rules enabled.

## Importing existing logic

If you already have strategy logic, you can use Strategy Forge as an execution and validation layer rather than an idea generator.

Typical flow:

1. Import the existing code through the available Strategy SDK or supported strategy interface.
2. Add metadata: market, timeframe, assumptions, risk rules, and intended venue.
3. Run a backtest inside Sidera.
4. Compare output with your original environment.
5. Deploy only after behavior is consistent and RiskGuard rules are active.

