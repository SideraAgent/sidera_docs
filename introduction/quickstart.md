# quickstart

This quickstart helps you use Sidera safely from first login to a controlled dry-run strategy. Do not begin with live trading. Start by proving that research, strategy logic, risk rules, alerts, and logs behave as expected.

## What you will do

In this guide you will:

{% stepper %}
{% step %}
## Create or sign in to your account
{% endstep %}

{% step %}
## Configure the workspace
{% endstep %}

{% step %}
## Start with a market prompt
{% endstep %}

{% step %}
## Generate an AI thesis
{% endstep %}

{% step %}
## Convert the thesis into strategy rules
{% endstep %}

{% step %}
## Backtest and validate the rules
{% endstep %}

{% step %}
## Configure RiskGuard limits
{% endstep %}

{% step %}
## Deploy the strategy in dry-run mode
{% endstep %}

{% step %}
## Review the decision logs before live trading
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Dry-run is the recommended first workflow. Live trading should only be enabled after you understand venue permissions, risk limits, and strategy behavior.
{% endhint %}

{% stepper %}
{% step %}
## Sign in

Open [sidera.markets](https://sidera.markets/) and sign in with the available account method. Depending on your workspace configuration, this may be email/password or wallet signature.

After sign-in, confirm:

* You are in the correct account.
* Your workspace shows research and trading modules.
* Trading mode is not live unless you intentionally enabled it.
{% endstep %}

{% step %}
## Start with a market prompt

Ask a focused question:

```
Scan BTC, ETH, and SOL for the next 24-72 hours. Compare liquidity, trend strength, volatility, catalysts, and downside risk. Rank them by opportunity quality.
```

Review the answer. Do not trade from the summary alone. Look for:

* Evidence quality.
* Key levels.
* Bull and bear cases.
* Invalidation conditions.
* Time horizon.
* Risks that would cancel the idea.
{% endstep %}

{% step %}
## Generate an AI thesis

The research answer should become a decision-ready thesis:

* What is the opportunity?
* Why might it work?
* What would prove it wrong?
* What conditions must exist before entry?
* What risks should block the trade?

If the thesis is vague, ask Sidera to refine it before moving forward.

```
Refine this into a tradeable thesis. Include bull case, bear case, trigger, invalidation, timeframe, and recommended next action.
```
{% endstep %}

{% step %}
## Convert thesis into rules

Choose one thesis and ask Strategy Forge to turn it into strategy logic.

```
Turn the SOL thesis into a 4-hour rules-based strategy. Include entry, invalidation, stop-loss, take-profit logic, no-trade conditions, and maximum 1% account risk per trade.
```

The goal is not to get the perfect strategy on the first attempt. The goal is to make the idea testable.
{% endstep %}

{% step %}
## Run a backtest

Run an initial backtest and inspect:

* Trade count.
* Profit factor.
* Maximum drawdown.
* Losing streak.
* Average trade after fees and slippage.
* Behavior in sideways markets.

If the strategy depends on one unusual historical period, reject or revise it.
{% endstep %}

{% step %}
## Configure RiskGuard

Before any deployment, set hard limits:

| Setting               | Conservative starting point      |
| --------------------- | -------------------------------- |
| Per-trade risk        | 0.25% to 1.00% of account equity |
| Daily drawdown stop   | 2% to 3%                         |
| Strategy allocation   | 10% to 20% of account equity     |
| Leverage              | None or low leverage             |
| Stop-loss requirement | Required for live strategies     |
{% endstep %}

{% step %}
## Deploy in dry-run mode

Dry-run mode lets Sidera generate signals, simulated orders, logs, and alerts without placing real orders.

Confirm:

* Entries happen only when strategy rules are met.
* Stop logic is present.
* RiskGuard warnings appear correctly.
* Logs are detailed enough to review.
* Alerts reach the expected channels.
{% endstep %}

{% step %}
## Review the run

After the dry-run, ask:

```
Review the dry-run logs for this strategy. Did it follow the intended entry, exit, and risk rules? Identify any issues before live deployment.
```

Only consider live trading after dry-run behavior matches the intended design.
{% endstep %}
{% endstepper %}

## Quickstart completion checklist

* Account created and verified.
* Workspace settings reviewed.
* Market prompt submitted.
* AI thesis generated and inspected.
* Strategy rules created.
* Backtest completed.
* RiskGuard limits configured.
* Dry-run deployment tested.
* Decision logs reviewed.
* Live trading remains disabled until intentionally approved.
