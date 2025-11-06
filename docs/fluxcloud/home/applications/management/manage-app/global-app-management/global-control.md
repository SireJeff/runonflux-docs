# Global Control

The **Global Control** tab gives you full authority over the lifecycle of your deployed application on a global level. Whether you're performing routine maintenance, recovering from an issue, or testing changes, this tab is your command center for starting, stopping, pausing, redeploying, or removing the app.

#### How To Access

> **Applications → Management → Manage App → Global App Management → Global Control**

Open the **Management** tab in the **Applications** menu, select an application from **My Active Apps**, click **Manage**, then go to the **Global App Management** section and open the **Global Control** tab.

***

### Overview Of Functions

<img src="/.gitbook/assets/Global Control.png" alt=""/>

#### Start / Stop / Restart

| Action          | Description                                                                                                                 |
| --------------- | --------------------------------------------------------------------------------------------------------------------------- |
| **Start App**   | Launches the application if it's currently stopped.                                                                         |
| **Stop App**    | Gracefully stops the running application and terminates its processes.                                                      |
| **Restart App** | Stops and immediately starts the app again — useful for applying configuration changes or recovering from temporary issues. |

***

#### Pause / Unpause

| Action          | Description                                                                                                                |
| --------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **Pause App**   | Suspends all active processes within the app without shutting it down. This is like hitting a “pause button” on execution. |
| **Unpause App** | Resumes previously paused processes and returns the app to its active running state.                                       |

***

#### Redeploy

| Action                | Description                                                                                                                       |
| --------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| **Soft Redeploy App** | Restarts the app while preserving persistent data. Ideal for safe updates or config changes.                                      |
| **Hard Redeploy App** | Wipes persistent data and redeploys the app from scratch. Use with caution — this is best for full resets or destructive testing. |

**Pro tip:** Always use **Soft Redeploy** unless you intentionally want to delete stored application state.

***

#### Fresh Start?

| Action                | Description                                                                                                                                                  |
| --------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Get New Instances** | Uninstalls the app and deletes all associated data all FluxNodes running the application. This will result in the app being deployed on different FluxNodes. |

Use this when you want to migrate this application from the current FluxNodes to a new ones.
