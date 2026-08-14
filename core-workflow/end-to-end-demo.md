# end to end demo

This demo shows how Sidera turns a user prompt into a complete trading workflow:

```
Prompt -> AI thesis -> Strategy -> Backtest -> Risk check -> Execution -> Monitoring -> Review
```

The example uses SOL, but the workflow applies to any supported liquid market.

{% hint style="warning" %}
This is a workflow demonstration, not trading advice. Replace the market, timeframe, risk limits, and venue with your own requirements before using it.
{% endhint %}

## Demo objective

The user wants to know whether SOL offers a tradeable opportunity this week. They do not start with a strategy. They start with a question.

The correct Sidera flow is:

{% stepper %}
{% step %}
## Ask Research Copilot for market intelligence
{% endstep %}

{% step %}
## Let the AI generate a clear thesis
{% endstep %}

{% step %}
## Convert the thesis into strategy rules
{% endstep %}

{% step %}
## Backtest the rules
{% endstep %}

{% step %}
## Configure RiskGuard
{% endstep %}

{% step %}
## Deploy through Smart Execution only if conditions remain valid
{% endstep %}

{% step %}
## Let Risk Sentinel monitor the position
{% endstep %}

{% step %}
## Review the result and feed the lesson back into future strategy decisions
{% endstep %}

{% step %}
## User prompt

The workflow starts with a research prompt.

```
Analyze SOL for the next 3-7 days.

I want to know whether there is a tradeable long or short opportunity.

Please include:
- Current market structure
- Key catalysts
- Derivatives positioning
- Liquidity conditions
- Bull case
- Bear case
- Trigger conditions
- Invalidation levels
- Main risks
- Recommended next action

Do not suggest a trade unless the thesis has clear invalidation and can be converted into rules.
```
{% endstep %}

{% step %}
## AI thesis

Research Copilot should return a structured thesis, not a generic market summary.

Example output:

| Section      | Example                                                                                            |
| ------------ | -------------------------------------------------------------------------------------------------- |
| Market read  | SOL is showing improving momentum but remains sensitive to BTC direction and funding spikes.       |
| Bull case    | Upside continuation is possible if price holds above the recent breakout level and volume expands. |
| Bear case    | Failure to hold the breakout level would indicate a false breakout and increase downside risk.     |
| Trigger      | Long only after a 4H close above resistance with volume confirmation.                              |
| Invalidation | Thesis invalid if price closes back below the breakout base or funding becomes extreme.            |
| Main risk    | BTC reversal, crowded long positioning, low-liquidity breakout, or failed retest.                  |
| Next action  | Convert the thesis into a rules-based strategy and backtest before any live order.                 |

The important product point: the AI thesis becomes the input for strategy generation. Sidera is not stopping at commentary.
{% endstep %}

{% step %}
## Strategy generation

The user now asks Strategy Forge to convert the thesis into executable rules.

```
Turn the SOL thesis into a rules-based strategy.

Market: SOL perpetuals
Timeframe: 4H
Direction: Long only
Risk: Maximum 1% account risk per trade

Rules:
- Enter only after a 4H close above the breakout level.
- Require volume expansion versus recent average.
- Avoid entry if funding is extreme.
- Stop below the failed breakout or recent swing low.
- Take profit at 2R or trail if momentum continues.
- Do not enter if BTC is breaking down at the same time.

Return:
- Strategy specification
- Entry logic
- Exit logic
- Stop-loss logic
- No-trade conditions
- Backtest assumptions
- RiskGuard settings required before deployment
```
{% endstep %}

{% step %}
## Strategy specification

Strategy Forge should produce a strategy that can be tested.

Example:

| Component    | Rule                                                              |
| ------------ | ----------------------------------------------------------------- |
| Market       | SOL perpetuals                                                    |
| Timeframe    | 4H                                                                |
| Direction    | Long only                                                         |
| Entry        | 4H close above breakout level with volume expansion               |
| Confirmation | BTC not in breakdown mode; funding not extreme                    |
| Stop         | Below breakout base or latest swing low                           |
| Target       | 2R initial target, optional trailing stop after target one        |
| Risk         | 1% account risk per trade                                         |
| No-trade     | Low liquidity, extreme funding, BTC breakdown, invalidated thesis |
{% endstep %}

{% step %}
## Backtest and validation

The user asks Sidera to validate the strategy before deployment.

```
Backtest this SOL 4H breakout strategy.

Include:
- Trade count
- Win rate
- Profit factor
- Maximum drawdown
- Average trade after fees and slippage
- Performance during trending markets
- Performance during sideways markets
- Worst losing streak
- Sensitivity to funding and slippage

End with a recommendation: reject, revise, dry-run, or live pilot.
```

Example validation result:

| Metric          | Example interpretation                                                    |
| --------------- | ------------------------------------------------------------------------- |
| Trade count     | Enough samples to evaluate behavior, but not enough to assume durability. |
| Profit factor   | Positive after fees, but sensitive to slippage.                           |
| Drawdown        | Acceptable only with strict position sizing.                              |
| Regime behavior | Performs best in trending regimes, weak in sideways chop.                 |
| Recommendation  | Dry-run first. Do not move directly to live trading.                      |
{% endstep %}

{% step %}
## RiskGuard configuration

Before any deployment, the user configures hard limits.

```
Recommend RiskGuard settings for the SOL 4H breakout strategy.

Account risk tolerance: Conservative
Max risk per trade: 1%
Max daily drawdown: 2%
Max strategy allocation: 15%
Leverage: Low or none

Return the required hard rules that should block an order.
```

Example RiskGuard rules:

| Rule              | Behavior                                               |
| ----------------- | ------------------------------------------------------ |
| Per-trade risk    | Block if expected loss exceeds 1% of account equity.   |
| Stop requirement  | Block if no stop or invalidation level exists.         |
| Daily drawdown    | Pause new entries after 2% daily drawdown.             |
| Funding filter    | Block if funding exceeds configured threshold.         |
| BTC regime filter | Block if BTC is in breakdown mode.                     |
| Slippage limit    | Block if estimated slippage exceeds allowed threshold. |
{% endstep %}

{% step %}
## Dry-run deployment

The strategy should run in dry-run mode first.

```
Deploy this SOL strategy in dry-run mode.

During dry-run, log:
- Every signal
- Whether the entry rule triggered
- Whether RiskGuard would approve or block
- Estimated position size
- Estimated slippage
- Simulated order result
- Alerts that would be sent
```

Dry-run confirms that the strategy behaves as intended before any capital is at risk.
{% endstep %}

{% step %}
## Smart Execution

If dry-run behavior is acceptable, the user can prepare a limited live pilot.

```
Prepare a minimum-size live pilot for this SOL strategy.

Before execution, check:
- Thesis still valid
- Breakout level still intact
- Volume confirmation
- BTC regime
- Funding
- Liquidity
- Estimated slippage
- RiskGuard approval
- Venue availability

Return one decision: proceed with minimum size, wait, resize, or cancel.
```

Smart Execution should only submit an order if:

* The thesis remains valid.
* The strategy rules are satisfied.
* RiskGuard passes.
* Venue conditions are acceptable.
* The order is logged.
{% endstep %}

{% step %}
## Risk Sentinel monitoring

After execution, Risk Sentinel monitors the position.

Example monitoring rules:

| Condition                    | Action                                                      |
| ---------------------------- | ----------------------------------------------------------- |
| Price approaches stop        | Send urgent alert.                                          |
| Stop is hit                  | Exit according to strategy rules.                           |
| Funding becomes extreme      | Pause new entries and request review.                       |
| BTC breaks down              | Reduce, pause, or exit depending on configured permissions. |
| Daily drawdown limit reached | Block new strategy entries.                                 |
| Venue connectivity issue     | Alert user and prevent new orders.                          |
{% endstep %}

{% step %}
## Post-trade review

After the trade closes, the user asks Sidera to review the full decision chain.

```
Review the completed SOL strategy cycle.

Use:
- Original research thesis
- Strategy rules
- Backtest summary
- RiskGuard checks
- Execution log
- Fill quality
- Risk Sentinel alerts
- Final outcome

Separate:
- Good decision quality
- Bad decision quality
- Good or bad execution
- Luck versus process
- What should change before the next trade
```
{% endstep %}
{% endstepper %}

## What this demo proves

This end-to-end workflow demonstrates Sidera's core value:

| Stage      | Product module   | Value                                           |
| ---------- | ---------------- | ----------------------------------------------- |
| Prompt     | Research Copilot | User starts with a market question, not code.   |
| AI thesis  | Research Copilot | Market information becomes a structured thesis. |
| Strategy   | Strategy Forge   | Thesis becomes executable rules.                |
| Backtest   | Strategy Lab     | Rules are tested before deployment.             |
| Risk check | RiskGuard        | Hard limits control the AI workflow.            |
| Execution  | Smart Execution  | Orders are placed only after validation.        |
| Monitoring | Risk Sentinel    | The position is watched after entry.            |
| Review     | Decision logs    | The system learns from the result.              |

## Reusable template

Use this template for any market:

```
Analyze [MARKET] over [TIMEFRAME].

Step 1: Build a tradeable AI thesis with bull case, bear case, trigger, invalidation, and risks.
Step 2: Convert the thesis into a rules-based strategy.
Step 3: Define entry, exit, stop, sizing, and no-trade conditions.
Step 4: Backtest with fees, slippage, drawdown, and regime analysis.
Step 5: Recommend RiskGuard settings.
Step 6: Prepare dry-run deployment.
Step 7: If dry-run passes, prepare a minimum-size live pilot.
Step 8: Define Risk Sentinel monitoring and post-trade review criteria.

Return the workflow as a decision chain from research to execution.
```
