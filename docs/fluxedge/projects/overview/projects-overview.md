# Projects Overview

In the Projects Overview tab, accessible from the left-hand side menu, you can find a comprehensive overview of all your current projects deployed on FluxEdge. To access this tab, click on "Projects" located next to the "Machines" tab at the top.

<img src="/.gitbook/assets/image (33) (1).png" alt=""/>

#### **Project Tiles** Info: Accesses the information screen for detailed control over the specific project. For more details, refer to the guide here.

Each project is displayed as a tile containing the following information:

* Project Name
* Service Category: E.g., Artificial Intelligence, Rendering, etc.
* Number of Machines: The count of machines running the project.
* Current Status: The operational status of the project.
* Creation Date: When the project was created.
* Hourly Cost: The cost of running the project per hour.

#### **Filtering Projects**

Use the filter options to sort projects by status and service category, making it easier to find specific projects.

#### **Adding New Projects**

An easy-to-use button is available to add new projects if needed.

#### **Managing Projects**

Click on a project tile to enter its detailed management interface, which includes various features and information displays:

<img src="/.gitbook/assets/image (32) (1).png" alt=""/>

### Application Info

* Project Name: The name given to the project during initial deployment, editable using the pencil icon.
* Provider: Information about the machine running the project:
  * Machine Name: Last ten digits of the machine's Hash ID.
  * Type of Machine Rental: Dedicated or shared machine rental.
  * Machine Uptime: Duration the machine has been running continuously.
  * Machine Reliability: Displays the percentage of rentals completed without disruptions. It also shows the number of completed jobs without interruptions and the total number of leases throughout the machine's lifetime.
  * Hardware Specifications: GPU, vRAM, cores, RAM, and storage.
  * Location: Physical location of the machine.
* Project Status
* Elapsed Time: Duration the project has been running.
* Created On: Date and time the project was created.
* Account Balance: Current balance available for machine rentals, with an option to deposit additional funds.
* Price: Hourly cost for the machine rental.
* Spent: Total amount spent on the machine rental.
* Time Left: Approximate time remaining based on current balance and hourly costs. Actual time may vary.

### Logs

Access project container logs, with the ability to view logs for individual containers using the container selection box.

<img src="/.gitbook/assets/image (31) (1).png" alt=""/>

### Shell

The Shell tab provides direct shell access to your project's pod, allowing you to enter commands as needed. SSH (Secure Shell) access ensures a secure and encrypted connection between your device and the remote machine running the project.

Please note that this shell access is designed for short-term interactions. Sessions may automatically refresh or disconnect after periods of inactivity or if your local device enters sleep mode. Consequently, any running processes may be interrupted.

<img src="/.gitbook/assets/image (30) (1).png" alt=""/>

#### Persistent Sessions with tmux

To maintain long-running processes or ensure session continuity despite disconnections, you can utilize **tmux**, a terminal multiplexer that allows you to create detachable and re-attachable shell sessions.​

#### Installing tmux

```bash
apt-get update
apt-get install sudo
sudo apt-get install tmux
```

#### Using tmux

Here's a brief guide to using tmux:​\


* **Start a new session**:

```
tmux
```

*   **Detach from the session**:

    Press `Ctrl+B`, then `D`​
* **List active sessions**:

```bash
tmux ls
```

* **Reattach to a session**:

```bash
tmux attach -t [session_name]
```

_Replace `[session_name]` with the actual session name listed from the previous command._

* **Create a named session**:

```bash
tmux new -s mysession
```

*   **Split window horizontally**:

    Press `Ctrl+B`, then `"`​
*   **Split window vertically**:

    Press `Ctrl+B`, then `%`​
*   **Navigate between panes**:

    Press `Ctrl+B`, then use arrow keys​
*   **Close a pane**:

    Type `exit` within the pane​

By using tmux, your processes will continue to run in the background even if your connection drops, allowing you to resume work seamlessly upon reconnection.

### Events

View project container events within this screen.

<img src="/.gitbook/assets/image (29) (1).png" alt=""/>

### Action Items

* Redeploy: Redeploy the project with the same configuration, replacing the original.
* Stop: Stop the project while keeping the machine rental active. Optionally, you can also stop the entire machine rental and all associated projects.
* Open App: Open the application's front end if available, using Cloudflare Tunnel technology.

By following this guide, you can effectively manage your projects on FluxEdge, ensuring optimal utilization of resources and seamless project operations.
