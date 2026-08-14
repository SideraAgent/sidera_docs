# About Sidera

Sidera is an AI research and trading workspace for active market participants. It helps traders move from market research to strategy design, execution, and risk monitoring inside one closed workflow.

Instead of treating AI as a standalone chat assistant, Sidera connects analysis, backtesting, live execution, deterministic risk checks, and post-trade review. The product is built around four core modules:

- **Research Copilot** for market intelligence, cited research, signal discovery, and thesis development.
- **Strategy Forge** for turning natural-language trading ideas into executable strategy logic.
- **Smart Execution** for placing trades only after market, liquidity, and risk conditions are checked.
- **Risk Sentinel** for 24/7 portfolio monitoring, alerts, and intervention workflows.

Sidera is designed for traders who already have hypotheses, watchlists, or strategy ideas, but need a better system for validating and executing them without losing context between separate tools.

{% hint style="warning" %}
Sidera provides research, automation, and execution tooling. It does not provide financial advice. AI output can be wrong, market data can be delayed or incomplete, and all trading involves risk. Always verify important information before trading.
{% endhint %}

## Why Sidera

Most trading workflows are fragmented. A trader may research in one product, chart in another, backtest elsewhere, execute on an exchange, manage alerts through separate apps, and manually write down what happened afterward. Each handoff creates delay, lost context, and operational risk.

Sidera is built to close that loop.

| Workflow problem | How Sidera addresses it |
| --- | --- |
| Market research is scattered across charts, news, social feeds, on-chain dashboards, and AI chat. | Research Copilot gathers multi-source context and turns it into a clear, inspectable thesis. |
| Strategy building requires code, infrastructure, or repeated manual testing. | Strategy Forge converts plain-language strategy ideas into code, backtests them, and prepares them for deployment. |
| Execution tools are mechanical and do not understand the original thesis or risk budget. | Smart Execution checks regime, liquidity, anomaly signals, and user-defined limits before placing orders. |
| Risk management depends too much on human discipline and constant screen time. | Risk Sentinel monitors positions and can alert, pause, hedge, or close according to configured rules. |
| Post-trade learning is often inconsistent. | Sidera records reasoning, risk checks, execution traces, and outcomes so decisions can be reviewed. |

## Who Sidera is for

Sidera is useful for several types of traders.

### Discretionary traders

Use Sidera to research market opportunities, form a long or short thesis, define invalidation levels, size the trade, and monitor the position after entry.

Typical questions:

- What is the bull case and bear case for SOL this week?
- Which markets show volatility expansion and unusual volume?
- What levels would invalidate this BTC long thesis?
- How should I size this trade if I only want to risk 1% of account equity?

### Systematic and strategy-driven traders

Use Strategy Forge to convert rules into code, run backtests, compare iterations, and deploy selected strategies with risk boundaries.

Typical tasks:

- Build a 4-hour momentum strategy on SOL with a 2% risk limit per trade.
- Backtest a mean-reversion strategy across multiple market regimes.
- Import existing strategy logic through the Strategy SDK and deploy it inside Sidera's execution environment.
- Compare win rate, profit factor, drawdown, and trade frequency before going live.

### Crypto-native traders

Use Sidera for fast-moving crypto markets where on-chain activity, social momentum, derivatives positioning, and exchange liquidity can change quickly.

Sidera initially focuses on exchange connectivity such as Binance and Hyperliquid, with more venues expected to depend on user demand and product roadmap.

### Busy operators and part-time traders

Use Sidera to keep a trading plan active when you are not watching the screen. Risk Sentinel can monitor positions and trigger alerts across configured channels, while your hard risk rules remain enforced by RiskGuard.

## What Sidera can do

| Area | Capabilities |
| --- | --- |
| Research | Market scan, thesis generation, cited analysis, catalyst review, on-chain and sentiment context, watchlist planning. |
| Strategy | Natural-language strategy authoring, code generation, backtesting, strategy metadata, iteration review, deployment preparation. |
| Execution | Pre-trade validation, venue routing, order checks, risk budget enforcement, decision logging. |
| Risk | Position limits, stop-loss thresholds, drawdown ceilings, anomaly checks, portfolio monitoring, intervention alerts. |
| Review | Reasoning traces, risk check outcomes, order history, backtest results, post-trade improvement notes. |

## Core workflow

The Sidera workflow is intentionally sequential:

1. **Research the opportunity.** Ask Sidera to scan markets, explain catalysts, compare long and short cases, and identify key risks.
2. **Build the strategy.** Convert the thesis into rules, triggers, invalidation levels, and risk sizing.
3. **Validate before execution.** Backtest the strategy and inspect whether it behaves well across market regimes.
4. **Execute with controls.** Use Smart Execution only after RiskGuard and user-defined limits are satisfied.
5. **Monitor continuously.** Let Risk Sentinel watch the position and notify or intervene according to configured permissions.
6. **Review the outcome.** Use logs, reasoning traces, and execution records to improve the next decision.

## Documentation map

If you are new to Sidera, start with:

- [Create your account](get-started/create-your-account.md)
- [Connect exchanges](get-started/connect-exchanges.md)
- [Core workflow](introduction/core-workflow.md)

If you want to understand the product modules, read:

- [Research Copilot](core-workflow/research-copilot.md)
- [Strategy Forge](core-workflow/strategy-forge.md)
- [Smart Execution](core-workflow/smart-execution.md)
- [Risk Sentinel](core-workflow/risk-sentinel.md)

If you are preparing to trade live, read:

- [RiskGuard](trading-operations/riskguard.md)
- [Exchanges and venues](trading-operations/exchanges-and-venues.md)
- [Decision logs](trading-operations/decision-logs.md)
