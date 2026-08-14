# Troubleshooting

Use this page to diagnose common Sidera setup, research, strategy, execution, and risk issues.

## Account and login

### Wallet signature does not appear

Try:

1. Open the wallet extension manually.
2. Confirm the extension is unlocked.
3. Check that the browser is not blocking popups.
4. Refresh Sidera and reconnect.
5. Confirm the connected wallet address is the one you expect.

### Wrong wallet account

Switch accounts in the wallet extension, then disconnect and reconnect in Sidera.

## Research

### Research answer is too broad

Use a more specific prompt:

```text
Analyze BTC for the next 24-72 hours only. Focus on liquidity, derivatives positioning, key levels, and invalidation. Do not include long-term macro commentary unless it changes the trade plan.
```

### Research lacks evidence

Ask for sources and confidence:

```text
For each claim, show the source or data type behind it and rate confidence as low, medium, or high.
```

## Strategy

### Strategy overtrades

Add no-trade conditions:

- Minimum volume threshold.
- Trend filter.
- Volatility filter.
- Cooldown between trades.
- Funding or spread filter.

### Backtest looks too good

Check:

- Fees.
- Slippage.
- Data range.
- Trade count.
- Overfitting.
- One-trade dependency.
- Lookahead bias.

## Execution

### Order blocked by RiskGuard

Review the exact blocked rule. Do not loosen risk settings until you understand why the order failed.

Common causes:

- Size too large.
- Missing stop.
- Leverage too high.
- Daily drawdown limit reached.
- Strategy paused.
- Venue disabled.

### Live order did not place

Check:

- Live trading is enabled.
- Exchange credentials are valid.
- Venue market is supported.
- RiskGuard approved the order.
- API permissions allow trading.
- Wallet or agent authorization is still active.

## Alerts

### Alerts are not reaching you

Check:

- Notification channel is connected.
- Strategy alerts are enabled.
- Urgent risk alerts are enabled.
- The channel is not muted.
- The alert rule actually triggered.

## Logs

### Missing decision logs

If logs are missing:

- Confirm the strategy ran.
- Confirm the workflow was not canceled.
- Check whether the action was research-only, dry-run, or live.
- Retry with a smaller workflow.
- Contact support with the strategy ID and timestamp.

