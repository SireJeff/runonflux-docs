# File Changes

The **File Changes** tab offers insight into the file system of your application’s container, showing both existing files and those that have been modified since the container was launched. This is especially useful for debugging, verifying application behavior, or detecting unwanted changes.

#### How To Access

> **Applications → Management → Manage App → Local App Management → File Changes**

Open the **Management** tab in the **Applications** menu, select an application from **My Active Apps**, click **Manage**, then go to the **Local App Management** section and open the **File Changes** tab.

#### Backend Selector

At the top right you'll find a **FluxNode IP selector**, letting you choose which node you want to inspect or control. This allows you to manage individual node instances of your app. A **reload button** is also available to refresh the list of currently active FluxNodes running your application.

<img src="/.gitbook/assets/Backend Selector.png" alt=""/>

***

### What You'll See

Each entry in the list includes:

* **Path**: The full file system location of the item.
* **Kind**: Indicates the type of item:
  * `0` → Directory
  * `1` → File

<img src="/.gitbook/assets/File Changes.png" alt=""/>

***

### Why This Is Useful

This tab helps developers:

* **Track runtime changes**: Identify files created, modified, or deleted by the application.
* **Verify deployment artifacts**: Ensure necessary files and directories were successfully placed.
* **Detect anomalies**: Spot unexpected files or unauthorized modifications (e.g., injected scripts or overwritten binaries).

Use this tab during deployment validation, debugging sessions, or security reviews.
