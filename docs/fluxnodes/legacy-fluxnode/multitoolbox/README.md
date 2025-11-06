# Multitoolbox

The **Multitoolbox** is a consolidated suite of scripts designed to **install**, **manage**, and **diagnose** your FluxNode. It simplifies complex tasks into menu‑driven options, so whether you’re setting up Docker, repairing your blockchain data, or configuring advanced services like Watchdog, Multitoolbox has you covered.

> ℹ️ You will use Multitoolbox frequently—familiarizing yourself with its options will streamline node operations and troubleshooting.

***

### Launching Multitoolbox

From your server's command line, run:

```bash
bash -i <(curl -s https://raw.githubusercontent.com/RunOnFlux/fluxnode-multitool/master/multitoolbox.sh)
```

After the initial download, you can simply type:

```bash
multitoolbox
```

to access the menu at any time.

***

### Menu Options

Below is a quick reference to the primary Multitoolbox options. Subsequent sections will dive into each one in detail.

| Option | Name                       | Purpose                                                                                   |
| ------ | -------------------------- | ----------------------------------------------------------------------------------------- |
| **3**  | Analyzer & Fixer           | Runs diagnostic checks and attempts automatic remediation of common node issues           |
| **4**  | Install Watchdog           | Installs the Watchdog service for automatic self‑healing and alerting                     |
| **5**  | Restore Flux Blockchain    | Re-syncs or repairs your local blockchain data using a fresh bootstrap snapshot           |
| **6**  | Create Install Config File | Collects your node credentials (keys, TX IDs, indices, Zel ID, KDA address) into a config |
| **7**  | Re‑Install Flux OS         | Performs a clean re-install of FluxOS components while preserving your configuration file |
| **8**  | Daemon Configuration       | Adjusts Flux daemon settings (e.g., peers, ports, service parameters)                     |
| **11** | Reconfigure Flux OS        | Re-runs setup steps (networking, SSH, notifications) without reinstalling the OS          |
| **13** | MongoDB Repair             | Repairs or rebuilds the MongoDB data used by FluxOS for analytics and app services        |
| **14** | Enable Multi‑Node (UPnP)   | Configures UPnP mappings for running multiple nodes on one external IP                    |

***

By mastering these Multitoolbox options, you’ll be able to perform complex maintenance tasks in just a few keystrokes. Next, explore each option in depth to understand its workflows, prompts, and best‑practice usage.
