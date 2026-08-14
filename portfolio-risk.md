# portfolio risk

Portfolio risk is the combined risk across all positions, strategies, venues, and market exposures. A single trade may look safe while the full portfolio is overloaded.

## Why portfolio risk matters

Multiple strategies can accidentally create the same exposure.

Example:

* Strategy A is long BTC.
* Strategy B is long ETH.
* Strategy C is long SOL.
* A discretionary trade is long a high-beta altcoin.

Each trade may respect its own risk limit, but the portfolio may be strongly exposed to one broad crypto market move.

## Portfolio controls

Configure controls for:

| Control            | Purpose                                            |
| ------------------ | -------------------------------------------------- |
| Total exposure cap | Limits total capital at risk.                      |
| Correlation cap    | Prevents too many similar positions.               |
| Venue cap          | Limits exposure to one exchange or venue.          |
| Strategy cap       | Prevents one strategy from dominating the account. |
| Drawdown cap       | Stops trading after portfolio losses.              |
| Leverage cap       | Limits total leveraged exposure.                   |
| Emergency pause    | Stops all new entries under severe conditions.     |

## Stress testing

Ask Sidera to stress test scenarios:

```
Stress test my portfolio if BTC drops 5%, 10%, and 20%. Estimate portfolio drawdown, identify the largest contributors, and suggest which exposures should be reduced first.
```

Run stress tests before:

* Increasing allocation.
* Adding a correlated strategy.
* Trading during major news.
* Holding positions through illiquid periods.
* Enabling higher leverage.

## Correlation review

Review whether strategies are truly independent. Strategies may look different but still depend on the same factor:

* Broad crypto beta.
* Momentum.
* Liquidity expansion.
* Funding rates.
* Volatility compression.
* USD liquidity or macro risk.

## Portfolio review cadence

For active users:

* Daily: exposure, drawdown, open positions, urgent risks.
* Weekly: strategy performance, correlation, venue risk, blocked orders.
* Monthly: allocation changes, retired strategies, limit adjustments.
