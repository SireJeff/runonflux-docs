# How to Install Arcane OS

This section will guide you through the installation of **Arcane OS**—the operating system purpose-built for running FluxNodes with enhanced security, privacy, and performance. Whether you’re deploying on physical hardware (bare metal) or in a virtual machine (VM), this guide will ensure you meet all requirements and complete installation correctly.

> ⚠️ **Note:** Arcane OS is currently only available for AMD64 (x86‑64) systems.

***

### Getting Started

To install and monitor FluxNodes using Arcane OS, you’ll need one of the following wallets:

* **ZelCore Wallet**
* **SSP Wallet**

> ⚠️ **This guide specifically focuses on installing Arcane OS** for running home-based FluxNodes. VPS usage is limited due to current Secure Boot constraints (see below).

***

### System Requirements

#### Hardware Specifications by Node Tier

Here’s the official recommended hardware for running FluxNodes at each tier, as of the most recent guidelines:

<table><thead><tr><th width="112.4444580078125">Node Tier</th><th>Collateral</th><th width="127.9998779296875">CPU</th><th width="86.888916015625">RAM</th><th>Storage</th><th>Bandwidth</th></tr></thead><tbody><tr><td><strong>Cumulus</strong></td><td>1,000 FLUX</td><td>2 vCores / 4 Threads</td><td>8 GB</td><td>220 GB SSD or NVMe</td><td>≥ 25 Mbit/s</td></tr><tr><td><strong>Nimbus</strong></td><td>12,500 FLUX</td><td>4 vCores / 8 Threads</td><td>32 GB</td><td>440 GB SSD or NVMe</td><td>≥ 50 Mbit/s</td></tr><tr><td><strong>Stratus</strong></td><td>40,000 FLUX</td><td>8 vCores / 16 Threads</td><td>64 GB</td><td>880 GB SSD or NVMe</td><td>≥ 100 Mbit/s</td></tr></tbody></table>

#### Additional Requirements for Arcane OS

Running Arcane OS introduces a few more requirements on top of the above hardware specs:

| Feature            | Bare Metal Hardware                 | Virtual Machine (VM)                                                           |
| ------------------ | ----------------------------------- | ------------------------------------------------------------------------------ |
| **TPM 2.0**        | Required (physical or onboard chip) | Required (must configure a _virtual TPM_)                                      |
| **UEFI Boot Mode** | Must be enabled in BIOS             | VM must be set to UEFI boot mode                                               |
| **Secure Boot**    | Not required                        | Required for VPS installation (note: few VPS providers currently support this) |

> 🔸 Most modern motherboards come with TPM 2.0 and UEFI support enabled by default.

#### Network Requirements for Home Based FluxNodes

* Your router supports **DMZ** or **UPnP**
* You can host **up to 8 nodes** on the same network
* If running more than one node, **UPnP must be enabled**

#### Additional Notes

* Arcane OS is only available on **AMD64 (x86-64)** architectures.
* If required features (TPM, UEFI, Secure Boot) are missing, the installer will display a warning and prevent installation.
* For VPS deployments, **Secure Boot support is generally unavailable**, making most hypervisors incompatible for Arcane OS at present.

***

### Download the ISO

You can always get the latest Arcane OS ISO from the official Flux image repository:

* **Browser:** [https://images.runonflux.io/latest](https://images.runonflux.io/latest)
* **Terminal (SSH):**

```bash
curl -JO https://images.runonflux.io/latest
# or
wget --content-disposition https://images.runonflux.io/latest
```

#### Create a Bootable USB (For Bare Metal Installations)

If you're installing Arcane OS on physical hardware, you'll need to flash the ISO to a USB stick.

**Recommended Tools**

* **Balena Etcher** (macOS & Windows): https://etcher.io
* **Rufus** (Windows only): https://rufus.ie
