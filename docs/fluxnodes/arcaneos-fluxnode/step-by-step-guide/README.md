# Step-by-Step Guide

This guide walks you through installing and configuring Flux Arcane OS in a virtualized environment. While we illustrate using **Proxmox Hypervisor v8.4.1**, the same workflow—with minor UI variations—applies to other platforms such as Oracle VirtualBox.

ℹ️ **Tested Compatibility**

* ✅ **Proxmox 8.4.1** – Fully supported and tested
* ✅ **Oracle VirtualBox (Windows)** – Very similar process
* ⚠️ **VMware v16** – Encountered issues during testing
* ✅ **VMware v17** – Reported working by the community

***

### High-Level Steps

1. **Create a Virtual Machine**\
   Provision a VM with UEFI, TPM 2.0, and resource allocations matching your chosen FluxNode tier (Cumulus, Nimbus, or Stratus).
2. **Install Arcane OS**\
   Boot the Arcane OS installer, configure keyboard, hostname, console user, networking, UPnP ports, and encrypted storage, then reboot.
3. **Enroll Platform Key (PK)**\
   Enter your UEFI/OVMF firmware to import the Flux Platform Key (`pk.der`), enabling Secure Boot for Arcane OS.
4. **Configure Your FluxNode**\
   From the Launch Screen, access the web UI (URL or QR code) and choose a configuration method: Manual, ZelCore Token, or SSP Token.
5. **Configure Notifications**\
   (Optional) Set up Discord or Telegram webhooks to receive real‑time node alerts.
6. **Configure SSH Access**\
   Enable the `operator` account via a generated or existing ed25519 keypair, and define any ports or package repositories to block.
7. **Confirm Settings**\
   Review and save your configuration, upload to Flux Storage or download as JSON/YAML, then apply your settings.
8. **Finalizing the Configuration**\
   Watch the Metrics Dashboard appear, monitor blockchain sync progress, and once complete, start your node from your wallet.
9. **Access the System**\
   Use the in‑browser Shell Console or SSH (if enabled) for ongoing maintenance, and reconfigure at any time via the Settings menu.
