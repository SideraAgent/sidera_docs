# backtesting

Backtesting evaluates how a strategy would have behaved on historical market data. It is a validation tool, not a prediction engine.

## What a backtest can tell you

A backtest can show:

* Whether the rules are executable.
* How often the strategy trades.
* Whether the average trade survives costs.
* How large drawdowns were historically.
* Whether performance depends on a specific regime.
* Whether the strategy is too sensitive to parameter changes.

## What a backtest cannot tell you

A backtest cannot guarantee:

* Future profitability.
* Future liquidity.
* Future exchange behavior.
* Perfect fills.
* Stable correlations.
* That a strategy is not overfit.

## Required assumptions

Every backtest should document:

| Assumption      | Example                                          |
| --------------- | ------------------------------------------------ |
| Market          | BTC-PERP on a specific venue.                    |
| Timeframe       | 1H, 4H, daily.                                   |
| Data range      | January 2021 to December 2025.                   |
| Fees            | Maker/taker fee assumptions.                     |
| Slippage        | Fixed or liquidity-adjusted slippage assumption. |
| Position sizing | Fixed size, volatility-based, or risk-based.     |
| Leverage        | None, fixed, or capped.                          |
| Reinvestment    | Whether profits compound.                        |

## Core metrics

| Metric                         | Meaning                                |
| ------------------------------ | -------------------------------------- |
| Total return                   | Overall return across the test period. |
| Profit factor                  | Gross profit divided by gross loss.    |
| Maximum drawdown               | Worst peak-to-trough decline.          |
| Win rate                       | Percentage of profitable trades.       |
| Average trade                  | Average PnL per trade after costs.     |
| Sharpe or risk-adjusted return | Return relative to volatility.         |
| Trade count                    | Number of trades in the sample.        |
| Exposure                       | Percentage of time capital is at risk. |

## Backtest red flags

Be careful if:

* Trade count is too low.
* Most profit comes from one trade.
* Small parameter changes destroy performance.
* Fees or slippage are missing.
* Drawdown is larger than you can tolerate.
* The strategy only works in one bull market.
* The strategy trades illiquid assets.
* Results look too smooth.

## Validation workflow

{% stepper %}
{% step %}
### Run a baseline backtest
{% endstep %}

{% step %}
### Add realistic fees and slippage
{% endstep %}

{% step %}
### Test across different market regimes
{% endstep %}

{% step %}
### Change one parameter at a time
{% endstep %}

{% step %}
### Run out-of-sample or more recent period checks
{% endstep %}

{% step %}
### Compare against a simple benchmark
{% endstep %}

{% step %}
### Move to dry-run before live trading
{% endstep %}
{% endstepper %}

## Promotion criteria

A strategy can move from backtest to dry-run when:

* Rules are clear.
* Risk is defined.
* Drawdown is acceptable.
* Cost assumptions are realistic.
* Trade count is meaningful.
* Performance is not obviously overfit.
* RiskGuard limits can be configured for it.
