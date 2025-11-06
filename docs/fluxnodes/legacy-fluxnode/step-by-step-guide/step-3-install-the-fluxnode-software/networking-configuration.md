# Networking Configuration

Proper network configuration is critical for your FluxNode to communicate reliably with the Flux network. This section covers both **Single‑Node** and **Multi‑Node** setups.

> 💡 **Note:** For the purpose of this guide, we’ll walk through the process using a **VPS server rental** scenario while configuring a **Cumulus FluxNode**. If you’re running FluxNode from home, steps may differ slightly. In this example, we’ll be using **PuTTY** as our SSH client to connect to the server.

***

### Single-Node Configuration

#### Recommended: UPnP

1. **Reserve a Static IP**
   * In your router’s DHCP settings, assign a fixed local IP to your node’s MAC address.
2. **Disable Any Existing Port Forwarding**
   * Remove old rules to avoid conflicts.
3. **Enable UPnP on Your Router**
   * Consult your router’s documentation for enabling Universal Plug‑and‑Play.
   * Reboot the router after enabling.
4. **Configure the Node via Multitoolbox**
   *   SSH into your node and run:

       ```bash
       bashCopyEditmultitoolbox
       ```
   * Select **Option 14: UPnP Port Configuration**.
   * Choose an API port (start at **16127**, then increment if needed).

> 🛡️ FluxOS includes a built‑in UFW firewall that will automatically open the necessary ports once UPnP mapping is established.

#### Alternative: DMZ

If UPnP is unavailable, you may place your node’s IP in the router’s **DMZ** (demilitarized zone), exposing all inbound traffic to the node. FluxOS’s UFW will still manage and restrict ports appropriately.

> ❗ **Note:** As of FluxOS v4.0.0, **port forwarding is no longer recommended**. See [Release Notes v4.0.0](https://github.com/RunOnFlux/flux/releases/tag/v4.0.0).

***

### Multi-Node Configuration

The Flux network supports up to **8 nodes** per single external IP. For multi‑node setups, **UPnP is required**; DMZ and manual port‑forwarding are generally unreliable on consumer routers.

1. **Assign Static IPs**
   * Reserve a unique local IP for each node instance.
2. **Enable UPnP**
   * As per the single‑node steps above.
3. **Configure Distinct API Ports**
   * For each node, run **Option 14: UPnP Port Configuration** in multitoolbox.
   * Assign a different API port to each node (e.g., 16127, 16128, … 16134).

> 💡 Ensure each node’s API port is unique to avoid address conflicts in UPnP mappings.
