# workspace setup

The Sidera workspace brings research, strategy, execution, risk, and review into one operating environment. A clean setup reduces mistakes later when workflows become automated.

## Main workspace areas

| Area          | Purpose                                                                         |
| ------------- | ------------------------------------------------------------------------------- |
| Research      | Ask market questions, run scans, develop theses, and collect evidence.          |
| Strategy Lab  | Create strategy logic, review generated code, and run backtests.                |
| Markets       | Inspect supported markets, charts, liquidity, and venue data where available.   |
| Trading panel | Prepare orders, review RiskGuard results, and manage execution settings.        |
| Risk          | Configure limits, monitor exposure, and review blocked actions.                 |
| Logs          | Inspect reasoning traces, backtest results, order decisions, and system events. |
| Settings      | Manage account, model, provider, exchange, notification, and security settings. |

## Recommended first-time settings

Before building a strategy, review these settings:

* Default trading mode: dry-run.
* Base currency or account unit.
* Time zone.
* Notification channels.
* Research provider configuration, if required.
* Exchange credentials, only if you are preparing live trading.
* RiskGuard default limits.
* Strategy allocation policy.

## Model and research providers

Sidera may allow AI model providers, web search providers, or MCP-style tools to extend research and agent workflows.

When adding providers:

* Use dedicated API keys.
* Store credentials only in the intended settings area.
* Confirm whether the provider is used for research, execution, or both.
* Test with low-cost research prompts before running large workflows.
* Remove unused providers.

## Notification setup

Configure notifications before live deployment. At minimum, enable alerts for:

* Strategy start and stop.
* Order generated.
* Order blocked.
* Position opened.
* Position closed.
* Drawdown warning.
* RiskGuard failure.
* Venue connectivity issue.

For active trading, route urgent risk alerts to channels you actually monitor.

## Workspace hygiene

Keep the workspace clean:

* Name strategies clearly.
* Archive abandoned ideas.
* Keep one source of truth for risk limits.
* Add notes to major backtest versions.
* Do not reuse live credentials across experimental environments.
* Review logs after each strategy iteration.

## Suggested naming convention

Use a strategy name that includes market, timeframe, and core logic.

Examples:

* `BTC-4H-Momentum-v1`
* `SOL-1H-Breakout-Risk1pct`
* `ETH-MeanReversion-NoHighFunding`
* `Portfolio-Hedge-BTC-Drawdown`

Good names make logs and support requests much easier to understand.
