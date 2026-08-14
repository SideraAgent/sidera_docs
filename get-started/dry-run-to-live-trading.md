# Dry-run to live trading

Moving from dry-run to live trading is a controlled release process. Treat it the way an engineering team treats production deployment: test first, limit blast radius, observe closely, and roll back quickly if behavior is wrong.

## Stage 1: Research-only

Use Sidera without exchange credentials.

Goals:

- Understand Research Copilot output.
- Build market theses.
- Learn prompt patterns.
- Save useful research.
- Avoid any execution risk.

Completion criteria:

- You can explain the thesis in your own words.
- You know what would invalidate the idea.
- You have not relied on one AI answer without verification.

## Stage 2: Strategy and backtest

Use Strategy Forge and Strategy Lab.

Goals:

- Convert theses into rules.
- Run backtests.
- Compare iterations.
- Reject weak strategies.
- Understand drawdown behavior.

Completion criteria:

- Strategy has explicit entry and exit rules.
- Backtest includes realistic fees and slippage.
- Drawdown is acceptable.
- Strategy behavior is understandable.

## Stage 3: Dry-run

Deploy the strategy without live orders.

Goals:

- Observe live signal behavior.
- Confirm logs and alerts.
- Verify RiskGuard checks.
- Confirm the strategy does not overtrade.
- Compare simulated entries against market conditions.

Completion criteria:

- Dry-run signals match intended rules.
- RiskGuard blocks invalid actions.
- Alerts work.
- Logs are reviewable.
- No unexpected behavior appears for a meaningful test period.

## Stage 4: Limited live pilot

Enable live trading with minimum practical size.

Controls:

- Small strategy allocation.
- Low or no leverage.
- Tight daily drawdown cap.
- Mandatory stop logic.
- Manual review of first orders.
- Real-time alert monitoring.

Completion criteria:

- Orders match dry-run behavior.
- Slippage is acceptable.
- RiskGuard works in live mode.
- You can pause or close quickly.
- The strategy behaves consistently across multiple trades.

## Stage 5: Scaled live operation

Increase allocation only after the limited pilot is stable.

Before scaling:

- Recheck venue liquidity.
- Review drawdown tolerance.
- Confirm portfolio-level exposure.
- Confirm strategy correlation with existing positions.
- Review support and incident procedures.

## Rollback rules

Pause or disable live trading if:

- Strategy behavior differs from dry-run.
- RiskGuard warnings are not understood.
- Slippage exceeds expectations.
- Exchange connectivity becomes unstable.
- Drawdown approaches the daily limit.
- Market conditions no longer match the strategy.
- You cannot monitor urgent alerts.

