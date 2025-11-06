# Local Storage

Local Storage enables deployment data to persist throughout the duration of a lease. By creating a volume on the provider's disk and mounting it to the deployment, this feature provides functionality similar to traditional container storage.

***

#### Key Features

* Persistent During Lease: Data remains accessible for the entire duration of the lease.
* Volume-Based Storage: A dedicated volume is created for the deployment, ensuring isolation and reliability.

#### Limitations

1. Storage Duration

* Storage exists only for the lease's lifetime.
* If the deployment is:
  * Migrated to another provider, the storage is lost.
  * Stopped or relaunched, even on the same provider, the data does not persist across leases.

2. No Shared Volumes

* Shared volumes are unsupported.
* If a deployment defines persistent storage for a single profile shared across multiple containers, each container will have its own unique volume.

3. Single Volume Per Container

* Each container can have only one persistent volume.
* It is not currently possible to mount multiple volumes to a single container.

#### Local Storage via BUILDER

When deploying through the BUILDER interface (Quick Launch):

* Default Configuration:
  * Each quick launch deployment has the Local Storage tile enabled by default.
  * A default mount path is provided, which can be overwritten as needed.
  * For deployments with multiple containers, each container receives its own mount path.
* Type Selector:
  * Acts as a filter for the machine lease list based on the provider's system disk type.
  * Useful for selecting faster disk drives like NVMe.
  * Only providers capable of delivering the specified storage type will appear in the lease list.
* Automatic Injection:
  * All provided values are automatically injected into the Kubernetes YAML file before deployment.
