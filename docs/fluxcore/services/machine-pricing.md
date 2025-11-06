# Machine Pricing

The hourly pricing for your FluxCore Machine on the FluxEdge Marketplace is determined by a comprehensive formula that considers various critical factors. This formula assigns weights to specific machine specifications based on their impact on performance. Key considerations include benchmark scores, CPU cores, GPU performance, storage capacity, network speed, machine reliability, and operating system.

**Factors Influencing the Pricing Formula**

The following specifications are integral to the pricing formula:

* **TFlops (Tera Floating Point Operations per Second)**
* **VRAM Speed**
* **RAM Speed**
* **RAM Capacity (in GB)**
* **Storage Capacity (in GB)**
* **Disk Write Speed**
* **Network Upload and Download Speeds**
* **Machine Reliability in Completing Leases Successfully**
* **Operating System**

These parameters are normalized by evaluating the highest and lowest values globally within the network.

**Price Adjustment Mechanism**

To ensure fairness and accuracy, an additional system checks if the computed hourly price of a machine falls within a predefined minimum and maximum range. If the calculated price is outside this range, the system adjusts it to a realistic level. This mechanism helps correct anomalies caused by issues such as incorrect hardware detection and other irregularities.
