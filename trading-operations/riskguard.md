# riskguard

RiskGuard is Sidera's deterministic pre-trade risk engine. It checks whether an order is allowed before it reaches the exchange.

The key principle is simple: AI may generate ideas, but hard risk rules must decide whether an order is permitted.

## What RiskGuard checks

RiskGuard can enforce:

* Maximum position size.
* Per-trade risk.
* Daily drawdown limits.
* Stop-loss requirements.
* Leverage caps.
* Venue restrictions.
* Strategy permissions.
* Market anomaly checks.
* Portfolio exposure limits.

## Deterministic rules

RiskGuard should be treated as a rule engine, not an opinion engine. If a user-defined hard limit is violated, the order should be blocked even if the AI's current analysis sounds confident.

| Rule                                           | Result                                                  |
| ---------------------------------------------- | ------------------------------------------------------- |
| Maximum BTC position is 10% of account equity. | A 15% BTC order is blocked.                             |
| Maximum daily drawdown is 3%.                  | New entries are blocked after the threshold is reached. |
| Every live strategy must define a stop.        | A strategy without stop logic cannot go live.           |
| Maximum leverage is 3x.                        | A 5x order is blocked.                                  |

## RiskGuard status

RiskGuard status should be visible before live trading:

* Overall pass or fail.
* Number of active rules.
* Any warnings.
* Any high-risk flags.
* The specific rule that blocked an order.

## Blocked order review

{% stepper %}
{% step %}
## Which rule failed

Identify the specific rule that blocked the order.
{% endstep %}

{% step %}
## Review the strategy

Determine whether the strategy should be changed.
{% endstep %}

{% step %}
## Keep or review the risk limit

Determine whether the risk limit should remain unchanged.
{% endstep %}

{% step %}
## Consider market conditions

Review whether market conditions have changed.
{% endstep %}

{% step %}
## Resize or delay the order

Determine whether the order can be resized or delayed.
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Do not loosen risk rules just to force a trade through. If a rule repeatedly blocks a strategy, the strategy may be mismatched to the account, venue, or market regime.
{% endhint %}
