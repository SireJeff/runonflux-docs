# Linux Installation

## FluxCore Installation Guide for Linux

Welcome to the **FluxCore Installation Guide**.\
This guide will walk you through everything needed to get FluxCore running properly on Ubuntu. Please follow each step carefully missing a package or installing them in the wrong order can cause GPU detection and benchmarking issues.

***

### ⚙️ System Requirements

* **OS**: Ubuntu 22.04 (Desktop or Server)
* **GPU Drivers**: NVIDIA 570 series (or AMD 23, coming soon).

> ⚠️Note:\
> Do **not** use Ubuntu 22.04 Minimal it is missing required dependencies for FluxCore.

***

### Step 1. Install GPU Drivers

#### NVIDIA

Update your system:

```bash
sudo apt update && sudo apt upgrade -y
```

Install the correct driver depending on your Ubuntu edition:

* **Ubuntu Server**

```bash
sudo apt install nvidia-driver-570-server
```

* **Ubuntu Desktop**

```bash
sudo apt install nvidia-driver-570
```

> ⚠️Note:\
> The above command installs the **latest version** in the 570 branch.\
> Check the official [FluxCore Supported NVIDIA Drivers list](https://docs.runonflux.com/flux/fluxcore/installation/fluxcore-supported-nvidia-drivers) to confirm compatibility before proceeding.

***

### Step 2. Install CUDA (Required for GPU Benchmarking)

Both CUDA toolkits must be installed **before FluxCore**.\
If installed afterward, FluxCore will not detect your GPU for benchmarks you’ll need to reinstall FluxCore.

Run these commands in order:

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get install -y nvidia-cuda-toolkit
sudo apt install -y cuda-toolkit-12-8   # Different from nvidia-cuda-toolkit, don't skip this!
```

> ⚠️Note:\
> The `cuda-toolkit-12-8` package is separate from `nvidia-cuda-toolkit`.\
> Forgetting to install it will cause GPU benchmarks to use CPU to benchmark.

***

### Step 3. Install FluxCore

Run the FluxCore setup script:

```bash
bash -i <(curl -s https://download.fluxcore.ai/setup.sh)
```

<img src="/.gitbook/assets/image (19).png" alt=""/>

\
During installation:

1. Enter **`1`** to install prerequisites.
2.  Provide your **sudo password** when prompted.\
    &#x20;

    <img src="/.gitbook/assets/image (20).png" alt=""/>
3. Select your machine’s **local IP address** when asked.

Example: If you choose `192.168.1.100`, the UI will be available at that ip if you access it on the same machine if you want to access from another machine either use [https://app.fluxcore.ai/](https://app.fluxcore.ai/) or [accessing machine from another PC locally](https://docs.runonflux.com/flux/fluxcore/machines/connecting-to-your-fluxcore-server-from-another-pc-on-your-local-network-without-installation)

```
http://192.168.1.100:18180
```

***

### Step 4. Save Machine ID & Password

During **Step Two (Register Machine)**, you will be prompted to download a file containing your **Machine ID** and **Password**.

<img src="/.gitbook/assets/image (21).png" alt=""/>

<img src="/.gitbook/assets/image (22).png" alt=""/>

> ⚠️Note:\
> Save this file — you may need it later to:
>
> * Reconnect to FluxCore
> * Manage your system remotely from another FluxCore GUI

***

### **Step 5.  Sign up on FluxCoreWEB**

Now go to [https://app.fluxcore.ai](https://app.fluxcore.ai/) and signup for an SSO account.

<img src="/.gitbook/assets/image (16).png" alt=""/>

### **Step 6 Add Machine to your account**

Now procceed and click "Add new Machine" and you will prompted for your Machine hash and the machine password you downloaded in the previous step

<img src="/.gitbook/assets/image (18).png" alt=""/>

### **Step 7 Connect to the Machine**

**Select the machine you want to connect to and click "Connect Now" and you can now fully access your machine from anywhere.**

### ⚠️ Notes & Troubleshooting

* Installing CUDA _after_ FluxCore requires a **FluxCore uninstall -> reinstall** for GPU benchmarking to work.
* Using unsupported drivers may cause issues with:
  * Benchmarks
  * Mining
  * GPU detection on the marketplace

***

✅ That’s it! FluxCore should now be installed and running smoothly on your system.

***
