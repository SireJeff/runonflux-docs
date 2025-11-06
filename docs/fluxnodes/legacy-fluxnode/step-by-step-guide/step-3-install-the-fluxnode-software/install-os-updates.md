# Install OS Updates

Before deploying the FluxNode software, it’s critical to bring your operating system fully up to date with the latest security patches and package improvements.

> 💡 **Note:** For the purpose of this guide, we’ll walk through the process using a **VPS server rental** scenario while configuring a **Cumulus FluxNode**. If you’re running FluxNode from home, steps may differ slightly. In this example, we’ll be using **PuTTY** as our SSH client to connect to the server.

***

### Why Update?

* **Security:** Protects against known vulnerabilities.
* **Stability:** Ensures compatibility with recent libraries and dependencies.
* **Performance:** May include kernel and driver improvements.

***

### Step-by-Step

#### 1. Connect via SSH

* Ensure you’re logged in as `root` (or an admin user with `sudo` privileges).

<img src="/.gitbook/assets/Logged in.png" alt=""/>

#### 2. Update Package Lists & Update

* Run the following command:

```bash
sudo apt update && sudo apt dist-upgrade -y
```

* **`apt update`** refreshes the package index.
* **`apt dist-upgrade`** installs all available updates and handles any package dependencies.

#### 3. Wait for Completion

* The system will download and install updates.
* This may take several minutes, depending on your server’s resources and network speed.

#### 4. Verify

* Once finished, you’ll return to the prompt:

```bash
root@servername:~$
```

* Optionally, reboot to apply kernel updates:

```bash
sudo reboot
```

<img src="/.gitbook/assets/Completed.png" alt=""/>

***

Once the OS is updated, proceed to **Networking Configuration** if you’re using a home-based server, or to [**Install FluxNode Software**](install-fluxnode-software/) if you’re using a VPS.[\
](https://app.gitbook.com/o/8NHLg7ON9cIrTU7B1B9f/s/HLuudQmOf7brj6Q46ncV/fluxnodes/legacy-fluxnode/step-by-step-guide/step-3-install-the-fluxnode-software)
