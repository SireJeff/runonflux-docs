# Linux Headless Installation

## Welcome to the FluxCore Headless Installation Guide for Linux

We're excited to help you get started with FluxCore on your Linux machine. Whether you're a seasoned Linux user or just getting started, this guide will walk you through the installation process smoothly. This guide is perfect for installing multiple computers quickly

### Prerequisites to run FluxCore

* You must have an SSO (Single Sign On) account already on Fluxcore or Fluxedge.
* [Signup for SSO (Single Sign On)](https://app.fluxcore.ai/auth/register).
* Ubuntu OS
* Graphic Card Driver

**Overview:** You can use Ansible or a custom script to install several machines at once. This guide covers the installation process for a single computer without scripts.

**Important Note:**

* You will not receive a password for your machine using this method, meaning you cannot share the machine with multiple accounts.

## Step-by-Step Installation

### 1. Sign up for a SSO account

To get started, you’ll need an SSO (Single Sign-On) account on **FluxCore** or **FluxEdge**.
If you don’t have one yet, [sign up here](https://app.fluxcore.ai/).

**Note:** Your SSO **email address** will be used as a flag when running the installation command to join the cluster.

### 2. Install Ubuntu OS

We officially recommend using Ubuntu 22.04 (Desktop or Server) for the best experience. While earlier versions of Ubuntu might work, they haven’t been thoroughly tested, so you may run into some unexpected challenges.

### 3. Install Graphic Card Driver and CUDA

To ensure a smooth installation, make sure you install the recommended graphics card drivers and CUDA on your Ubuntu system before setting up FluxCore. This step is crucial to avoid any hiccups down the road. The recommended version for AMD is being added here soon.

**NVIDIA: Version 570**

```bash
sudo apt update && sudo apt upgrade -y
```

**Ubuntu Server:**

```bash
sudo apt install nvidia-driver-570-server
```

**Ubuntu Desktop:**

```bash
sudo apt install nvidia-driver-570
```

> ⚠️ **Note:** This command always installs the latest version within the 570 driver branch in the repo, which might not yet be supported by FluxCore. Please refer to the official [FluxCore Supported NVIDIA Drivers](https://docs.fluxedge.ai/fluxcore/fluxcore-supported-nvidia-drivers) for the most up-to-date compatibility list before proceeding.

**CUDA:**

```bash
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt-get update
sudo apt-get install -y nvidia-cuda-toolkit
sudo apt install cuda-toolkit-12-8
```

_**Important Note:**_

_Choosing a different driver version for your system should be done with caution. Doing so may result in potential issues with certain FluxCore services, such as:_

* _Benchmarking_
* _Mining_
* _GPU detection on the marketplace_

_Ensure you understand the risks before proceeding with a driver change, as it could affect the performance and functionality of your system within the FluxCore ecosystem._

### 4. Run the install script

Run the following command to bind your machine to your SSO account:

```bash
bash -i <(curl -s https://download.fluxcore.ai/setup.sh) -i 192.168.1.100 youremail@mail.com -cluster default
```

* Replace `192.168.1.100` with your machine's local IP address and `youremail@mail.com` with your registered email address.
* The -cluster default flag makes you join your regions cluster after the setup has finished.

After running this command, your machine should appear on your Fluxcore dashboard, which can be accessed from [fluxcore](https://app.fluxcore.ai/auth/login?redirect=/) website UI.
**Change the Owner Email of a Machine (if needed)**

If you need to change the owner email of your machine, use the following command:

```bash
bash -i <(curl -s https://download.fluxcore.ai/setup.sh) -email yournewowner@mail.com
```

_Ensure that the new email address you are replacing with is associated with an SSO account on Fluxcore or Fluxedge._

***
