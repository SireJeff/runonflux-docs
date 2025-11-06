# Install FluxNode (Option 2)

This step installs and configures all FluxNode components. The Multitoolbox will prepare your server, bootstrap the blockchain, and finalize your node so it’s ready for activation.

***

### Detailed Step-by-Step Configuration

#### 1. Log in as Your New Non-Root User

* If your SSH session timed out, reconnect via **PuTTY** using your **non‑root username** and its password.

<img src="/.gitbook/assets/image (50).png" alt=""/>

#### 2. Open the Flux Multitoolbox

```
multitoolbox
```

* Enter your **sudo password** if prompted.

<img src="/.gitbook/assets/image (51).png" alt=""/>

#### 3. Select Installation Config File Option

* In the Toolbox menu, select **`2: Install FluxNode`**.
* Enter your **sudo password** again if prompted.
* The process may take up to **45+ minutes**—duration varies by connection speed.

***

### Installation Process

During installation, the following steps occur automatically:

#### **1. Preparing Your Server**

* Adds a **swap file** to improve performance.
* Installs required packages and dependencies.

#### **2. Installing Flux Components**

* Downloads and installs:
  * **fluxbench** (benchmark tool)
  * **fluxd** (daemon)
  * **flux-fetch-params** (zkSNARK params)
  * **flux-tx** (transaction tool)
* Configures the Flux daemon and imports the official GPG key.

#### **3. Restoring the Blockchain via Bootstrap**

* Tests download speeds from multiple CDN servers.
* Selects the fastest server to download the **bootstrap file**.
* Bootstrapping speeds up blockchain sync significantly.

<img src="/.gitbook/assets/Install FluxNode 2.png" alt=""/>

#### **4. Blockchain Synchronization**

* Starts the daemon and begins syncing with the blockchain.
* Displays messages such as:

```
Starting daemon & syncing with chain please be patient this will take about 5 min...
```

* **What to watch for:**
  * **Connections:** Check that the number of failed connections is ideally `0`.\
    If some failures occur, it’s usually fine as long as syncing continues.
  * **Progress:** Watch the **Left: X blocks** counter.\
    This shows how many blocks remain before your node is fully synced.
* **Time Estimate:** Depending on how many blocks need to be synced, this step can take **45–60 minutes**.\
  Please be patient and let it finish.

<img src="/.gitbook/assets/image (27).png" alt=""/>

#### **5. Installing Watchdog**

* Installs **Flux Watchdog** to monitor your node and ensure it stays online.
* Watchdog automatically restarts the daemon if it stops responding.

#### **6. Finalizing Installation**

* Creates final configuration files.
* Completes any remaining setup tasks.
* Displays:

```
Finalizing Flux installation please be patient this will take about ~5 min...
```

<img src="/.gitbook/assets/Install FluxNode 5.png" alt=""/>

#### **7. Installation Complete**

* Your FluxNode installation has successfully finished.
* You will see a completion message and be returned to the terminal prompt.
* At this stage, your node is ready for **final configuration and start-up**.

<img src="/.gitbook/assets/Install FluxNode 6.png" alt="" width="563"/>

***

### Verify Successful Benchmark

After installation completes, scroll up in the terminal until you see the **Flux Benchmark** results.\
You should confirm that it passed and is showing the correct **FluxNode tier** (CUMULUS, NIMBUS, or STRATUS).

<img src="/.gitbook/assets/Install FluxNode Benchmark passed.png" alt="" width="563"/>

**Check Benchmark Status:**

```bash
fluxbench-cli getbenchmarks
```

Possible results:

* **RUNNING** – Benchmark is still in progress.
* **FAILED** – Benchmark did not pass; see diagnosing steps.
* **CUMULUS / NIMBUS / STRATUS** – Benchmark passed successfully.

<img src="/.gitbook/assets/Install FluxNode Benchmark passed 2.png" alt=""/>

**Restart Benchmark if Needed:**

```bash
fluxbench-cli restartnodebenchmarks
```

> If your benchmark failed, rerun it using the above command.

***

**Next Step:** When your benchmark passed, proceed to **Step 4: Start Your FluxNode** to bring your FluxNode online.
