# execution prompts

Use execution prompts before a live order or dry-run deployment. These prompts help verify that the trade is still valid at the moment of action.

## Pre-order check

```
Before placing this order, perform a full execution check.

Order:
- Market: [ASSET]
- Direction: [LONG / SHORT]
- Entry type: [MARKET / LIMIT / TWAP]
- Size: [SIZE]
- Stop: [STOP]
- Target: [TARGET]
- Venue: [VENUE]

Check:
- Thesis still valid
- Invalidation not breached
- Liquidity
- Estimated slippage
- Funding or market stress
- RiskGuard approval
- Position size
- Venue availability
- Whether execution should proceed, wait, resize, or cancel
```

## Dry-run deployment check

```
Prepare this strategy for dry-run deployment.

Check whether the following are complete:
- Entry rules
- Exit rules
- Stop logic
- Position sizing
- RiskGuard limits
- No-trade conditions
- Alert rules
- Decision logs
- Review plan

If anything is missing, return a blocker list before deployment.
```

## Live pilot setup

```
Create a minimum-size live pilot plan for this strategy.

Include:
- Initial capital allocation
- Max position size
- Max daily drawdown
- Leverage cap
- Alert settings
- Manual review requirements
- Rollback conditions
- Number of trades required before scaling
```

## Slippage and liquidity review

```
Review execution quality for this planned order.

Market: [ASSET]
Venue: [VENUE]
Order size: [SIZE]
Order type: [TYPE]

Evaluate:
- Order book depth
- Spread
- Expected slippage
- Whether to use market, limit, or sliced execution
- Whether size should be reduced
- Best execution plan
```

## Emergency action prompt

```
Evaluate whether this position requires emergency action.

Position:
[PASTE POSITION]

Current market change:
[PASTE CONTEXT]

Check:
- Invalidation level
- Drawdown
- Liquidity
- Funding
- News or event risk
- Venue stability

Recommend one action: hold, reduce, hedge, pause strategy, or force-exit. Explain the tradeoff.
```
