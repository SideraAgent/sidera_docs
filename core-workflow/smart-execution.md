# smart execution

Smart Execution is Sidera's execution layer. It is designed to place trades only after the strategy, market context, and risk rules are checked.

Sidera execution is not just order routing. A professional execution workflow should verify whether the order still makes sense at the moment it is about to be placed.

## Pre-trade checks

Before submitting an order, Smart Execution should check:

| Check               | Purpose                                                                          |
| ------------------- | -------------------------------------------------------------------------------- |
| ---                 | ---                                                                              |
| Strategy permission | Confirms the strategy is allowed to trade live.                                  |
| RiskGuard approval  | Enforces position, leverage, drawdown, and stop-loss rules.                      |
| Market regime       | Checks whether current conditions match the strategy assumptions.                |
| Liquidity           | Estimates whether the order can be filled without excessive slippage.            |
| Venue availability  | Confirms exchange connectivity and market availability.                          |
| Order type          | Confirms whether market, limit, reduce-only, or sliced execution is appropriate. |
| Decision logging    | Records why the order was placed or blocked.                                     |

## Order planning

For each order, define:

* Market.
* Direction.
* Entry type.
* Position size.
* Stop level.
* Target or exit logic.
* Maximum slippage.
* Time-in-force.
* Venue.
* Strategy ID or manual decision reason.

Example:

```
Prepare a BTC long order only if liquidity is normal, slippage is below 0.15%, RiskGuard approves the size, and BTC remains above the invalidation level from the research thesis.
```

## Execution styles

Sidera may support different execution styles depending on venue and product availability.

| Style                                    | Best for                                        | Main risk                                 |
| ---------------------------------------- | ----------------------------------------------- | ----------------------------------------- |
| Market order                             | Fast entry or exit.                             | Slippage.                                 |
| Limit order                              | Price-controlled entry.                         | Missed fill.                              |
| Reduce-only order                        | Closing or reducing exposure.                   | Incorrect position state if not verified. |
| Sliced execution or TWAP-style execution | Larger orders that should reduce market impact. | Partial fills and execution drift.        |

## Blocked orders

An order should be blocked if:

* It violates maximum position size.
* It exceeds leverage limits.
* It would breach daily drawdown rules.
* Required stop-loss logic is missing.
* The venue is unavailable.
* Liquidity or slippage is outside acceptable range.
* The market has moved beyond the thesis invalidation level.
* The strategy is paused or not authorized for live trading.

## Execution review

After an order is placed, review:

* Requested price versus average fill price.
* Slippage.
* Fees.
* Whether the order matched the strategy rules.
* Whether any risk warnings appeared.
* Whether the position was monitored correctly after entry.
