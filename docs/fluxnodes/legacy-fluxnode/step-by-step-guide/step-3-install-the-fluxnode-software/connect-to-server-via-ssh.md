# Connect to Server via SSH

Before installing FluxNode software, you’ll need SSH access to your server.

> 💡 **Note:** For the purpose of this guide, we’ll walk through the process using a **VPS server rental** scenario while configuring a **Cumulus FluxNode**. If you’re running FluxNode from home, steps may differ slightly. In this example, we’ll be using **PuTTY** as our SSH client to connect to the server.

***

### Why SSH?

SSH (Secure Shell) provides an encrypted terminal session between your workstation and the remote server. It’s the standard method for managing Linux servers.

***

### Supported Clients

* **macOS / Linux:** Built‑in `Terminal`
* **Windows:**
  * **PowerShell** or **Command Prompt**
  * **PuTTY** (GUI): [www.putty.org](https://www.putty.org)
  * Other **SSH and Telnet** clients

***

### Step-by-Step

#### 1. Obtain Your Server IP and Login Information

* **VPS:** Provided by your hosting company, usually via email.
* **Home:** Your public IP (Google _“my IP address”_).

<img src="/.gitbook/assets/SSH Login data.png" alt="" width="375"/>

#### 2. Open Your SSH Client

* Launch **Terminal** (macOS/Linux), **PowerShell** (Windows), or **PuTTY**.

#### 3. Connect to Your Server

* Enter your server’s **IP address**.
  * If the IP includes a `/value`, omit it and use only the IP (e.g., `91.99.182.157`).
* Leave **Port** set to `22`.
* Click **Open**.

<img src="/.gitbook/assets/Putty Login (1).png" alt=""/>

#### 4. Authenticate

* On first connection, click **Accept** to trust the host key.

<img src="/.gitbook/assets/Putty login 2.png" alt="" width="489"/>

#### 5. Log In

* When prompted, enter the username **root**.
* Enter the server password provided by your VPS provider.

#### 6. Change Your Password

Some VPS providers will automatically ask you to change your password on your first login, but others will not. If you are not prompted, you should change it manually for security.

```bash
passwd
```

You will be prompted to:

* Enter your **current password** (the one provided by your VPS provider).
* Enter a **new, secure password**.
* Confirm the new password.

<img src="/.gitbook/assets/change PW.png" alt=""/>

#### 7. Verify Login

You should see a prompt similar to:

```
root@servername:~$
```

or

```
ubuntu@servername:~$
```

<img src="/.gitbook/assets/Logged In (1).png" alt=""/>

***

❗ **If Your Connection Fails**

* Double‑check the IP address and username.
* Ensure port 22 is open and accessible in your server’s firewall or home router.
* Verify your ISP or provider allows SSH traffic.

***

Once connected, proceed to **Install OS Updates**.
