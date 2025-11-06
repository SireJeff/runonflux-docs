# Auto-Switch

The Auto-Switch feature is designed to help traditional PoW cryptocurrency miners at FluxCore transition smoothly to offering their machines for Proof-of-Useful-Work (PoUW) on FluxEdge. This feature allows miners to continue PoW mining while simultaneously offering their machines on FluxEdge, automatically switching off mining activities when a lease is initiated.

### **Understanding the Auto-Switch Feature**

#### **Overview**

The Auto-Switch feature enables seamless transitions between PoW mining and FluxEdge leases. When a machine is leased, the mining operations and its Overclocking (OC) profile stop. Once the lease ends, the default mining configuration resumes.

Note: This feature is available only to the account owner of the machine.

#### **Enabling Auto-Switch**

<img src="/.gitbook/assets/image (21) (1).png" alt=""/>

1. Locate the Toggle:
   * On the Mining Overview data table, find the toggle in the last column.
   * Hover over the toggle for a brief explanation.
2. Activate Auto-Switch:
   * Toggle this setting on to make your machine available on the marketplace even while it is mining.

#### **Important Settings for Efficient Use**

<img src="/.gitbook/assets/image (20) (1).png" alt=""/>

#### **Default Mining Configuration**

1. Accessing Machine Settings:
   * Click on the machine name in the Machine Overview.
2. Add Miner Configurations:
   * Set the asset to mine, software, mining pool, wallet, and GPU to be used.
   * Create multiple mining configurations as needed.
3. Set Default Mining Configuration:

<img src="/.gitbook/assets/image (19) (1).png" alt=""/>

* Click the rocket icon at the top of the My GPUs data table.
* A pop-up will appear with all mining configurations.
* Select the configurations to set as the default by checking the appropriate boxes.

The default mining configuration will activate during machine reboots or idle periods, such as when a lease ends.

#### **Setting Up a Default OC Profile**

* Ensure you have a default OC profile set up. Refer to the guide on OC profiles for detailed instructions.
* The default OC profile will automatically start with the default mining configuration.

Important: Ensure both the default mining configuration and the default OC profile are set before enabling the Auto-Switch feature. Starting a default mining configuration without an attached OC profile can be detrimental to the machine.

### **Example of an Auto-Switch Cycle**

1. Mining Configuration Active:
   * Your machine is mining with a FLUX miner configuration and the default OC profile applied.
2. Lease Initiated:
   * When someone rents your machine, the FLUX miner and the default OC profile stop.
3. During Lease:
   * If a default PoUW OC profile is set, it will apply during the lease period.
4. Lease Ends:
   * Upon lease completion, the default mining configuration and OC profile resume, continuing to mine FLUX until the machine is leased again.

This cycle ensures maximum efficiency with minimal idle time for your machine.

By following this guide, you can effectively utilize the Auto-Switch feature to manage your mining operations and leases seamlessly, ensuring optimal use of your machine's resources.
