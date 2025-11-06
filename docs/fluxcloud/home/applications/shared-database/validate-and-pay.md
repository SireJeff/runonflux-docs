# Validate & Pay

The **Validate & Pay** section is the final step after completing all previous sections. It allows you to register, test, and pay for your shared database deployment on the Flux network.

***

### Overview

This process is completed step-by-step. Each step must be finished in sequence before your application can be launched on the network.

> ⚠️ **Important:** Any change to your configuration during the registration steps will reset the process. Make sure your settings are correct before proceeding.

#### Steps Overview:

1. Agree to the Terms of Service
2. Compute Registration Message
3. Register Application
4. Test Application Installation
5. Send Payment

***

### Registration Steps

#### 1. Agree to the Terms of Service

You must accept the Terms of Service before continuing.

* Toggle the checkbox to confirm your agreement.

#### 2. Compute Registration Message

* Click the **Compute Registration Message** button.
* A JSON-formatted message will be generated.
* Sign this message using one of the following methods:
  * **Web3 Wallet** (e.g., Zelcore, MetaMask, SSP): Click the wallet icon to open the signing prompt.
  * **Email Login**: Click the **Flux SSO/Email** button to sign.
* Once signed, the **Signature** field will auto-populate.

<img src="/.gitbook/assets/Validate &#x26; Pay 1.png" alt=""/>

#### 3. Register Application

You will now see the **Total Price + VAT** and the **subscription period**.

* Click the **Register** button to propagate the signed message across the Flux network.
* If successful, a green confirmation message will appear in the top-right corner.
* Proceed to the **Test Application Installation** section.

<img src="/.gitbook/assets/Validate &#x26; Pay 2.png" alt=""/>

#### 4. Test Application Installation

Before paying, it’s essential to verify that your app can install and launch successfully.

* Click the **Test Installation** button.
* Scroll down to view the live installation logs.
* If the test passes, a green confirmation message will appear in the top-right corner.

> ❌ **If the test fails**: Update your application specifications and re-run the test before proceeding.

<img src="/.gitbook/assets/Validate &#x26; Pay 3.png" alt=""/>

#### 5. Payment

Once your app passes the installation test, payment options will be unlocked. Links remain valid for **30 minutes**.

* **Available Methods:** Stripe (Credit/Debit Card), PayPal, or FLUX.
  * Pay with FLUX to receive a **5% discount**.

<img src="/.gitbook/assets/Validate &#x26; Pay 4.png" alt=""/>

***

After successful payment, deployment begins automatically. Your shared database deployment typically deploys within **10–30 minutes**. \
\
Once live, it will appear under **Management > My Active Apps**. Learn more about managing deployed applications in the My Active Apps section.
