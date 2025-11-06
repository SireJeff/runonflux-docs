# Application Control

The **Application Control** tab gives you full authority over the lifecycle of your deployed application. Whether you're performing routine maintenance, recovering from an issue, or testing changes, this tab is your command center for starting, stopping, pausing, redeploying, or removing the app.

#### How To Access

> **Applications → Management → Manage App → Local App Management → Application Control**

Open the **Management** tab in the **Applications** menu, select an application from **My Active Apps**, click **Manage**, then go to the **Local App Management** section and open the **Application Control** tab.

#### Backend Selector

At the top right you'll find a **FluxNode IP selector**, letting you choose which node you want to inspect or control. This allows you to manage individual node instances of your app. A **reload button** is also available to refresh the list of currently active FluxNodes running your application.

<img src="/.gitbook/assets/Backend Selector.png" alt=""/>

***

### Overview Of Functions

<img src="/.gitbook/assets/Application control.png" alt=""/>

#### Control

General options to control running status of Application.

| Action          | Description                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Start App**   | Launches the application if it's currently stopped.                                                                         |
| **Stop App**    | Gracefully stops the running application and terminates its processes.                                                      |
| **Restart App** | Stops and immediately starts the app again — useful for applying configuration changes or recovering from temporary issues. |

***

#### Pause

The Pause command suspends all processes in the specified Application.

| Action          | Description                                                                                                                |
| --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Pause App**   | Suspends all active processes within the app without shutting it down. This is like hitting a “pause button” on execution. |
| **Unpause App** | Resumes previously paused processes and returns the app to its active running state.                                       |

***

#### Monitoring

Controls Application Monitoring.

| Action                 | Description                                           |
| ---------------------- | ----------------------------------------------------- |
| **Start Monitoring**   | Start the monitoring process.                         |
| **Stop Monitoring**    | Stop the monitoring process.                          |
| **Stop & Delete Data** | Stop monitoring process, and delete all history data. |

***

#### Redeploy

Reinstall your application from the docker repo. Soft option, keeps data on the instance, Hard option deletes everything and gets installed like a fresh install.

| Action                | Description                                                                                                                       |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Soft Redeploy App** | Restarts the app while preserving persistent data. Ideal for safe updates or config changes.                                      |
| **Hard Redeploy App** | Wipes persistent data and redeploys the app from scratch. Use with caution — this is best for full resets or destructive testing. |

**Pro tip:** Always use **Soft Redeploy** unless you intentionally want to delete stored application state.

***

#### Remove

Stops, uninstalls and removes all App data from this FluxNode. Use this when you want to migrate this application from the current FluxNode to a new one.

| Action         | Description                                                                                                                                                                        |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Remove App** | Uninstalls the app and deletes all associated data from the current selected FluxNode running the application. This will result in the app being deployed on a different FluxNode. |
