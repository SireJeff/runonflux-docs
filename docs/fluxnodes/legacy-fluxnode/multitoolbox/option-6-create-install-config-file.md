# Option 6 – Create Install Config File

Collects all your node settings into a JSON config file for unattended installs.

***

### Why It Helps

* **Option 2** (Install Flux) will read this file and skip prompts
* Speeds up re‑installs and scaling to multiple nodes

***

### What You'll Need

* Identity Key (private key)
* Collateral TX ID & Output Index
* ZelID
* Discord Webhook & User ID (for Watchdog)
* UPnP gateway IP & API port (for multi‑node)

***

### How to Use

1. Select **6**.
2. Follow prompts and paste in each piece of information.
3. The script writes a config file to `~/fluxnode_install_config.json`.
