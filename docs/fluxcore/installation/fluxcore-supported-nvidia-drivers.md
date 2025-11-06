# FluxCore Supported NVIDIA Drivers

Fluxcore requires specific versions of the **NVIDIA GPU driver** to run correctly. Using a supported driver ensures stability, compatibility, and optimal performance when running FluxCore.

This page lists all **officially supported NVIDIA drivers**, separated by **Windows** and **Linux**, and grouped by version series (e.g., 550, 560, etc.).

> ⚠️ **AI Benchmarks** and **Service Mode** (offering your machine to the marketplace) may **not be supported on all driver versions**.\
> For the best experience with these features, we **recommend using the 550 series** drivers marked by recommended in the list⭐.&#x20;

### 🖥️ Windows Supported Drivers

These drivers are tested and validated on **Windows**. Use the versions below to ensure compatibility with Fluxcore.

| Driver Series | Supported Versions                             | GPU Detection | Mining | Recommended |
| ------------- | ---------------------------------------------- | ------------- | ------ | ----------- |
| 538           | 538.78, 538.95                                 | ✅             | ✅      |             |
| 545           | 545.29.06                                      | ✅             | ✅      |             |
| 546           | 546.65                                         | ✅             | ✅      |             |
| 551           | 551.23, 551.52, 551.61, 551.76, 551.86         | ✅             | ✅      |             |
| 552           | 552.12, 552.22, 552.44, 552.55, 552.74, 552.86 | ✅             | ✅      |             |
| 553           | 553.09, 553.24, 553.35                         | ✅             | ✅      |             |
| 555           | 555.85, 555.99                                 | ✅             | ✅      |             |
| 556           | 556.12                                         | ✅             | ✅      |             |
| 560           | 560.70, 560.81, 560.94                         | ✅             | ✅      |             |
| 561           | 561.09                                         | ✅             | ✅      |             |
| 565           | 565.90                                         | ✅             | ✅      |             |
| 566           | 566.03, 566.14, 566.36                         | ✅             | ✅      |             |
| 572           | 572.16, 572.42, 572.47, 572.60, 572.70, 572.83 | ✅             | ✅      | ⭐ Yes       |
| 575           | 575.51.02                                      | ✅             | ✅      |             |
| 576           | 576.02, 576.28, 576.40, 576.52, 576.80, 576.88 | ✅             | ✅      |             |



***

### 🐧 Linux Supported DriversThese drivers are officially supported on **Linux distributions**. If you’re running Fluxcore on Linux, please ensure your system is using one of the versions below.

<table><thead><tr><th width="137.3333740234375">Driver Series</th><th width="236.333251953125">Supported Versions</th><th width="136.6666259765625">GPU Detection</th><th width="95.9998779296875">Mining</th><th width="146.3333740234375">Recommended</th></tr></thead><tbody><tr><td><strong>470</strong></td><td>470.182.03, 470.199.02, 470.223.02, 470.239.06, 470.256.02</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>510</strong></td><td>510.60.02, 510.108.03</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>515</strong></td><td>515.86.01, 515.105.01</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>525</strong></td><td>525.60.11, 525.78.01, 525.85.05, 525.89.02, 525.105.17, 525.116.03, 525.116.04, 525.125.06, 525.147.05</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>530</strong></td><td>530.30.02, 530.41.03</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>535</strong></td><td>535.43.02, 535.54.03, 535.86.05, 535.98, 535.104.05, 535.113.01, 535.129.03, 535.146.02, 535.154.05, 535.161.07, 535.161.08, 535.171.04, 535.179, 535.183.01, 535.183.06, 535.216.01, 535.216.03</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>538</strong></td><td>538.78</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>545</strong></td><td>545.23.06, 545.29.02</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>550</strong></td><td><pre><code>550.100, 550.107.02, 550.120,
550.127.05, 550.127.08, 
550.135, 550.144.03, 550.163.01
</code></pre></td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>555</strong></td><td>555.42.02, 555.52.04, 555.58, 555.58.02</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>560</strong></td><td>560.28.03, 560.31.02, 560.35.03, 560.35.05</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>565</strong></td><td>565.57.01, 565.77</td><td>✅</td><td>✅</td><td></td></tr><tr><td><strong>570</strong></td><td><p></p><pre><code>570.124.04, 570.133.07, 570.133.20,
570.144, 570.153.02, 570.158.01, 
570.169, 570.86.15, 570.86.16, 
570.124.06, 570.148.08
</code></pre></td><td>✅</td><td>✅</td><td>⭐ Yes</td></tr></tbody></table>

***

### ℹ️ Not Sure Which Version You Have?

To check your current NVIDIA driver version:

#### **Windows**

1. Open Command Prompt.
2. Type: `nvidia-smi`
3. Press Enter — the version will show under "Driver Version".

#### **Linux**

1. Open Terminal.
2. Type: `nvidia-smi`
3. Press Enter — you'll see your current driver version listed.

***

### 📥 Need Help Updating?

If your driver isn't supported:

* Visit the [official NVIDIA driver download page](https://www.nvidia.com/Download/index.aspx)
* Choose your GPU model and operating system
* Download and install a supported version listed above

