# Flex Widget Test

There seems to be an issue with Construct projects when run inside a MTR Compute, specifically a UC-Engine

The project goes inside the UC-Engine and comunicates no problem whith the processors, but after a while (So far observarions have been after 3 days of no use), widgets are no longer displayed in the page.

The project where the issue happend had a button list on a widget. The widget was shared across many pages. The button list have visibility contract per button, but no visibility for the widget on the pages.

Chaning to a different page, makes the shared widget show up again on the second page, but going back is still gone.  Changing the visibility while in the main page, did not brought back the buttons.

Other buttons in the page work fine. 

Other widgets in the page work fine.

This project is providing the minimum amount of code and pages to try to recreate the issue.

There are two pages, both sharing the same Buton List Widget.  The Button List widget contains a Button List. The button list doesn't have any contract in it. Each page does not have a visibility control on the Button List Widget.

There is another button list on each page. These lists are directly inserted in the page, not through a widget.  They are used for visibility testing, as well as to provide a means to switch between pages.

There are also two buttons on each page that provide the same page switching funtionality in case the button list also disapears

> [!IMPORTANT]
> All Touch Panel tests were done through the Crestron Remote Application Version 1.11.00.004

# Steps to recreate the issue:

## Step 1

Project has a shared widget with a button list in it.  All buttons on the button list do not have any contract.  Widget dosen't have a visibility join or contract.

# Construct Information

* Crestron Construct Version: 2.801.22.0
* User Interface Plugin: 1.4401.12.0
* CH5 Version Used: 2.17.0

# UC Enginge Information

__System Information__
* UC-ENGNE unified collaboration system
* MS Teams Rooms App version. 5.4.210.0
* Serial Number: UCE04003860


* *HD-CONV-USB-200: 51.10
* Crestorn Remote: 1.11.00.004
* Controller: TSW-1060 3.002.107.001
* Room Camera: Huddly IQ 1.6.21-156906

* Installed Packages 
* CCS-300: 1.00.16.096 
* Dock: 1.01.050 
* eEverDbcl0Driver 1.00.0000.0052 
* Environment: 1.00.00.004 
* Firmware: 1.21.00.217 
* Flex-Hub: 1.3.0238.10139 
* HD-cow-usB-200: 010.051 
* HD-cow-usB-2S0: 010.051 
* HD-covv.usB.260: 010.051 
* HD-cow-usB-300: 3.25.28 
* Huddly IQ Camera: 1.3-30.104119 
* HuddlyIP: 8.4.3 
* IntelBios: 0073.2021.0722.1021 
* IntelDriverpackage: 1.00.00.66 
* JabraXpress: 5.9.55495 
* LogiSync: 2.1.273-0 
* MercuryFWUpdater: 1.5003.00061.001 
* MercurySrv: 1.5003.00061.001 
* MercuryXFWUpdater: 1.5003.00061.001 
* OneDrive: 21.150.0725.0001
* OOBEApp: 1.00.0000 
* OS: 10.17134.16.428 
* RemoteSrv: 1.21.00.974 
* ToolBoxConsole: 3.0.0.0 
* TouchHelper: 1.19.00.01 
* Tswx60srv:  3.002.1071.001 
* Tswx70srv: 2.006.0067.001 
* TSWxx60FwUpdater: 3.002.1071.001 
* TSWxx70FWUpdater: 2.006.0067.001 
* TSxx70FWUpdater: 2.004.1050.001 
* TSxxx70FWUpdater: -2.006.0067. 0011 
* UC2FWUpdater: 1.0.7.71 
* UC-SB-1 FW: 2.3.98.56 
* UC-SB-1.DFU: 1.00.0000 
* UC-SB-2 FW: 2.4.1.20 
* UC-SB2-CAM: 3.0.4009 
* UC2srv: 1.0.7.71
* UCPR-FW: 1.4588.00064
* UCPR-HDBTTX: 7.5.8


