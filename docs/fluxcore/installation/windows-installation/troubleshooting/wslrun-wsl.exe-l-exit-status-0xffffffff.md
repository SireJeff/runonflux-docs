# WSLRun(\[wsl.exe -l]): exit status 0xffffffff



<img src="/.gitbook/assets/image (58).png" alt=""/>

* If you encounter this message during the FluxCore installation or while the UI is installing dependencies, it indicates an issue with your WSL (Windows Subsystem for Linux) setup.
* Here's how you can potentially resolve the issue:

1.  **Check for .wslconfig File:**

    * Navigate to `C:\Users\<User>` in File Explorer.
    * Look for a file named `.wslconfig`.

    _Note: It may be hidden. To reveal hidden files, right-click inside the `C:\Users\<User>` folder, select "Properties," check the "Hidden" checkbox, click "Apply," and then "OK."_

![](/.gitbook/assets/image%20(59).png)

2. **Check for fluxcore-wsl-kernel:**

* Ensure that a directory named `fluxcore-wsl-kernel` exists in `C:\Users\<User>`.

3. **Delete .wslconfig:**

* If you find the `.wslconfig` file, delete it.

4. **Delete FluxCore in AppData:**

* Navigate to `C:\Users\<User>\AppData\Local\FluxCore`.
* Delete the `FluxCore` folder.
  * Note: The file `OpenHardwareMonitorLib.sys` may not delete itself. This file is for monitoring CPU temperature and is not critical if it remains.

5. **Rerun FluxCore.exe:**

* Once you've deleted these files and folders, rerun the `FluxCore.exe` installation file.

Following these steps should prevent the error message from appearing again.
