# Update & Maintenance

Legacy FluxNodes require manual updates. Keep both your operating system and Flux software current to avoid downtime.

***

### Full System & Flux Update

```bash
sudo apt-get update -y
sudo apt-get --with-new-pkgs upgrade -y && sudo apt autoremove -y
cd ~/zelflux && git reset --hard origin/master && git pull
bash -i <(curl -s https://raw.githubusercontent.com/JKTUNING/Flux-Node-Tools/dev/flux_node_viewer.sh) node-update
pm2 restart flux watchdog --watch
```

***

### OS-Only Update

```bash
sudo apt update && sudo apt upgrade -y
sudo reboot    # if kernel or critical patches were applied
```

***

### Flux-Only Update

* If **auto‑update** is enabled in Watchdog, Flux will update automatically.
* To update manually via FluxOS UI:
  1. Navigate to `http://<nodeIP>:<port>` and log in with your ZelID.
  2. Go to **Flux Admin → Manage Flux**.
  3. Click **Update Flux**.

> 📅 Stay aware of upcoming enforcement dates—see `#maintenance-notices` on Discord.
