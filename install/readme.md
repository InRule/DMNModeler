# Installation

#### Installation Notes for DMN Modeler 1.1.2 and irAuthor 5.7.3

DMN Modeler does not currently install with some irAuthor trial installations.  If you are in the middle of a trial, download irAuthor from the support site directly ( [Support Site Downloads](https://support.inrule.com/hc/en-us/articles/360058138552-Download-InRule-Software) ) before following the instructions below. 

#### Prerequistes
- irAuthor 5.7.3 ( [Support Site Downloads](https://support.inrule.com/hc/en-us/articles/360058138552-Download-InRule-Software) )
- The install process will attempt to download and install the Microsoft Edge Web View2 runtime.  This engine allows DMN Modeler to run as a web application within irAuthor.  In some cases, workstations block this download and force the user download and install it manually. Download the installation package from [https://downloads.inrule.com/latest/MicrosoftEdgeWebView2RuntimeInstallerX64.exe](https://downloads.inrule.com/latest/MicrosoftEdgeWebView2RuntimeInstallerX64.exe). 
- This installation requires you to have local administrative rights on your windows workstation for installation only.

#### Release Notes
- Side-by-side installations of irAuthor are now supported. During the installation process, you will be prompted for the target directory of irAuthor 5.7.3.
- DMN Modeler now supports check-in/out behavior like other components within irAuthor.
- DMN Modeler supports linking of some shapes to assets like Decisions, Entities, Rulesets and Decision Tables.
- DMN Modeler now supports rapid modeling with the introduction of a 'mini menu' bound to each shape on the canvas.  Use this menu to add new shapes with a single click, navigate links and edit properties.

#### Installation Steps
1. Download the installation package from [here](/install/InstallationFiles%20v1.1.2%20for%20irAuthor%205.7.3.zip). Click the 'Download' button.
1. Extract the zip file into into a directory like "Documents".
1. Open a command window as Administrator.  Type 'cmd' in the Start bar at the bottom of your windows desktop.  Right click on the menu for 'Command Prompt' and select 'Run as administrator'.
1. From the commandline, use the 'cd' command to navigate to the installation directory. Cut and paste the command below into the CMD window:
````
CD %UserProfile%\Documents\InstallationFiles v1.1.2 for irAuthor 5.7.3\InstallationFiles v1.1.2 for irAuthor 5.7.3\
````
5. Type the following file name into the command window and press 'Return':  
````
Install_AllUsers_LatestInRuleVersion.bat
````
If side-by-side installations of irAuthor are detected, you will be prompted to type in the name of the installation to use.  Finally, in some cases, the installation process will ask to overwrite files.  Indicate 'All' if you are prompted.

6. Open irAuthor and enable the DMN Modeler extension. Close irAuthor and re-open it. When you launch irAuthor, you should see the new item "DMN Models" on the vertical navigation pane on the left side of the screen, and also notice the new "DMN" group of menu options on the Home page ribbon. If for any reason it does not load correctly, you may see log information in the Event Log. Running the Uninstall.bat file found in the installation package will remove it if issues arise.
1. In some cases, the installation process will ask to overwrite files.  Indicate 'All' if you are prompted. 
