# Get support

Use support when you need help with account access, exchange setup, strategy behavior, risk rules, billing, or technical issues.

## Before contacting support

Collect the following information:

- Account email or wallet address used for login.
- Approximate time of the issue.
- Browser and operating system.
- Exchange or venue involved.
- Strategy name or ID, if relevant.
- Order ID or decision log entry, if relevant.
- Screenshots of error messages, with sensitive information hidden.
- Whether the issue happened in dry-run or live trading mode.

## Trading issue checklist

For order or strategy issues, include:

- Market.
- Venue.
- Strategy name.
- Expected behavior.
- Actual behavior.
- RiskGuard status.
- Error message.
- Whether an order was placed, blocked, partially filled, or canceled.

## Security issue checklist

If you suspect account or credential compromise:

1. Disable live trading.
2. Revoke affected exchange API keys from the exchange account.
3. Disconnect or rotate credentials in Sidera.
4. Change account password if email login is enabled.
5. Review recent decision logs and exchange order history.
6. Contact support with the incident timeline.

## Good support request example

```text
I was running SOL 4H Momentum in dry-run mode at around 14:30 UTC. The strategy generated an entry even though my no-trade rule says to avoid extreme funding. RiskGuard showed a warning but did not block it. Please review strategy ID S-123 and the decision log around that time.
```

## Do not share

Never send support:

- Seed phrases.
- Private keys.
- Full exchange API secrets in plain text.
- Passwords.
- Two-factor authentication backup codes.

