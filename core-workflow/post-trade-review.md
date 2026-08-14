# Post-trade review

Post-trade review turns Sidera from an execution tool into a learning system. The goal is to improve decision quality, not just count profit and loss.

## When to review

Review after:

- Every live trade during early deployment.
- Every blocked order.
- Every drawdown event.
- Every strategy pause.
- Any trade that violates your expectations.
- Weekly, for active strategies.

## Review questions

Ask these questions after each trade:

| Question | Why it matters |
| --- | --- |
| Was the original thesis clear? | Vague theses create vague execution. |
| Did the entry match the strategy rules? | Prevents accidental discretionary drift. |
| Was the position size correct? | Confirms risk budget discipline. |
| Did RiskGuard behave correctly? | Validates the safety layer. |
| Was execution quality acceptable? | Surfaces slippage, liquidity, and venue issues. |
| Did the exit follow plan? | Separates process quality from outcome luck. |
| What should change? | Converts experience into a better next iteration. |

## Review prompt

Use this prompt with a completed trade:

```text
Review this trade using decision quality, execution quality, and risk discipline. I will provide the thesis, entry, stop, target, order details, and outcome. Identify what was correct, what was lucky, what was wrong, and what should change before the next trade.
```

## Weekly strategy review

For each active strategy, summarize:

- Number of signals.
- Number of orders.
- Orders blocked by RiskGuard.
- Realized and unrealized PnL.
- Maximum drawdown.
- Average slippage.
- Rule violations.
- Market regime notes.
- Recommended action: keep, reduce, pause, revise, or retire.

## Decision quality versus outcome

A profitable trade can be a bad decision, and a losing trade can be a good decision. Judge both:

| Decision quality | Outcome | Interpretation |
| --- | --- | --- |
| Good | Profit | Reinforce the process, but avoid overconfidence. |
| Good | Loss | Accept the loss if rules were followed. |
| Poor | Profit | Treat as a warning. Profit from bad process is dangerous. |
| Poor | Loss | Fix the process before trading again. |

