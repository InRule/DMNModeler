# Installation
1. Download the installation package from [here](/InstallationFiles%20v1.0.5%20for%20irAuthor%205.7.2.zip)
1. Extract the archive into a folder on your PC where irAuthor is installed.
1. Download and save in the extracted archive the WebView2 Runtime installer from the online link https://developer.microsoft.com/en-us/microsoft-edge/webview2/ -> on the bottom of the page -> Fixed Version -> Version 91.0.864.64 , Select Architecture x64 for 64bit operating system. The name of the installer is MicrosoftEdgeWebView2RuntimeInstallerX64.exe
Ensure there are no instances of irAuthor currently open.
1. Ensure there are no instances of irAuthor currently open.
1. Open the command promt as Administrator and run the Install_AllUsers_LatestInRuleVersion.bat batch file to install the extension.
This file installs the extension for all users of the PC, and only for the current version of irAuthor installed in the default installation folder: "C:\Program Files (x86)\InRule\irAuthor".
This can be helpful if you are running many versions of irAuthor in Side-by-Side mode, where some versions installed cannot support the extension.
1. Open irAuthor and enable the DMN Modeler extension. Close irAuthor and re-open it. When you launch irAuthor, you should see the new item "DMN Models" on the vertical navigation pane on the left side of the screen, and also notice the new "DMN" group of menu options on the Home page ribbon. If for any reason it does not load correctly, you may see log information in the Event Log. Running the Uninstall.bat file found in the installation package will remove it if issues arise.
