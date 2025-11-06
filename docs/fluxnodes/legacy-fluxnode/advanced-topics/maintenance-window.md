# Maintenance Window

Understanding your FluxNode’s **maintenance window** is vital to avoid missing confirmations and falling behind in the reward queue. The maintenance window is the maximum time your node has to “check in” (confirm) with the Flux blockchain before it is considered offline.

***

### How It Works

**How It Works**

* **Flux block time:** 2 minutes per block
* **Node confirmation interval:** At least 120 blocks

A node “checks in” every time it confirms its status on-chain. If it fails to confirm within the maintenance window, it misses its slot and drops to the back of the queue.

***

### Manual Calculation

1.  Retrieve the **current block height** from any Flux explorer or via RPC:

    ```
    flux-cli getblockcount
    ```
2. Retrieve your node’s **last confirmed block height** (via logs or FluxNodeView).
3.  Plug into the formula:

    ```
    RemainingWindowMinutes = (120 - (currentBlockHeight - lastConfirmedHeight)) × 2
    ```
4. The result is the number of minutes left before your node must confirm again.

> **Example:**
>
> * Current height: 1500
> * Last confirmed: 1430
> * Difference: 70 blocks
> * Remaining window: (120 - 70) × 2 = 100 minutes

***

### Tools for Real-Time Maintenance Window

You don’t need to calculate manually—use one of these utilities:

| Tool                   | Command / URL                                                                                                 | Notes                                                     |
| ---------------------- | ------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------- |
| **FluxNodeView (CLI)** | `bash -i <(curl -s https://raw.githubusercontent.com/JKTUNING/Flux-Node-Tools/main/flux_node_viewer.sh) node` | Displays maintenance window in the "Nodes" section.       |
| **FluxNode App**       | https://fluxnode.app.runonflux.io/#/nodes                                                                     | Enter wallet address to view all nodes’ maintenance data. |
| **Telegram Bot**       | `@fluxstats_bot /mw <yourWalletAddress>`                                                                      | Returns maintenance windows for your wallet’s nodes.      |

> 🔄 If you manage multiple nodes, FluxNode App and Telegram Bot are ideal for a consolidated view.
