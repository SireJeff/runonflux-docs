# How to Uninstall Rancher on Linux via Command

Follow these steps in the specified order to uninstall Rancher.

**1. Pull the Uninstall Script**

Run the following command to download and execute the uninstall script:

```sh
curl https://raw.githubusercontent.com/rancher/system-agent/main/system-agent-uninstall.sh | sudo sh
```

**2. Uninstall Rancher**

Run the following command to uninstall Rancher:

```sh
sudo rke2-uninstall.sh
```

**3. Remove Files**

Remove the specified directories and files with the following command:

```sh
sudo rm -rf /etc/ceph \
    /etc/cni \
    /etc/kubernetes \
    /etc/rancher \
    /opt/cni \
    /opt/rke \
    /run/secret/kubernetes.io \
    /run/calico \
    /run/flannel \
    /var/lib/calico \
    /var/lib/etcd \
    /var/lib/cni \
    /var/lib/kubelet \
    /var/lib/rancher \
    /var/log/containers \
    /var/log/kube-audit \
    /var/log/pods \
    /var/run/calico
```

_Note that reciving the error :sudo: rke2-uninstall.sh: command not found is normal after running the command means your rancher is already uninstalled and you are free to rejoin the cluster._



This guide should help you properly uninstall Rancher from your Linux system.



