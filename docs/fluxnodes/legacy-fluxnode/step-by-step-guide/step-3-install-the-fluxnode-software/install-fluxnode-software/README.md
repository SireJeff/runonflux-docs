# Install FluxNode Software

Flux provides a comprehensive **multitoolbox** script to streamline Docker installation, FluxNode setup, benchmarking, and service management. Follow the steps below to deploy your node.

> 💡 **Note:** For the purpose of this guide, we’ll walk through the process using a **VPS server rental** scenario while configuring a **Cumulus FluxNode**. If you’re running FluxNode from home, steps may differ slightly. In this example, we’ll be using **PuTTY** as our SSH client to connect to the server.

***

### Launch Multitoolbox

#### 1. Connect via SSH

* Ensure you’re logged in as `root` (or an admin user with `sudo` privileges).

<img src="/.gitbook/assets/Logged In.png" alt=""/>

#### 2. Download & Run Multitoolbox

```bash
bash -i <(curl -s https://raw.githubusercontent.com/RunOnFlux/fluxnode-multitool/master/multitoolbox.sh)
```

<img src="/.gitbook/assets/download multitoolbox.png" alt=""/>

#### 3. Welcome Screen

After the initial run, invoke the toolbox anytime with:

```bash
multitoolbox
```

<img src="/.gitbook/assets/Welcome (1).png" alt=""/>

***

### Next Steps

With the FluxNode Multitoolbox launched, follow these three steps to complete your setup:

1. **Install Docker (Option 1)** – Install Docker, create a non‑root user, and switch to it for improved security.
2. **Create Installation Configuration (Option 6)** – Generate your FluxNode configuration file with wallet and collateral details.
3. **Install FluxNode (Option 2)** – Install and configure Flux components, bootstrap the blockchain, and prepare your node for activation.
