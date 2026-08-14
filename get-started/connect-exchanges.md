# Connect exchanges

Exchange connectivity allows Sidera to move from research and simulation into live execution. Sidera's initial live-trading focus includes venues such as Binance and Hyperliquid, with additional venues depending on product availability and user demand.

{% hint style="warning" %}
Connecting exchange credentials can allow real orders to be placed when live trading is enabled. Start in dry-run mode, use small limits, and confirm that RiskGuard is configured before enabling live execution.
{% endhint %}

## Trading modes

Sidera supports two practical operating modes:

| Mode | What it means | Recommended use |
| --- | --- | --- |
| Dry-run | The agent can research, generate strategies, simulate actions, and validate logic without placing real exchange orders. | First setup, strategy testing, onboarding, and review. |
| Live trading | Orders can be submitted to configured exchanges after RiskGuard approval and user-defined permissions. | Only after credentials, limits, and execution permissions are reviewed. |

## Connect Binance

The exact setup screen may vary, but the professional checklist is the same:

1. Create or open your Binance API key from the exchange account.
2. Restrict the API key to the minimum permissions required for your intended workflow.
3. Disable withdrawal permission for trading automation keys.
4. Add IP restrictions if the exchange and Sidera deployment model support it.
5. Enter the API key and secret in Sidera's exchange settings.
6. Run a dry-run order validation before enabling live trading.
7. Set maximum order size, leverage limits, and daily loss limits before first live use.

## Connect Hyperliquid

Hyperliquid setup may involve wallet connection, agent authorization, and order-signing permissions.

Typical flow:

1. Connect the wallet that controls the Hyperliquid account.
2. Bind the wallet to your Sidera account if required.
3. Authorize the trading agent for order placement.
4. Confirm that funds remain in your wallet or venue account according to the venue's design.
5. Review the agent address and permission scope before approving.
6. Test with dry-run or minimum-size activity before scaling up.

## Credential security checklist

Before enabling live trading, confirm:

- API keys do not have withdrawal permission.
- Your account uses two-factor authentication.
- Risk limits are already configured in Sidera.
- You understand which strategies are allowed to place live orders.
- You know how to pause, override, or force-exit a strategy.
- You have checked venue-specific fees, slippage, and liquidation rules.

## Venue readiness checklist

| Item | Why it matters |
| --- | --- |
| Market coverage | Confirm that the asset or contract you want to trade is available on the connected venue. |
| Liquidity | Thin markets can create slippage and poor fills. |
| Leverage | Higher leverage increases liquidation risk and can amplify small mistakes. |
| Fees | Backtests should account for realistic trading costs. |
| Order types | Confirm whether market, limit, trigger, reduce-only, or TWAP-style execution is supported. |
| Maintenance windows | Exchange downtime can affect strategy reliability. |

## When not to connect live trading

Do not enable live trading if:

- You have not configured maximum position size and daily drawdown limits.
- You do not understand the strategy's entry, exit, and invalidation rules.
- The strategy has not been tested in dry-run or backtest mode.
- You cannot monitor alerts during the first live deployment.
- You are trading with funds you cannot afford to lose.

