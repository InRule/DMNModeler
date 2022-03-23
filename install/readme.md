# Installation

Installation Notes

DMN Modeler does not currently install with some irAuthor trial installations.  If you are in the middle of a trial, download irAuthor from the support site directly before following the instructions below.  [Support Site Downloads](https://support.inrule.com/hc/en-us/articles/360058138552-Download-InRule-Software)

If you have more than one installation of irAuthor (side-by-side install), note that the instructions below will look for the default installation location 'C:\Program Files (x86)\InRule'.  If you would like DMN Modeler installed to a different instance, simply rename your target instance to 'InRule' prior to following the instructions.



[Install Video Instructions](https://player.vimeo.com/video/617285075?h=a6604f7220)


1. Download the installation package from [here](/install/InstallationFiles%20v1.0.10%20for%20irAuthor%205.7.2.zip)
1. Extract the archive into a folder on your PC where irAuthor is installed.
1. Download and save in the extracted archive the WebView2 Runtime installer for 64bit OS from the online link https://downloads.inrule.com/latest/MicrosoftEdgeWebView2RuntimeInstallerX64.exe
1. Ensure there are no instances of irAuthor currently open and that the firewall is temporarly turned off, until this installation completes.
1. Open the command promt as Administrator and run the Install_AllUsers_LatestInRuleVersion.bat batch file to install the extension.
This file installs the extension for all users of the PC, and only for the current version of irAuthor installed in the default installation folder: "C:\Program Files (x86)\InRule\irAuthor".
1. Open irAuthor and enable the DMN Modeler extension. Close irAuthor and re-open it. When you launch irAuthor, you should see the new item "DMN Models" on the vertical navigation pane on the left side of the screen, and also notice the new "DMN" group of menu options on the Home page ribbon. If for any reason it does not load correctly, you may see log information in the Event Log. Running the Uninstall.bat file found in the installation package will remove it if issues arise.
