# Installation

Installation Notes for DMN Modeler 1.1 and irAuthor 5.7.2

DMN Modeler does not currently install with some irAuthor trial installations.  If you are in the middle of a trial, download irAuthor from the support site directly before following the instructions below.  [Support Site Downloads](https://support.inrule.com/hc/en-us/articles/360058138552-Download-InRule-Software)

##### Prerequistes
- irAuthor 5.7.2 ( [Support Site Downloads](https://support.inrule.com/hc/en-us/articles/360058138552-Download-InRule-Software) )
- The install process will attempt to download and install the Microsoft Edge Web View2 runtime.  This engine allows DMN Modeler to run as a web application within irAuthor.  In some cases, workstations block this download and force the user download and install manually. Download the installation package from [https://downloads.inrule.com/latest/MicrosoftEdgeWebView2RuntimeInstallerX64.exe](https://downloads.inrule.com/latest/MicrosoftEdgeWebView2RuntimeInstallerX64.exe). 
- This installation requires you to have local administrative rights on your windows workstation for installation only.

##### Release Notes
- Side-by-side installations of irAuthor are now supported. During the installation process, you will be prompted for the target directory of irAuthor 5.7.2.
- DMN Modeler now supports check-in/out behavior like other components within irAuthor.
- DMN Modeler supports linking of some shapes to assets like Decisions, Entities, Rulesets and Decision Tables.
- DMN Modeler now supports rapid modeling with the introduction of a 'mini menu' bound to each shape on the canvas.  Use this menu to add new shapes with a single click, navigate links and edit properties.


[Install Video Instructions](https://player.vimeo.com/video/617285075?h=a6604f7220)


1. Download the installation package from [here](/install/InstallationFiles%20v1.1%20for%20irAuthor%205.7.2.zip)
1. Extract the zip file into into a directory like "Documents".
1. Open the command promt as Administrator.
1. From the commandline, use the 'cd' command to navigate to the installation directory. Cut and paste the command below into the CMD window:
````
CD "%UserProfile%\Documents\InstallationFiles v1.1 for irAuthor 5.7.2\InstallationFiles v1.1 for irAuthor 5.7.2\
````
1. Type the following file name into the command window and press 'Return':  
````
Install_AllUsers_LatestInRuleVersion.bat
````
1. Open irAuthor and enable the DMN Modeler extension. Close irAuthor and re-open it. When you launch irAuthor, you should see the new item "DMN Models" on the vertical navigation pane on the left side of the screen, and also notice the new "DMN" group of menu options on the Home page ribbon. If for any reason it does not load correctly, you may see log information in the Event Log. Running the Uninstall.bat file found in the installation package will remove it if issues arise.
