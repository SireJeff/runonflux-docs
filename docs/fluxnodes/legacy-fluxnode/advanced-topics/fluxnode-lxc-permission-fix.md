# FluxNode LXC Permission Fix

When running your FluxNode inside an LXC container on Proxmox, you may encounter loop device permission errors when installing or running dApps. Follow the steps below on the **host** machine to resolve these issues.

***

### Increase Loop Device Limits

1.  Edit the GRUB configuration:

    ```
    sudo nano /etc/default/grub
    ```
2.  Find the line beginning with `GRUB_CMDLINE_LINUX_DEFAULT="..."` and add `max_loop=255`. For example:

    ```
    GRUB_CMDLINE_LINUX_DEFAULT="quiet splash max_loop=255"
    ```

    If other parameters are present, append `max_loop=255` after a space.
3. Save and exit (`Ctrl+O`, `Enter`, `Ctrl+X`).
4.  Update GRUB and reboot:

    ```
    sudo update-grub
    sudo reboot
    ```

***

### Expand Loop Devices in LXC Configuration

1.  On the host, open your container’s config file (replace `CTID` with your container ID):

    ```
    sudo nano /etc/pve/lxc/CTID.conf
    ```
2.  Add the following lines to allow unconfined AppArmor, full device access, and bind mounts for loop devices:

    ```
    lxc.apparmor.profile: unconfined
    lxc.cgroup2.devices.allow: a
    lxc.cap.drop:
    lxc.cgroup2.devices.allow: b 7:* rwm
    lxc.cgroup2.devices.allow: c 10:237 rwm
    ```
3.  Append bind mounts for each loop device you need (example for loop0–loop63):

    ```
    lxc.mount.entry: /dev/loop0 dev/loop0 none bind,create=file 0 0
    lxc.mount.entry: /dev/loop1 dev/loop1 none bind,create=file 0 0
    ...
    lxc.mount.entry: /dev/loop63 dev/loop63 none bind,create=file 0 0
    lxc.mount.entry: /dev/loop-control dev/loop-control none bind,create=file 0 0
    ```
4. Save and exit.

***

### Recreate (Privileged) Container

1. **Backup** the existing container in the Proxmox GUI.
2. **Remove** the container.
3. **Restore** from backup, ensuring **Privileged** mode is **enabled** (uncheck "Unprivileged").
4. **Start** the new container.

***

### Verify Device Availability

Inside the container, run:

```
ls -l /dev/loop*
```

You should see all configured `/dev/loop0`–`/dev/loop63` and `/dev/loop-control` entries.
