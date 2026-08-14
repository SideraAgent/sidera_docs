# Key concepts

## Research Copilot

The market research layer. It helps traders scan opportunities, compare assets, build theses, and identify risks.

## Strategy Forge

The strategy engineering layer. It turns natural-language ideas into executable logic, backtests strategies, and prepares them for deployment.

## Smart Execution

The execution layer. It checks market conditions, risk constraints, venue readiness, and order details before placing trades.

## Risk Sentinel

The monitoring layer. It watches strategies and positions after execution, sends alerts, and can support intervention workflows.

## RiskGuard

The deterministic pre-trade rule engine. It blocks orders that violate hard user-defined limits.

## Dry-run

A non-live mode for testing strategy behavior, alerts, logs, and execution logic without placing real exchange orders.

## Live trading

The mode where approved orders can be submitted to connected venues. Live trading should only be enabled after credentials, permissions, and risk limits are reviewed.

## Invalidation

The condition that proves a trade thesis wrong. A strong thesis always includes invalidation before execution.

## Risk budget

The amount of capital or account equity a trader is willing to risk on a trade, strategy, or portfolio segment.

## Strategy allocation

The maximum capital a strategy is allowed to control.

## Decision log

A record of why Sidera generated, approved, blocked, or executed a trading action.

