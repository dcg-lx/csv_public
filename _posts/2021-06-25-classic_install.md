# Instructions

## Software requirements

### All users

- Download the Evaluation version of Rhino [here](https://www.rhino3d.com). You will need to create a free account.
- Download QGIS version 2 [here](https://qgis.org/downloads/QGIS-OSGeo4W-2.18.28-2-Setup-x86_64.exe).
- Download the CSV python installer [here](https://github.com/dcg-lx/csv_public/releases/latest/download/install.gh).
- Download the QGIS triangulation tools, Grasshopper convex solid tools, and example files [here](http://solidvoids.fa.ulisboa.pt/download-tool-software/).

### Mac users

At the moment the tools are not fully compatible with the Mac. Development is ongoing to make all tools cross-platform. You are welcome to download Rhino and QGIS 3 for Mac but be aware that the code will not work. Please do not download QGIS 2 for Mac.

Instead, we suggest you create a virtual machine while the software is not updated.
- In this tutorial, we will be using VMware Fusion Player which is free for non-commercial use. If your OS is older than 10.15, you will need to choose an alternative:
  - VMware Fusion Player (free, macOS 10.15+)
  - VMware Fusion (paid, trial available).
  - Parallels Desktop (paid, trial available)
  - VirtualBox (free).
- You will need to adjust our instructions accordingly. In summary, install the correct VM, and install the Parallels or VirtualBox drivers on the windows machine.
- Download VMware Fusion Player from [here](https://my.vmware.com/web/vmware/evalcenter?p=fusion-player-personal) and install it. You will need to create a free account.
- Download a windows virtual machine from microsoft [here](https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/).
- Choose MSEdge on Win10 (x64)
- Choose VMware, Parallels, or VirtualBox as platform depending on the app you're using. Unzip it once the download is finished.

## Prepare the computer

### Mac users

##### Setup the virtual machine

- Create a DCG folder for your course work somewhere on your Mac.
- Move the Rhino and QGIS installers to your DCG folder.
- Launch VMware Fusion. If you already use it, make sure your other virtual machines are suspended or closed.
- Go to the File menu and click on 'Import' (if you can't see the File menu, right click on the VMware icon on the dock and choose 'Virtual Machine Library').
- Choose the windows VM .ovf file you downloaded.
- Continue the installation accepting the default options.
- Before pressing 'Finish', click on 'Customize Settings'. These are optional but will make your life easier.
- How many processors and how much memory you give to the VM will depend on your Mac. We recommend an absolute maximum of half you processor logical cores and memory to be given to the Virtual Machine. For this exercise we recommend 2 cores and 8 GB. A minimum would be 2 cores and 2 or 4 GB. You can find out how many logical cores your Mac has by opening 'Activity Monitor', choosing 'Window' --> 'CPU Usage', and counting the number of bars. You can find out how much memory your Mac has by clicking on 'About this Mac' in the apple menu.
- Use the following settings, in the following order:

| Option             | Setting                                                                                         |
| ------------------ | ----------------------------------------------------------------------------------------------- |
| Compatibility      | Latest Hardware version (18). Click 'Apply'                                                     |
| Sharing            | Enable shared folders                                                                           |
|                    | Add the folder you are using for your DCG course                                                |
| Processor & Memory | Choose 2 processors (adjust accordingly) cores                                                  |
|                    | Choose 2-8 GB of memory (adjust accordingly)                                                    |
|                    | Advanced: Enable hypervisor                                                                     |
| Display            | Enable Accelerate 3D Graphics                                                                   |
|                    | Choose the recommended amount of shared graphics memory (anything between 1 GB to 8 GB will do) |
|                    | Enable 'Use full resolution for Retina display'                                                 |
| Network Adapter    | Confirm 'Connect Network Adapter' is enabled                                                    |
|                    | Chose 'Share with my Mac'                                                                       |
| Isolation          | Enable both options                                                                             |

- You can now close the Options window.
- Click on 'Preferences' in the VMware Fusion menu.
- Choose  'Keyboard & Mouse' and set the following options:

| Option             | Setting                                 |
| ------------------ | --------------------------------------- |
| Key Mappings       | Profile - Default                       |
|                    | Enable Key Mappings                     |
|                    | Disable Language Specific Key Mappings  |
| Mouse Shortcuts    | Disable everything                      |
| Mac Host Shortcuts | Enable                                  |
|                    | Use 'Right Command Key' for Windows key |

- You can now close the preferences window and delete the VM folder and zip file you downloaded.

##### Configuration on the VM client

- Click the play button to launch the virtual machine.
- Click on green button to put it in full screen or increase the window size.
- When you login, it will ask you to reboot to finish installing the drivers. Let it.
- Once its restarted, login with the default username and password (you can change them later):
  - IEUser
  - Passw0rd!
- Windows will probably ask you to logout and login one more time.
- On the Desktop, you will see a 'VMware Shared Folders' folder containing all folders that you shared from your MAC. This folder is mapped to drive 'Z:'. You can think of Z: as being your Mac. Your DCG folder is inside.
- Open the DCG folder in windows. Your QGIS and Rhino installers are there.
- **Follow the instructions for Windows users to install and setup the software.**
- Once you've finished, you may want to create a snapshot:
  - If you are using your own Windows license, this is optional.
  - If you are using a VM you downloaded from Microsoft, you need to take a snapshot of your virtual machine to be able to use it after 90 days:
    - Right click on the VMware Fusion icon on the Dock, and choose 'Virtual Machine Library'.
    - Select your Virtual Machine. Right click and choose 'Snapshots'.
    - Take a snapshot by clicking on the camera button on the top left. Close the snapshot window.
- When you're finished using the virtual machine, quit VMware and choose 'suspend'.

### Windows users

##### Setup Rhino and CSV dependencies

- Install Rhino with the default options.
- Start Rhino to finish installing.
- Enter the license key you were sent in the email from Rhino and activate the software.
- Open Grasshopper (type grasshopper in the command line or press the round green button on the top toolbar.
- In grasshopper, open the csv installer by going to 'File' ---> 'Open document' in the menu bar, and choosing the file you downloaded (install.gh).
- Toggle the 'Install' button by double clicking on 'False' or 'True'.
- A window will pop up asking you to confirm. Press yes.
- The installation process will take some time. Let it run.
- Grasshopper will now create a dcg_csv folder in C:\Users\{use name} and download the required files and install Python and a number of dependencies. Your main system and other python installs you may have will not be affected.
- Once everything completes successfully, a window will pop up informing you that the installation was successful. If not, error messages will be published on the yellow pane at the right.

##### Setup QGIS

- Install QGIS with the default options.
- Open QGIS.
- Click on 'Plugins' in the menu bar, and then 'Manage and install plugins'.
- Do a search for QuickMapServices, and install.
- Do a search for bulkvectorexport and install.
- Close the plugin window.
- Click on 'Web' in the menu bar, 'QuickMapServices', 'Settings'.
- Click on 'More services', and then click on 'Get contributed pack'.\
- Close the settings window by pressing save.
- Click on 'Settings' in the menu bar, and 'Options'

Use the following options:

| Option    | Setting                                                              |
| --------- | -------------------------------------------------------------------- |
| General   | 'Check QGIS version at startup': disabled                            |
| Rendering | 'Render layers in parallel using many CPU cores: enabled             |
| CRS       | 'Automatically enable 'on the fly' reprojection ...': enabled        |
|           | 'Always start new projects with following CRS': EPSG:3763 (see note) |

Note: To pick a CRS, simply choose it from the drop-down menu. If it's not there, click on the globe icon next to the drop-down menu and do a filter (search) for the relevant number (3763). Click on the item found, and press OK. From now on, the CRS will appear in the drop-down menu for quick access.

- Open the Processing Toolbox by clicking on 'Processing' in the menu bar, and 'Toolbox'. The pane will open on the right hand side.
- You should be able to see a 'GRASS GIS 7' commands list in the toolbox. If it's not there, you will need to enable it by clicking on 'enable additional providers' on the bottom.
- To make more room you can close all panes apart from the 'Processing Toolbox' on the right and the 'Layers Panel' on the left.

##### Install the QGIS scripts
- On the 'Processing Toolbox' pane on the right, double click on 'Scripts' ---> 'Tools ---> 'Add script from file'.
- In the file browser, navigate to your qgis scripts folder, select the first script (ending in .py), and press open.
- Repeat with the remaining scripts in the folder.
- The scripts will all be accessible in 'User scripts', in the 'Processing Toolbox'.

##### Create the QGIS project file
- Create a new project by clicking on 'Project' in the menu bar, and 'New'.
- Click on 'Project', in the menu bar, and 'Project Properties'.
- In the properties window, click on the 'CRS' pane.
- Enable 'On the fly crs transformation (OTF)'
- Choose the correct CRS by clicking on it EPSG:3763. Do a filter for 3763 if you need to.
- Press apply, and then ok.
- The bottom right of the QGIS main window should read EPSG:3763 (OTF). If it does not, click on the icon and do as above.
- Save the project on your computer by clicking on 'Project' in the menu bar, and 'Save'.
- From now on, when working with QGIS, open this project before adding any files. Don't forget to save it as you progress.
