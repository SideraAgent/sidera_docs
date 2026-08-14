# faq

<details>

<summary>Is Sidera financial advice?</summary>

No. Sidera is a research, strategy, automation, and execution workspace. It can help analyze markets and run workflows, but trading decisions remain the user's responsibility.

</details>

<details>

<summary>Do I need to code?</summary>

No for most strategy-building workflows. You can describe a strategy in plain English and use Strategy Forge to generate strategy logic. Users with existing code may also import or adapt their own logic where supported.

</details>

<details>

<summary>Can Sidera trade automatically?</summary>

Sidera can support automated strategy execution when live trading is enabled, exchange credentials are configured, and RiskGuard approves the order. You should test workflows in dry-run mode before allowing live orders.

</details>

<details>

<summary>What happens if the AI is wrong?</summary>

AI output can be wrong. That is why Sidera separates AI reasoning from deterministic risk enforcement. RiskGuard should block actions that violate user-defined rules, even if the AI analysis appears confident.

</details>

<details>

<summary>Can I set my own risk rules?</summary>

Yes. You should configure maximum position size, per-trade risk, daily drawdown ceiling, stop-loss requirements, leverage caps, and strategy allocations before live trading.

</details>

<details>

<summary>Which exchanges does Sidera support?</summary>

Sidera's current public product messaging emphasizes Binance and Hyperliquid as initial live-trading venues. Venue support may change, so confirm availability inside the app before planning live execution.

</details>

<details>

<summary>Can I intervene in a live strategy?</summary>

Yes. A professional setup should allow you to pause, override, or close a strategy manually. Risk Sentinel is designed to support real-time monitoring and intervention workflows.

</details>

<details>

<summary>What are credits?</summary>

Credits meter AI-powered actions such as research queries, strategy generation, backtesting, and execution workflows. Review estimated credit cost before running larger tasks.

</details>

<details>

<summary>Should I start with live trading?</summary>

No. Start with research, strategy generation, backtesting, and dry-run deployment. Move to live trading only after you understand the strategy, risk rules, exchange permissions, and alert behavior.

</details>
