# configure risk limits

Risk limits define the boundaries within which Sidera can operate. They are not optional polish; they are the control layer that keeps AI-assisted trading from becoming open-ended automation.

Sidera's risk system is centered on **RiskGuard**, a deterministic pre-trade rule engine. RiskGuard checks orders before execution and blocks actions that violate configured limits.

## Core limits

Set these limits before live trading:

| Limit                  | Description                                          | Example                                               |
| ---------------------- | ---------------------------------------------------- | ----------------------------------------------------- |
| ---                    | ---                                                  | ---                                                   |
| Maximum position size  | Caps the total exposure for a market or strategy.    | No single BTC position above 15% of account equity.   |
| Per-trade risk         | Limits the amount you can lose if the stop is hit.   | Risk no more than 1% per trade.                       |
| Daily drawdown ceiling | Stops new trading after a loss threshold.            | Pause all strategies after 3% daily drawdown.         |
| Stop-loss requirement  | Requires every live strategy to define invalidation. | No live order without a stop or equivalent risk exit. |
| Leverage cap           | Limits liquidation and volatility risk.              | Maximum 3x leverage for discretionary trades.         |
| Strategy allocation    | Caps how much capital a strategy can control.        | Strategy A may use up to 20% of available capital.    |

## Suggested default setup

For a first live strategy, use conservative settings:

* Per-trade risk: 0.25% to 1.00% of account equity.
* Maximum daily drawdown: 2% to 3%.
* Maximum strategy allocation: 10% to 20% of account equity.
* Leverage: no leverage or low leverage until execution behavior is proven.
* Alerts: enabled for entry, exit, blocked order, drawdown warning, and forced pause.

## RiskGuard approval flow

Before an order is submitted, Sidera should check:

{% stepper %}
{% step %}
## Whether the strategy is allowed to trade
{% endstep %}

{% step %}
## Whether the market is supported by the connected venue
{% endstep %}

{% step %}
## Whether account balance and margin are sufficient
{% endstep %}

{% step %}
## Whether the order respects position, leverage, and drawdown limits
{% endstep %}

{% step %}
## Whether market conditions are abnormal, illiquid, or outside the strategy's intended regime
{% endstep %}

{% step %}
## Whether required stops, exits, or intervention rules are present
{% endstep %}

{% step %}
## Whether the decision is logged for review
{% endstep %}
{% endstepper %}

If any required check fails, the order should be blocked or returned for user review.

## Portfolio-level risk

Single-trade limits are not enough. Configure portfolio-level rules when running multiple strategies:

* Maximum correlated exposure across related assets.
* Maximum total leverage across all strategies.
* Maximum open positions.
* Maximum exposure to one venue.
* Emergency pause rule if market volatility exceeds a defined threshold.
* Emergency pause rule if exchange connectivity becomes unstable.

## Intervention permissions

Risk Sentinel can support different intervention levels. Choose the level that matches your trust and experience.

| Permission level | Behavior                                                           |
| ---------------- | ------------------------------------------------------------------ |
| Alert only       | Sidera notifies you but does not change positions.                 |
| Pause strategy   | Sidera can stop new orders from a strategy.                        |
| Hedge            | Sidera can open protective exposure according to predefined rules. |
| Force-exit       | Sidera can close positions when severe risk rules trigger.         |

{% hint style="info" %}
Start with alert-only or pause permissions before allowing hedge or force-exit automation.
{% endhint %}
