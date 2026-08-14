# review prompts

Use review prompts after trades, strategy runs, blocked orders, or weekly performance reviews. The goal is to improve the system, not to rationalize outcomes.

## Completed trade review

```
Review this completed trade.

I will provide:
- Original thesis
- Entry
- Stop
- Target
- Position size
- Execution details
- Exit
- Outcome

Evaluate:
- Thesis quality
- Entry quality
- Position sizing
- Risk discipline
- Execution quality
- Exit quality
- What was skill
- What was luck
- What should change next time
```

## Strategy cycle review

```
Review this strategy cycle.

Strategy:
[NAME]

Period:
[DATES]

Data:
- Signals
- Orders
- Blocked orders
- PnL
- Drawdown
- Slippage
- Rule violations
- Market regime

Return:
- Keep, reduce, pause, revise, or retire
- Main reason
- Required changes
- Next test plan
```

## Blocked order review

```
Review this RiskGuard-blocked order.

Blocked order:
[PASTE DETAILS]

RiskGuard result:
[PASTE RESULT]

Explain:
- Which rule blocked it
- Whether the block was correct
- Whether the strategy should be changed
- Whether the risk rule should remain unchanged
- Whether a smaller or delayed order would be acceptable
```

## Weekly trading review

```
Create a weekly trading review.

Inputs:
- Trades taken
- Strategies active
- PnL
- Drawdown
- Blocked orders
- Best decision
- Worst decision
- Missed opportunities
- Emotional or discipline issues

Output:
- Summary
- What worked
- What failed
- Risk issues
- Strategy changes
- Next week's focus markets
- Rules to follow next week
```

## Decision quality review

```
Separate decision quality from outcome for this trade.

Trade:
[PASTE DETAILS]

Classify the trade as:
- Good decision / good outcome
- Good decision / bad outcome
- Bad decision / good outcome
- Bad decision / bad outcome

Explain why, and recommend one rule to improve future decisions.
```
