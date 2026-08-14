# decision logs

Decision logs make Sidera reviewable. They record the reasoning, checks, and execution details behind trading actions.

Logs are essential for three reasons:

{% stepper %}
{% step %}
## Understand why Sidera acted
{% endstep %}

{% step %}
## Identify whether a strategy followed its rules
{% endstep %}

{% step %}
## Create a feedback loop for improving future decisions
{% endstep %}
{% endstepper %}

## What should be logged

For every strategy run or live order, record:

* Strategy name or ID.
* Market and venue.
* Direction and order type.
* Trigger condition.
* AI reasoning summary.
* RiskGuard result.
* Position size.
* Stop-loss and target logic.
* Estimated slippage.
* Execution result.
* Fees where available.
* Outcome and review notes.

## Example log structure

| Field         | Example                                                      |
| ------------- | ------------------------------------------------------------ |
| Strategy      | SOL 4H Momentum                                              |
| Market        | SOL-PERP                                                     |
| Venue         | Hyperliquid                                                  |
| Trigger       | 4H close above moving average with volume expansion          |
| RiskGuard     | Passed                                                       |
| Position size | 1% account risk                                              |
| Order type    | Market or sliced execution                                   |
| Stop          | Below last swing low                                         |
| Result        | Filled with acceptable slippage                              |
| Review        | Entry matched strategy; monitor funding and BTC correlation. |

## Reviewing decisions

After each trade or strategy cycle, ask:

* Did Sidera follow the intended rules?
* Was the research thesis still valid at execution time?
* Was position size appropriate?
* Did RiskGuard catch all relevant issues?
* Was slippage acceptable?
* Did the exit follow plan or emotion?
* What should change before the next deployment?
