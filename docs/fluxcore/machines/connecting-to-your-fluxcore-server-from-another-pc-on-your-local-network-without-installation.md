# Connecting to Your Fluxcore Server from Another PC on Your Local Network Without Installation

To connect to your Fluxcore server from a PC without Fluxcore installed, you'll need to edit the host file on the non-Fluxcore PC. Although this process will eventually transition to an external website, it's currently essential for remote machine administration without Fluxcore.

_Connecting from a Windows PC without Fluxcore installed to a remote Fluxcore Windows server is not currently supported._

If you're setting up your Fluxcore server with Linux as your OS, ensure that you specify your local IP address during the setup process. This can be done by running the command `curl -o setup.sh <https://download.fluxcore.ai/setup.sh> ; bash setup.sh` and selecting option D to set it to your desired IP address (e.g., 192.168.9.177). It's worth noting that you can update the IP address at any time by rerunning the installation script and choosing option D; there's no need to reinstall the entire setup.

<img src="/.gitbook/assets/image (8) (1).png" alt=""/>

#### **Windows:**

1\.  **Open Notepad with Administrative Privileges**:

* Find the Notepad application either by searching for it in the Start menu or by navigating to `C:\\Windows\\System32` and locating `notepad.exe`.
* Right-click on the Notepad application icon.
* From the context menu, select "Run as administrator." This ensures that you have the necessary permissions to modify system files.

2\.  **Navigate to the Hosts File**:

* With Notepad open, click on the "File" menu at the top-left corner.
* From the drop-down menu, select "Open..."
* In the file dialog that appears, navigate to `C:\\Windows\\System32\\drivers\\etc`
* Ensure that you have selected "All Files" from the file type drop-down menu to see all files, as the hosts file doesn't have an extension.

3\.  **Open the Hosts File**:

* Once you're inside the `etc` directory, look for a file named "hosts" (with no file extension).
* Click on the "hosts" file to select it.
* Then, click on the "Open" button at the bottom-right corner of the dialog box.

4\.  **View the Hosts File**:

* After opening the hosts file, you'll see its contents displayed within the Notepad window.
* The hosts file typically contains a series of lines with IP addresses followed by hostnames.
* You can now view and edit the contents of the hosts file as needed.

By following these steps, you'll be able to open the hosts file in Notepad with administrative privileges and view its contents for editing.

<img src="/.gitbook/assets/image (7) (1).png" alt=""/>

Ensure to append the following entries to the hosts file, tailoring the local IP addresses as per your preference and the number of machines you wish to add. In this example, four machines are included. It's crucial to adhere to the specified naming convention for these entries to function correctly.

192.168.9.177   machine1.remote.fluxcore

192.168.9.179   machine2.remote.fluxcore

192.168.9.130   machine3.remote.fluxcore

192.168.9.178   machine4.remote.fluxcore

Each line associates a local IP address with a unique hostname following the format `machineX.remote.fluxcore`, where "X" represents the machine number. Be mindful to replace the IP addresses with the desired ones for your network setup.

#### **Linux Desktop:**

#### First, initiate the process by accessing the hosts file for editing. This can be accomplished through the command line interface on your Linux desktop by launching a terminal window. We'll employ the nano text editor, known for its simplicity and suitability for this task. Given that the hosts file resides within the protected /etc/ directory, elevating user privileges is necessary via the sudo command. To begin editing the file, execute the following command:

#### sudo nano /etc/hosts

After entering the command, you'll be prompted to input your user password. Once you've successfully entered your password, the hosts file will open, awaiting your edits (as shown in picture).

<img src="/.gitbook/assets/image (6) (1).png" alt=""/>

Add your remote machines like this at the bottom of the file:

<img src="/.gitbook/assets/image (5) (1).png" alt=""/>

To save your changes, press the Ctrl+X keyboard combination. This will prompt a confirmation to save the file, to which you should respond by typing 'y'.
