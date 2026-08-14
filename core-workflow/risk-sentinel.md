# risk sentinel

Risk Sentinel monitors positions, strategies, and portfolio risk after execution. It exists because trading risk does not end when an order is placed.

Markets move continuously. A strategy can be valid at entry and invalid later. Liquidity can disappear, volatility can expand, and human attention can fail. Risk Sentinel is designed to keep watch and escalate when action is needed.

## What Risk Sentinel monitors

Risk Sentinel should monitor:

* Open positions.
* Strategy status.
* Stop-loss and take-profit levels.
* Daily drawdown.
* Portfolio exposure.
* Market volatility.
* Funding and derivatives positioning.
* News or event risk.
* Exchange connectivity.
* Unusual execution or order behavior.

## Alerts

Configure alerts for:

| Alert            | Trigger                                               |
| ---------------- | ----------------------------------------------------- |
| Position opened  | A live order creates exposure.                        |
| Position closed  | A strategy exits or a manual close occurs.            |
| Stop approaching | Price moves near the invalidation level.              |
| Drawdown warning | Loss approaches the configured threshold.             |
| RiskGuard block  | An order is blocked by risk rules.                    |
| Venue issue      | Exchange connectivity or market availability changes. |
| Strategy pause   | Sidera pauses a strategy due to risk or user action.  |

## Intervention levels

Risk Sentinel can support multiple levels of intervention.

| Level  | Description                                   |
| ------ | --------------------------------------------- |
| Notify | Send alerts only.                             |
| Pause  | Stop new orders from a strategy.              |
| Hedge  | Place predefined protective exposure.         |
| Close  | Exit a position under severe risk conditions. |

{% hint style="info" %}
For new users, start with **Notify** and **Pause**. Enable **Hedge** or **Close** only after you fully understand the rules and have tested them in dry-run mode.
{% endhint %}

## Example rule set

```
If BTC drops below the invalidation level, pause the strategy and send an urgent alert.
If account drawdown reaches 2% in one day, block new entries for all strategies.
If exchange connectivity fails, cancel pending entries and notify me.
If slippage exceeds the configured threshold, block the order and request review.
```

## Review after alerts

Every alert should produce a reviewable record:

* What triggered the alert.
* Which strategy or position was affected.
* Whether Sidera notified, paused, hedged, or closed.
* Whether the action followed configured rules.
* Whether the rule should be changed.
