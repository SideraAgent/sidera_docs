# Prompt playbooks

Prompt playbooks are reusable workflows. Use them when you want Sidera to follow a consistent research, strategy, or review process.

## Market scan playbook

Use when deciding what to focus on today.

```text
Run a market scan for BTC, ETH, SOL, and the highest-liquidity altcoin opportunities. Rank them for the next 24-72 hours using trend, liquidity, volatility, catalysts, derivatives positioning, and downside risk. For each market, provide bull case, bear case, invalidation level, and whether it is suitable for strategy testing.
```

Expected output:

- Ranked opportunity list.
- Evidence quality.
- Tradeability score.
- Key levels.
- Risks.
- Next action.

## Thesis-to-strategy playbook

Use after a research answer looks promising.

```text
Convert this thesis into a rules-based strategy. Define market, timeframe, entry trigger, exit logic, stop-loss, take-profit, position sizing, no-trade conditions, and RiskGuard requirements. Then list what needs to be backtested before dry-run deployment.
```

Expected output:

- Strategy specification.
- Assumptions.
- Risk rules.
- Backtest plan.
- Deployment checklist.

## Backtest review playbook

Use after a strategy backtest.

```text
Review this backtest as if deciding whether to move it to dry-run. Evaluate return quality, drawdown, trade count, fee sensitivity, slippage sensitivity, regime dependence, overfitting risk, and the exact changes needed before deployment.
```

Expected output:

- Pass or fail recommendation.
- Key weaknesses.
- Required changes.
- Dry-run readiness.

## Live readiness playbook

Use before enabling live trading.

```text
Perform a live-readiness review for this strategy. Check strategy rules, backtest quality, dry-run behavior, exchange setup, RiskGuard limits, portfolio exposure, alert coverage, and rollback rules. Tell me whether live trading should remain disabled, start with minimum size, or be rejected.
```

Expected output:

- Live readiness status.
- Blockers.
- Minimum viable live settings.
- Rollback conditions.

## Post-trade review playbook

Use after trade completion.

```text
Review this completed trade. Separate process quality from PnL outcome. Evaluate thesis quality, entry quality, sizing, RiskGuard behavior, execution quality, exit quality, and what should change next time.
```

Expected output:

- Good decisions.
- Bad decisions.
- Lucky/unlucky factors.
- Rule changes.
- Next-trade instructions.

