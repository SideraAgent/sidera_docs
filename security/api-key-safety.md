# api key safety

Exchange API keys can allow automated trading. Configure them with the least privilege required.

## API key principles

Use these principles:

* Create dedicated keys for Sidera.
* Disable withdrawals.
* Enable only required trading permissions.
* Use IP restrictions when supported.
* Rotate keys periodically.
* Delete keys that are no longer used.
* Never paste full secrets into chat or support messages.

## Permission checklist

Before adding an exchange API key:

| Permission         | Recommended setting                    |
| ------------------ | -------------------------------------- |
| Read account data  | Enabled if required.                   |
| Place trades       | Enabled only for live trading.         |
| Withdraw funds     | Disabled.                              |
| Internal transfers | Disabled unless explicitly required.   |
| Margin or futures  | Enabled only if the strategy needs it. |
| IP whitelist       | Enabled when supported.                |

## Key rotation

Rotate keys when:

* A team member leaves.
* A device is compromised.
* You accidentally expose a secret.
* You stop using a venue.
* You move from testing to production.
* The exchange recommends rotation.

## Support communication

When asking for help, share:

* Exchange name.
* Permission type.
* Error message.
* Timestamp.
* Last four characters of key ID if needed.

Do not share:

* Full API secret.
* Seed phrase.
* Password.
* Two-factor backup code.
