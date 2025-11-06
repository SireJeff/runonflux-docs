# Overclocking (OC) Profiles

**Introduction to Overclocking**

Overclocking is the process of pushing your hardware beyond its stock settings to boost performance. In FluxCore, an overclocking template is a configuration set designed to optimize your machine's performance.

### **Accessing OC Profiles**

1. Navigate to the Account tab located in the left-hand menu.
2. Click on the OC Profile tab to access your OC Profile overview.

<img src="/.gitbook/assets/image (18) (1).png" alt=""/>

#### **Machine-Based Overclocking Profiles**

OC Profiles in FluxCore are machine-specific. Use the selection box at the top of the screen to choose the machine you want to create or manage OC profiles for.

#### **Types of OC Profiles**

There are two types of OC Profiles:

* Mining Profiles: These are linked to your Proof of Work (PoW) mining activities.
* PoUW Profiles: These apply when your machines are on lease for Proof of Useful Work (PoUW) activities.

### **Creating an OC Profile**

If no OC Profiles have been created, you will see a prompt to create your first one.

<img src="/.gitbook/assets/image (17) (1).png" alt=""/>

1. Click the Add OC Profile button in the middle of the screen.
2. A pop-up will appear, detecting if your machine has NVIDIA or AMD GPUs.
3. Specify various settings such as:
   * Configuration Name
   * Lock Core Clock
   * Core Clock Offset
   * Memory Clock Lock
   * Memory Clock Offset
   * Power Limit
   * Fan Speed (among others, depending on your GPU)

#### **Inputting Values**

You can enter a single value for all GPUs or different values for each GPU, separated by spaces.

* Example for all GPUs: 150
* Example for individual GPUs: 0 100 0 80 (GPU0 = none, GPU1 = 100, GPU2 = none, GPU3 = 80)
* Setting the fan speed to 0 will enable automatic adjustment, where the fan speed changes based on load and heat.

### **Default Configuration Toggle**

The default configuration is applied when no other overclocking profile is selected at miner startup. If auto-switch is enabled between PoW and FluxEdge Leases, this configuration will start with your default mining configuration. Only one default configuration is allowed per machine.

_Note: Only the machine owner can set a default configuration. If you imported the machine via its hash and password, you do not have ownership rights._

### **Saving and Managing OC Profiles**

After entering your desired settings, click the Save button. The profile will appear in your OC profile list, with its values visible. You can delete or edit OC profiles later.

<img src="/.gitbook/assets/image (16) (1).png" alt=""/>

### **Setting OC Profiles**

To apply OC Profiles, navigate to the specific module:

#### **Mining Profiles**

<img src="/.gitbook/assets/image (15) (1).png" alt=""/>

1. Go to the Mining Module and open the Mining Overview Page.
2. Click the machine name you want to access.
3. In the My GPUs data table, click the Overclocking Symbol.
4. Set an OC Profile on the fly, which will remain active while the machine is online. The current default OC Profile will also be visible.
5. The OC Icon pop-up allows switching between temporary OC profiles and editing them. To create new profiles click the "New OC Profile" button or manage existing ones, return to the Account > OC Profile Page.

#### **PoUW Profiles**

<img src="/.gitbook/assets/image (14) (1).png" alt=""/>

1. Enter the Service Module and click on the machine name you want to access.
2. In the My GPUs data table, click the Overclocking Symbol.
3. Set an OC Profile on the fly, which will remain active while the machine is online. The current default OC Profile will also be visible.
4. The OC Icon pop-up allows switching between temporary OC profiles and editing them. To create new profiles or manage existing ones, return to the Account > OC Profile Page.

By following this guide, you can effectively manage and optimize your machines' performance using OC Profiles within FluxCore.
