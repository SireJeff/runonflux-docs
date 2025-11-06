# Cancel Subscription

The **Cancel Subscription** tab allows you to permanently terminate your active application subscription on the FluxCloud. This action is **irreversible** and should only be used if you're certain you no longer need the application or its data.

#### How To Access

> **Applications → Management → Manage App → Global App Management → Cancel Subscription**

Open the **Management** tab in the **Applications** menu, select an application from **My Active Apps**, click **Manage**, then go to the **Global App Management** section and open the **Cancel Subscription** tab.

***

### Overview

You can view the current end date of your subscription directly in the Cancel Subscription panel.\
Example:

> _**"Currently your application is subscribed until 17/07/2025, 05:26:58."**_

#### What Happens When You Cancel

* The application is **immediately removed** from the Flux network.
* All associated **data will be lost** permanently.
* The app will no longer be recoverable unless you have made a **manual backup** using the **Backup/Restore** tool.

<img src="/.gitbook/assets/Cancel Subscription.png" alt=""/>

***

### Finalizing Cancellation

Follow these steps to cancel your application subscription:

Once your changes are configured and you're ready to proceed, follow these steps:\


1. **Generate Cancel Message**
   * Click **Compute Cancel Message** to generate a JSON-formatted message.
2. **Sign the Message**
   * **Web3 Wallet** (Zelcore, MetaMask, SSP): Click the wallet icon.
   * **Email Login**: Click the **Flux SSO/Email** button
   * Once signed, the **Signature** field will auto-fill.
3. **Submit Cancellation**
   * Click **Cancel Application** to confirm.
   * Your app cancellation will begin processing.

> ⏱ Cancellation is typically **effective within 30 minutes**, and your app will be fully removed from the network within approximately **3 hours**.

***

### Alternatives To Cancelling

If you're unsure, consider the following options before canceling:

* **Backup & Migrate** your app to another FluxNode.
* **Reduce resource usage** (e.g., CPU, RAM, Storage) to lower costs.
* **Contact Flux Support** for optimization advice.

***

### Frequently Asked Questions

#### Can I pause instead of canceling?

No. Currently, there is no pause feature. You must cancel and redeploy if you wish to stop and restart usage.

***

#### What happens to my billing?

Once canceled, no further billing occurs. However, any remaining time on your subscription will be forfeited.

***

#### Can I retrieve my data after canceling?

No. Canceling the subscription results in permanent data loss. Always back up before canceling.
