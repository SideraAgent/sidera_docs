# strategy forge

Strategy Forge converts trading ideas into executable strategy logic. It is designed for traders who can describe what they want in plain English, but do not want to manually write, test, and deploy every line of code.

## What Strategy Forge does

Strategy Forge can help with:

* Translating natural-language rules into code.
* Creating strategy metadata.
* Running backtests.
* Iterating on strategy logic.
* Comparing results.
* Preparing strategies for live deployment.
* Importing existing code through a Strategy SDK where available.

## Strategy request format

The best Strategy Forge prompts include six elements:

| Element       | Example                                                                             |
| ------------- | ----------------------------------------------------------------------------------- |
| Market        | SOL perpetuals on Hyperliquid.                                                      |
| Timeframe     | 4-hour candles.                                                                     |
| Entry rule    | Enter long when price breaks above the 20-period moving average and volume expands. |
| Exit rule     | Take profit at 2R or exit when momentum weakens.                                    |
| Risk rule     | Risk no more than 1% of account equity per trade.                                   |
| No-trade rule | Avoid trading during extreme funding spikes or low liquidity.                       |

Example:

```
Build a 4-hour SOL momentum strategy. Enter long when price closes above the 20-period moving average with volume expansion. Risk 1% per trade, stop below the last swing low, take profit at 2R, and avoid entries when funding is extremely positive.
```

## Backtesting

After strategy generation, run a backtest before deployment.

Review:

* Number of trades.
* Win rate.
* Profit factor.
* Maximum drawdown.
* Average win and average loss.
* Worst losing streak.
* Performance after fees and slippage.
* Performance across bull, bear, and sideways regimes.

{% hint style="warning" %}
A profitable backtest does not guarantee future performance. It only shows how the rules behaved on historical data under the chosen assumptions.
{% endhint %}

## Iteration process

{% stepper %}
{% step %}
## Define the first version
{% endstep %}

{% step %}
## Run a baseline backtest
{% endstep %}

{% step %}
## Identify the main weakness
{% endstep %}

{% step %}
## Change one variable at a time
{% endstep %}

{% step %}
## Compare the new version against the baseline
{% endstep %}

{% step %}
## Reject changes that improve returns but create unacceptable drawdown or overfitting risk
{% endstep %}

{% step %}
## Promote only stable versions to dry-run or live testing
{% endstep %}
{% endstepper %}

## Deployment readiness

A strategy is not ready for live trading until it has:

* Clear entry and exit rules.
* A stop-loss or equivalent risk exit.
* Defined position sizing.
* Realistic fee and slippage assumptions.
* Acceptable drawdown.
* Enough trade samples to be meaningful.
* RiskGuard limits configured.
* Monitoring and intervention rules enabled.

## Importing existing logic

If you already have strategy logic, you can use Strategy Forge as an execution and validation layer rather than an idea generator.

Typical flow:

{% stepper %}
{% step %}
## Import the existing code

Import the existing code through the available Strategy SDK or supported strategy interface.
{% endstep %}

{% step %}
## Add metadata

Add metadata: market, timeframe, assumptions, risk rules, and intended venue.
{% endstep %}

{% step %}
## Run a backtest

Run a backtest inside Sidera.
{% endstep %}

{% step %}
## Compare output

Compare output with your original environment.
{% endstep %}

{% step %}
## Deploy

Deploy only after behavior is consistent and RiskGuard rules are active.
{% endstep %}
{% endstepper %}
