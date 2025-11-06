# Details

The Details tab is where you provide general information and configuration settings for your application.

***

### Overview

Use this section to define your app’s name, description, contact information, deployment locations, instance count, and other preferences.

<img src="/.gitbook/assets/Details.png" alt=""/>

### Version

* Shows you the version of the application specifications
* This is hardcoded and cannot be changed

### Application Name

* Must be at least **3 characters** long
* Allowed characters: **A–Z, a–z, 0–9**
* **No spaces or special characters** allowed

### Application Description

* Must be at least **3 characters** long

### Owner

* Displays the FluxID associated with your account.
* This is hardcoded and cannot be changed.

### Contacts (Optional)

* Enter a **public contact email** enclosed within brackets and enclose them in quotations., for example: `["test@gmail.com"]`. You will receive important notifications (e.g., app expiration).

> ⚠️ Contacts are **publicly accessible** via the FluxCloud API

**Upload to Flux Storage**

* Use the blue upload button next to the field to upload your contact information to Flux Storage
* This replaces parameters with a storage link (only the link is visible via API, and the content is not accessible)

### Allowed Locations (Optional)

Specify where your app can be deployed. You can select one or more by clicking the plus icon:

* Continents
* Countries
* Regions

### Forbidden Locations (Optional)

Specify where your app can be deployed. You can select one or more by clicking the plus icon:

* Continents
* Countries
* Regions

### Instances

Define how many **servers (instances)** will run your application

* **Minimum:** 3 (for redundancy and load balancing)
* **Maximum:** 100

### Period

Choose your app’s **subscription duration**

* from **1 week to 1 year**
* This is a **prepaid**, **non-refundable** period

### Static IP (Optional)

Toggle this on if your app requires a **static IP address**

* **Additional cost:** $0.40 USD

### Enterprise Application (Optional)

Enable this option if your app requires:

* **Private container images**
* **Secrets management**
* **Targeted deployment to specific nodes**
* **Additional cost:** $0.80 + $0.40 USD per **enterprise port**
* ⚠️ **Geolocation targeting is not supported** when Enterprise Application is enabled

***

Let’s continue to the next section, the Components section, to configure your application’s services and settings.
