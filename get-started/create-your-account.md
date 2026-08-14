# create your account

Create a Sidera account to unlock the AI research and trading workspace. Depending on the enabled login options, you may sign in with a wallet signature or with email and password.

## Before you start

Prepare the following:

* A supported browser wallet if you plan to use wallet login or Hyperliquid setup.
* Access to your email if using email and password login.
* A clear understanding of whether you want research-only usage first or live trading setup.

{% hint style="info" %}
You can start with research and dry-run workflows before connecting exchange credentials. Live trading should only be enabled after you understand execution permissions, risk limits, and venue behavior.
{% endhint %}

## Sign up

{% stepper %}
{% step %}
### Open Sidera

Open [sidera.markets](https://sidera.markets/).
{% endstep %}

{% step %}
### Choose a sign-up option

Choose the sign-up or sign-in option available in the app.
{% endstep %}

{% step %}
### Authenticate with a wallet

If using a wallet, connect the browser wallet and confirm the signature request.
{% endstep %}

{% step %}
### Create an email account

If using email, create an account with your email and password.
{% endstep %}

{% step %}
### Complete onboarding

Complete any onboarding steps shown in the workspace.
{% endstep %}
{% endstepper %}

## Wallet login

Wallet login proves that you control the connected address. A wallet signature is used for authentication; it should not transfer funds by itself.

When using wallet login:

* Confirm that the wallet address shown in Sidera matches the active account in your wallet extension.
* Check the network requirement before signing. Some flows may require Arbitrum One.
* Do not sign messages if the domain or request looks unfamiliar.
* Keep your seed phrase private. Sidera should never ask for it.

## After account creation

After your account is created, complete the basic setup checklist:

| Step                                         | Purpose                                                                                |
| -------------------------------------------- | -------------------------------------------------------------------------------------- |
| Configure profile                            | Establish account identity and default workspace settings.                             |
| Review trading mode                          | Decide whether to remain in dry-run mode or prepare live trading.                      |
| Add research providers if needed             | Enable web or market research integrations where available.                            |
| Connect exchange credentials only when ready | Required for live execution, not required for reading documentation or basic research. |
| Set risk limits                              | Define the hard boundaries that RiskGuard must enforce.                                |

## Common issues

<details>

<summary>Nothing happens after clicking connect wallet</summary>

Check the wallet extension icon in your browser toolbar. The signature prompt may be waiting there.

</details>

<details>

<summary>The active wallet account is different</summary>

Switch to the expected wallet account in your extension, disconnect the wallet in Sidera, and reconnect.

</details>

<details>

<summary>Signature request times out</summary>

Open the wallet extension, confirm whether a request is pending, and try again. If the browser extension is locked, unlock it first.

</details>

<details>

<summary>Wallet is not registered</summary>

Complete account creation before trying to sign in with that wallet.

</details>
