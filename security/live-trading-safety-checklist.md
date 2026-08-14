# live trading safety checklist

Use this checklist before enabling live trading for any Sidera strategy.

## Account

* [ ] Account identity is verified.
* [ ] Login method is secure.
* [ ] Wallet address is correct.
* [ ] Two-factor authentication is enabled where available.
* [ ] You know how to disable live trading quickly.

## Venue

* [ ] Exchange credentials are dedicated to Sidera.
* [ ] Withdrawal permission is disabled.
* [ ] Venue supports the intended market.
* [ ] Fees, funding, and liquidation rules are understood.
* [ ] Minimum order size is understood.
* [ ] API limits are understood.

## Strategy

* [ ] Strategy has clear entry rules.
* [ ] Strategy has clear exit rules.
* [ ] Strategy has explicit invalidation.
* [ ] Backtest includes fees and slippage.
* [ ] Dry-run behavior matches expectations.
* [ ] Strategy does not overtrade.
* [ ] Strategy has a defined allocation.

## RiskGuard

* [ ] Maximum position size is configured.
* [ ] Per-trade risk is configured.
* [ ] Daily drawdown limit is configured.
* [ ] Stop-loss requirement is enabled.
* [ ] Leverage cap is configured.
* [ ] Portfolio exposure cap is configured if running multiple strategies.

## Monitoring

* [ ] Alerts are enabled.
* [ ] Urgent alerts reach a channel you monitor.
* [ ] You know how to pause the strategy.
* [ ] You know how to force-exit a position.
* [ ] Decision logs are enabled and reviewable.

## Final approval

{% hint style="warning" %}
Only enable live trading when every item above is complete. If one item is unclear, remain in dry-run mode.
{% endhint %}
