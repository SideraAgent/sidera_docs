# overview

This section provides ready-to-use Sidera prompts for research, strategy generation, risk management, execution checks, and post-trade review.

Prompts work best when they define:

* The market or asset.
* The timeframe.
* The decision you are trying to make.
* The required evidence.
* The risk limits.
* The output format.

## Prompt structure

Use this structure for most Sidera prompts:

```
Objective:
Market:
Timeframe:
Context:
Constraints:
Output format:
Decision needed:
```

Example:

```
Objective: Decide whether BTC is suitable for a long setup.
Market: BTC perpetuals.
Timeframe: Next 24-72 hours.
Context: I only want trades with clear invalidation and acceptable liquidity.
Constraints: Max 1% account risk per trade. Avoid high funding spikes.
Output format: Bull case, bear case, trigger, invalidation, risk/reward, and next action.
Decision needed: Watch, reject, backtest, or prepare an order.
```

## How to use these prompts

{% stepper %}
{% step %}
### Start with research prompts

Identify a thesis.
{% endstep %}

{% step %}
### Convert the thesis into a strategy prompt
{% endstep %}

{% step %}
### Run backtest and validation prompts
{% endstep %}

{% step %}
### Use risk prompts before allocation
{% endstep %}

{% step %}
### Use execution prompts before live orders
{% endstep %}

{% step %}
### Use review prompts after the trade or strategy cycle
{% endstep %}
{% endstepper %}

{% hint style="warning" %}
Prompts are not trading advice. Treat them as workflow templates. Always verify data, risk assumptions, venue behavior, and execution details before trading.
{% endhint %}

## Recommended prompt flow

```mermaid
flowchart LR
    A["Research prompt"] --> B["Thesis prompt"]
    B --> C["Strategy prompt"]
    C --> D["Backtest prompt"]
    D --> E["Risk prompt"]
    E --> F["Execution prompt"]
    F --> G["Review prompt"]
```

For a complete walkthrough of this sequence, see [End-to-end demo](file:///4774416/core-workflow/end-to-end-demo.md).

## Prompt quality checklist

Before running a prompt, check:

* Is the asset clearly named?
* Is the timeframe clear?
* Is the requested output specific?
* Does the prompt ask for invalidation?
* Does it ask for risks, not only upside?
* Does it include position sizing or risk budget when relevant?
* Does it require a decision at the end?
