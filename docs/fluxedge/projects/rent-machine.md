# Rent Machine

You can rent a machine in two ways: by selecting what to deploy first, or by renting a machine and deciding what to deploy afterward. Renting a machine first offers the flexibility to filter by specific requirements if you already know what you need.

To access the Rent Machine UI, navigate to it using the menu tab.

On the Rent Machine UI, you'll find three machine types: Premium, Dedicated GPU, and Dedicated CPU. You can switch between these options using the corresponding tabs.

### Dedicated CPU and GPU

* Dedicated CPU machines do not have a GPU. These machines are suitable for CPU-only tasks or cases where the GPU is not yet supported by the GPU operator working with Kubernetes. We continuously work to support more GPU variants by keeping up with new GPU operator updates.
* Dedicated GPU machines come equipped with a GPU, which can be leveraged for GPU-intensive tasks.

Both machine types offer filters such as System, Region, Price Range, and more, allowing you to narrow down your search. There are also advanced filters that let you refine the search further, such as specifying GPU VRAM, CPU cores, or network speeds.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3iCFwymuUM9dGdjvGUgVeToZ6zDbjqLgE6Jvyzs5od1P55mqmRbKY_ztJmGWPx6DyIfE52i8DgtjiufFsMv0lOP-yLlJWHEZNRhSGOJIZqrn_pIdGkAsRYstFUbgFQSRMmdgLQg?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt="" width="188"/>

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXelmFWfiKH1A6uqxLR5pqtL4u3Pxd-WXKLFklDL2PxozTt7bLjt8o4elFqISE0CZtn00FiMdAZ_h4TL2lv8NvIGMFQ0TL_BdDp0zFRbHPEu58JAEqYI_JHyBxnxU1wmcrQDdGWpQA?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt="" width="375"/>

If you have favorite machines, you can quickly filter for them with a single click. For Dedicated GPU machines, you can filter by GPU model (e.g., Nvidia RTX 4090).

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXfgv2fj7aN41NOWkaLaDP9XrkB5-xOkn7c_QTMMblgjl0drRWsrv2oZNHh_AWj6TgxldbKc7sWZ3YqhT-ocvK5ZdZqJfW1WoSZzzGxynBhAOfJEY5eoZTN3B_7Xjmmdxq7G7KQd3Q?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt="" width="375"/>

To rent either a Dedicated CPU or GPU machine, simply select the machine you need, click the Rent button at the top right, and confirm your selection in the confirmation popup.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXe390MuY8nTUhJQN_5KKLisBFP8HpVtDWqeDkChPoknEGhQCMe2H79T207Pj4K05pmsEhuelHLAvig1IjcZidyDeiCReczYbeaXg-VWsRKn96vmwBLcdbNUqCRhQOGZFYaGpgnrTg?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt="" width="375"/>

***

### Premium - High-Performance Machines

Our Premium machine offerings are sourced from trusted third-party providers, such as **Hyperstack**, an NVIDIA partner. These machines are equipped with cutting-edge **NVIDIA H100**, **A100**, and next-generation Blackwell GPUs, designed for demanding workloads like large-scale simulations, deep learning, and advanced data processing. By partnering with industry leaders, we ensure top-tier performance, scalability, and reliability.

To rent a Premium machine, your account must be at the **KYC1** level. This can be unlocked by making a fiat deposit using either Stripe or PayPal.

Once your account is verified, you can access the Premium Machine tab and choose from enterprise-grade GPUs provided by our trusted partners.

#### Renting a Premium Machine

When renting a Premium machine, you'll follow these steps:

1. Select the **GPU type and quantity**.
2. Choose the **hardware specifications**. Some providers may offer different specs depending on the GPU chosen.
3. Select the **server location**.
4. Specify the **number of machines** you wish to rent.
5. Choose the **rental duration**. Some providers follow a "pay-as-you-go" model, meaning you pay as long as the machine is running. Others may allow you to specify the rental period, with potential discounts for longer commitments.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXc6JhrnuVLjh_sE74Lxi0yBZZZSvrlKKGn4JlQz50bURL8hx0pMQuzhF6cr5aGDy5WKHllTYouGY7D93f3hUtjUgfchXVR6_JImsPEfDy3t7hUBbbS8tDFvO10EWMHcF3K9Ooq7?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt=""/>

After selecting your preferences, you'll see the price per hour, along with any additional costs, such as a one-time startup fee.

Once all selections are made, confirm your rental by clicking the Rent button and accepting the terms in the confirmation popup. You will be asked to agree to the terms and conditions of both InFlux Technologies and the provider.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdler4oKz0TKGbHM0qoieHKjksmjE5l2zSYYgC8yH4HbqYY70CmjrGcM2FhA8bHdr6F7FV9NmAkKudFKCVHUqWn1U0cG5AKkMQLcCW5uiCniCYkf_cL8YZvs4DccoxU8cxYxQyEJw?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt="" width="375"/>

#### Premium Machine Status Lifecycle

Once you confirm the rental, your machine will appear in the machine overview screen in the Provisioning state. Here's an overview of the provisioning process:

1. **Provisioning**: The machine is being set up by the provider. This may take a few minutes.
2. **Provisioning - Installing FluxCore**: The machine is fully set up and is now installing FluxCore to interact with the FluxEdge front-end.
3. **Provisioning - Configuring Cluster**: After FluxCore is installed, the machine will join a Kubernetes cluster.
4. **Provisioning - Installing GPU Operator**: The machine has joined the cluster and is installing necessary components, such as GPU operator pods.

<img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXek5H1xx6ZksjokPr8gEVuopj2GcW2870kPfO41X9LaAuxG1DEm1YGVTKziF7lSxjsq6Mkk6yqod33AJ-9cc0yOL_2DNJPwUDvwVpwSxzPiJXsU-F3Tikcwq_aCx8vQ6rzjaD7JAw?key=nPUrKJM9J8YVM6Z1WOhzPzNQ" alt=""/>

The entire setup process can take up to **30 minutes**, depending on the GPU, hardware specifications, and network conditions. However, in most cases, it should not take longer than **10 minutes**.

Once all phases are complete, the machine is fully functional and can be controlled like any other machine rented via FluxEdge. You can stop the machine, deploy apps via Quick Launch, or customize deployments as needed.

\
