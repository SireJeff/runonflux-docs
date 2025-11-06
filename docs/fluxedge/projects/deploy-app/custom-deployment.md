# Custom Deployment

### **Creating a Custom Deployment**

**Navigate to Custom Deployment:**

* From the left-hand menu, click on "Custom Deployment."
* Alternatively, select the "Custom Deployment" option when creating a new project via the Projects Overview tab.

<img src="/.gitbook/assets/Overview (3).png" alt=""/>

#### **Using the Deployment Builder**

Upon accessing the custom deployment UI, you will be directed to the builder option by default. This tool allows you to customize your deployment using user-friendly building blocks tailored to your specific needs.

<img src="/.gitbook/assets/Overview (10).png" alt=""/>

#### **General Settings**

* Name: Enter your project name.
* Docker Image: Specify your Docker image repository. Supported repositories include Docker Hub, GitHub, Google, and more.

#### **Connectivity Settings**

* Ports: List all necessary container ports. Specify the corresponding public ports and select the internet protocol suite (e.g., TCP or HTTP). To add more ports, click the "+ Add Port" button.
* Domains: Attach your deployment or specific ports to domains, separating multiple domains with commas.

#### **Customization Settings**

* Environments: Initially empty, this section allows you to add environmental parameters. Click the "Edit" button to set KEY and VALUE pairs. Use the "+ Add Variable" button to add more parameters.
* Commands: Also initially empty, this section allows you to add commands and their arguments. Click the "Edit" button to enter commands, with each command row linked to its argument row. Use separate lines for new commands and arguments.

#### **Resource Allocation**

Specify the resources for your deployment and its Kubernetes pod:

* CPU (Cores)
* RAM
* Ephemeral Storage

To leverage a GPU, check the GPU box and select the GPU count, manufacturer (e.g., NVIDIA or AMD), and model. To add more containers to the deployment, click the "Add Container" button and specify the new container's information.

#### **YAML Configuration**

Next to the builder, you can access the YAML file for direct customization. Any information entered in the Builder tab is automatically ported to the YAML file. Adjust the YAML as needed or specify everything directly via code.

<img src="/.gitbook/assets/image (41) (1).png" alt=""/>

Disclaimer: Custom deployment, especially editing a YAML file, is advanced and should be done with caution. Deploying a corrupted YAML will prevent the pod from deploying, though the machine rental will start and must be stopped manually. No reimbursements are offered. Proceed carefully.

#### **Finalizing the Deployment**

When all deployment specifications are complete, click the "Create Deployment" button. You will then see a screen displaying all available machines based on your chosen resources.

### **Selecting a Machine for Rental**

#### **Machine Selection**

You will have options to choose between different rental types, such as dedicated GPU or dedicated CPU. Your choice can affect both pricing and performance.

#### **Machine Data Table**

At the top, you will see a summary of your custom deployment name and resources. Below, a data table provides detailed information about available machines with filters for price, benchmark score, operating system, region, and advanced filters.

<img src="/.gitbook/assets/Machine Lease List.png" alt=""/>

* Machine Name: Last ten digits of the machine's Hash ID.
* Machine Uptime: Duration the machine has been running continuously.
* Machine Reliability: Displays the percentage of rentals completed without disruptions. It also shows the number of completed jobs without interruptions and the total number of leases throughout the machine's lifetime.
* Price: Hourly cost of the machine.
* Score/$/h: Score per dollar per hour for the machine.
* System: Operating system of the machine.
* Hardware Specifications: GPU, vRAM, cores, RAM, and storage.
* GPU Stats: Specific stats like teraflops and max CUDA configuration.
* Location: Physical location of the machine.

#### **Confirming the Rental**

Select your desired machine via the radio button. At the top of the screen, you will see a summary of your selection with the hourly price. Click the "Rent" button to open a confirmation popup showing a summary of the rental and its financial impact. Confirm to complete the rental and proceed to the Deployments Information screen.

<img src="/.gitbook/assets/Machine Lease Confirmation.png" alt=""/>

By following this guide, you can efficiently create a custom deployment and select the optimal machine for your needs on FluxEdge.
