# Exchanges and venues

Sidera connects trading logic to supported execution venues. Venue support can change over time, but the current product messaging emphasizes Binance and Hyperliquid as initial live-trading venues.

## Venue responsibilities

Before trading live, understand which responsibilities belong to Sidera and which belong to the venue.

| Area | Sidera role | Venue role |
| --- | --- | --- |
| Strategy logic | Generate, validate, and monitor rules. | Not responsible. |
| Risk checks | Enforce Sidera-side rules before order submission. | May enforce margin, liquidation, and venue-specific controls. |
| Order placement | Submit approved orders through configured credentials or authorization. | Match, reject, fill, or cancel orders according to venue systems. |
| Funds custody | Depends on venue and integration model. | Holds funds or margin according to account structure. |
| Fees and liquidation | Estimate and log where possible. | Final source of fee, funding, margin, and liquidation behavior. |

## Binance

When using Binance:

- Use dedicated API keys for Sidera.
- Disable withdrawals.
- Restrict permissions to trading requirements.
- Confirm futures, spot, or margin scope before enabling a strategy.
- Review fee tier, funding, leverage, and liquidation mechanics.

## Hyperliquid

When using Hyperliquid:

- Connect the wallet used for trading setup.
- Review the agent authorization flow carefully.
- Confirm the agent address and order permissions.
- Understand how signing, funds, and account control work for the venue.
- Start with low-risk testing before increasing allocation.

## Adding new venues

If a venue is not supported yet, document the request with:

- Venue name.
- Markets needed.
- Spot, perps, options, or other instrument type.
- Required order types.
- Expected trading volume.
- API and authentication requirements.
- Why the venue matters for your strategy.

