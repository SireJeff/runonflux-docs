# Manual Deployment

This guide walks you through launching a custom Kaspa Node on FluxCloud using the **Register New App** tab.

**How To Access**

> **Applications → Register New App**

Visit [home.runonflux.io](https://home.runonflux.io/), sign in, open the **Applications** menu, and select **Register New App**.

***

#### Overview of Sections <a href="#overview-of-sections" id="overview-of-sections"></a>

You'll configure all necessary settings across four main sections:

* **Details**
* **Component**
* **Validate & Pay**

Let’s walk through each tab **step by step**.

***

#### Details

The Details tab is where you provide general information and configuration settings for your application.

**Version**

* Shows you the version of the application specifications
* This is hardcoded and cannot be changed

**Application Name**

* Must be at least **3 characters** long
* Allowed characters: **A–Z, a–z, 0–9**
* **No spaces or special characters** allowed

**Application Description**

* Must be at least **3 characters** long

**Owner**

* Displays the FluxID associated with your account.
* This is hardcoded and cannot be changed.

**Contacts (Optional)**

* Enter a **public contact email** enclosed within brackets and enclose them in quotations., for example: `["test@gmail.com"]`. You will receive important notifications (e.g., app expiration).

> ⚠️ Contacts are **publicly accessible** via the FluxCloud API

* Use the blue upload button next to the field to upload your contact information to Flux Storage
* This replaces parameters with a storage link (only the link is visible via API, and the content is not accessible)

**Allowed Locations (Optional)**

Specify where your app can be deployed. You can select one or more by clicking the plus icon:

* Continents
* Countries
* Regions

**Forbidden Locations (Optional)**

Specify where your app can be deployed. You can select one or more by clicking the plus icon:

* Continents
* Countries
* Regions

**Instances**

Define how many **servers (instances)** will run your application

* **Minimum:** 3 (for redundancy and load balancing)
* **Maximum:** 100

**Period**

Choose your app’s **subscription duration**

* from **1 week to 1 year**
* This is a **prepaid**, **non-refundable** period

**Static IP (Recommended)**

Toggle this on if your app requires a **static IP address**

* **Additional cost:** $0.40 USD

**Enterprise Application (Not Needed)**

***

#### Component

The Component section is where you define your application’s container settings, connectivity options, environment variables, and resource requirements.

**Component Name**

* kaspad

**Component Description**&#x20;

* kaspad container

**Repository**

* kaspanet/rusty-kaspad:latest

**Ports**

* Mainnet: `[15110,15111,17110,18110]`
* Testnet: `[15210,15211,17210,18210]`

&#x20;**Domains**&#x20;

* Default needs to be `["","","",""]`
* You can add custom domains, It is mapping to the number position of each port xeample format `["www.test.com","","",""]`
* For setup instructions, refer to the **Custom Domain Setup** guide

**Cont. Ports**

* Mainnet: `[15110,15111,17110,18110]`
* Testnet: `[15210,15211,17210,18210]`

**Environment (Not Needed)**&#x20;

**Commands (Optional)**

* Mainnet: `["kaspad","--yes","--nologfiles","--disable-upnp","--utxoindex","--listen=0.0.0.0:15211"--rpclisten=0.0.0.0:15210","--rpclisten-borsh=0.0.0.0:17210","--rpclisten-json=0.0.0.0:18210"]`
* Testnet: `["kaspad","--yes","--nologfiles","--disable-upnp","--utxoindex","--testnet","--listen=0.0.0.0:15211"--rpclisten=0.0.0.0:15210","--rpclisten-borsh=0.0.0.0:17210","--rpclisten-json=0.0.0.0:18210"]`

**Cont. Data**&#x20;

* /app/data

**Resources**

* Recommended Resources
  * CPU: 8 vCores
  * RAM: 16,000MB, or 24,000MB RAM
  * SSD: 256GB

***

#### Validate & Pay

The Validate & Pay section is the final step after completing all previous sections. It allows you to register, test, and pay for your application deployment on the Flux network. Follow the Registration Steps below.&#x20;

**1. Agree to the Terms of Service**

You must accept the Terms of Service before continuing.

* Toggle the checkbox to confirm your agreement.

**2. Compute Registration Message**

* Click the **Compute Registration Message** button.
* A JSON-formatted message will be generated.
* Sign this message using one of the following methods:
  * **Web3 Wallet** (e.g., Zelcore, MetaMask, SSP): Click the wallet icon to open the signing prompt.
  * **Email Login**: Click the **Flux SSO/Email** button to sign.
* Once signed, the **Signature** field will auto-populate.

<img src="/.gitbook/assets/image (80).png" alt=""/>

**3. Register Application**

You will now see the **Total Price + VAT** and the **subscription period**.

* Click the **Register** button to propagate the signed message across the Flux network.
* If successful, a green confirmation message will appear in the top-right corner.
* Proceed to the **Test Application Installation** section.

<img src="/.gitbook/assets/image (81).png" alt=""/>

**4. Test Application Installation**

Before paying, it’s essential to verify that your app can install and launch successfully.

* Click the **Test Installation** button.
* Scroll down to view the live installation logs.

<img src="/.gitbook/assets/image (82).png" alt=""/>

**5. Payment**

Once your app passes the installation test, payment options will be unlocked. Links remain valid for **30 minutes**.

* **Available Methods:** Stripe (Credit/Debit Card), PayPal, or FLUX.
  * Pay with FLUX to receive a **5% discount**.

<img src="/.gitbook/assets/image (83).png" alt=""/>

***

After successful payment, deployment begins automatically. Your app typically deploys within **10–30 minutes**. Once live, it will appear under **Management > My Active Apps**. Learn more about managing deployed applications in the [**Management**](../../management/) section.

