# Create a new Flux Wallet

Before you can lock your collateral and run a FluxNode, you’ll need a wallet that supports Flux and allows you to manage your collateral transaction.&#x20;

> 💡 **If you already have a wallet set up, you can skip this step and continue to Send the Required Amount of Flux to Your Wallet.**

You have two options:

* **Zelcore Wallet** – Official, multi-platform Flux wallet with full FluxNode collateral and support.
* **SSP Wallet** – Lightweight browser-based multi-signature wallet designed for managing FluxNode collateral.

> 🔐 Both wallets give you full custody of your funds and are compatible with FluxNode configuration.

***

### Option 1: Zelcore Wallet

Zelcore is the most feature-rich wallet for the Flux ecosystem, available on **Windows**, **macOS**, **Linux**, **Android**, and **iOS**.

#### Set Up Your Account

1. Download Zelcore from the [official website](https://zelcore.io/).
2. Launch the app and click **“Sync/Register BIP44 Seed Phrase Account.”**
3. Select the desired **seed phrase word count**, then click **Generate Seed Phrase**.
   * **12 words** – Basic security, faster to write down.
   * **18 words** – Stronger security.
   * **24 words** – **Recommended** for maximum security.

<img src="/.gitbook/assets/BIP44.png" alt=""/>

4. **Save your seed phrase** in a secure location.

* Toggle on **"I have saved my seed phrase in a secure location"** and click **Next**.

<img src="/.gitbook/assets/Seed phrase copy.png" alt=""/>

5. Enter your seed phrase again to confirm, then click **Verify**.

<img src="/.gitbook/assets/Seed phrase verify.png" alt=""/>

5. Once verified, enter a **name** for your seed phrase and set an **Easy Login password**.
   * This password will be used for signing in to your account.

<img src="/.gitbook/assets/Easy Login PW.png" alt=""/>

6. Click **Register**, then log in to your new account using your Easy Login password.

<img src="/.gitbook/assets/Easy Login Login.png" alt=""/>

#### Enable Decentralized 2FA (d2FA)

For increased security, enable d2FA—an encrypted PIN stored on the **Flux blockchain**:

* Open the **Apps** menu → Click **FluxID**
* Select **d2FA** and follow the setup
* A small fee of `0.0002 FLUX` is required (automatically airdropped to new wallets within 24 hours)

<img src="/.gitbook/assets/d2fa.png" alt=""/>

#### View & Add Assets

* Click **"Show Zero Sum"** to display all assets, including Flux.
* To add Flux from other chains (e.g., Flux-BSC, Flux-ETH), hover over **“+ Add Assets”** and follow the prompts.



***

### Option 2: SSP Wallet&#x20;

If you're looking for a browser-based, self‑custodial wallet with advanced multi‑signature and Web3 capabilities, the **SSP Wallet** is an excellent choice.

**Why choose SSP Wallet?**

* **True 2-of-2 multisignature security**: every transaction requires approval by both your desktop wallet (extension) and your SSP mobile Key app—preventing single-device compromise.
* **Supports 15+ blockchains, including FLUX**; integrates with WalletConnect v2 and ERC-4337 smart contract wallets for seamless dApp access.
* **Zero server-side data storage**—private keys and seeds never leave your devices, encrypted locally and verified through Halborn audits.

#### Set Up Your Account

1. Visit the **official SSP Wallet documentation**: [docs.sspwallet.io](https://docs.sspwallet.io/docs)
2. Follow the guide to **create a new wallet**.
3. Complete the steps to **install the SSP Key**.

> ℹ️ All setup instructions are provided in the SSP Wallet documentation to ensure you have the most up-to-date process.
