# Flex Widget Test

There seems to be an issue with Construct projects when run inside a MTR Compute, specifically a UC-Engine

The problem reported by the client was that the project running inside the UC-Engine would comunicates no problem whith the processors, but after a while, a widget is no longer displayed in the page.

The project where the issue happend had a button list on a widget. The widget was shared across many pages. The button list have visibility contract per button, but no visibility for the widget on the pages.

It looked like this:

![Bad](<Images/Client Bad.png>)

When top half should have looked like this:

![Good](<Images/Client Good.png>)

Using Debugger to change to to a different page, makes the shared widget show up again on the other pages, but going back to the main page would still not shown.  Changing the visibility while in the main page, did not brought back the buttons.

Other buttons in the page work fine. 

Other widgets in the page work fine.

In an effort to isloate the problem, this project was created. It provides the minimum amount of code and pages to try to recreate the issue.

There are two pages, both sharing the same Buton List Widget.  The Button List widget contains a Button List. 

There is another button list on each page. These lists are directly inserted in the page, not through a widget.  They are used for visibility testing, as well as to provide a means to switch between pages.

There are also two buttons on each page that provide the same page switching funtionality in case the button list also disapears

> [!IMPORTANT]
> All Touch Panel tests were done through the Crestron Remote Application Version 1.11.00.004

# Steps to recreate the issue:

## Step 1

Project has a shared widget with a button list in it.  All buttons on the button list do not have any contract.  Widget dosen't have a visibility join or contract.

Problem was not replicated.

## Step 2

Modifying project to add visibility contract to the button list buttons.  Added buttons to toggle that visibility.

It was observed that when the program restarts the button list visibility and the visibility toggle buttons states did not refresh.

The was tried on both a CP3 and a VC4 as the control program device.


![Sync issue](<Images/Sync Issue.png>)

<video controls src="Images/Flex Sync Issue.mp4" title="Title"></video>


The system was also left overnight on page 2 with all the buttons visible like this:

![Before End OF Day](<Images/Before End Of Day.png>)

# SIMPL Information

SIMPL Windows:  4.30 (build: 4.3000.01)
SIMPL+  4.06 (build: 4.0600.00)
Path:  C:\Program Files (x86)\Crestron\Simpl

INCLUDE4_2SERIES.DAT Version Information: (2 Series)  : 1.80  

INCLUDE4.DAT Version Information: (3 & 4 Series)  : 2.21.184  

Data Files: Path: C:\Program Files (x86)\Crestron\Cresdb\Programming  

Symlib2.Tio 1234  12/17/2025      01:55  
  iodev.tio 1234  12/17/2025      01:55   

Other Crestron SW:

        Device Database: 200.435 (build: 200.43500.001.00)
        Crestron Database (cnctrldb22000.mdb) :  228.35 (build: 228.3500.001.00)
        Crestron Toolbox: 3.13p60 (build: 3.1360.0013.8)
        SIMPL+ Cross Compiler: 1.3

        Crestron Construct (all users): 2.801.22

      Legacy Device Tools:  Not Available

Windows System Information:   
        Windows OS: Windows 10 Enterprise Version 2009 (OS Build 26200.7840)



# CP3 Information

CP3>ver -v
CP3 Cntrl Eng [v1.8001.5061.26823 (Nov 10 2022), #008C6CF4] @E-00107f3dd9f1  
Build: 14:54:07  Nov 10 2022 (5061.26823)  
Cab: 1.8001.0214  
Applications:  1.0.8348.22707  
Updater: 1.0.33  
Bootloader: 1.30.00  
IOPVersion: S3 - IO Processor [v1.3177.00007, #FFFFFFFF] slot:6   
CP3-SetupProgram: 1.003.0024   
PUF: 1.8001.0214.01  
FORCED_AUTH_MODE: True   

# VC4 Information

Manufacturer: Crestron  
Model: VC-4  
Category: Control System  
Serial Number: 00be43ea8a4800be43ea8a4800be43ea  
Version: 4.0004.00145  
Build Date: Oct 27 2025  
MAC Address: 00:be:43:ea:8a:48  
Connection Type: XiO Cloud  
Connection Status: Connected  
Application Version: 1.8004.0174  
Python Version: 3.8.17  
Mono Version: 6.12.0.107  
BACnet Version: 15.1.74  
IoTSDK Version: 1.12.1  
.NET Version: 8.0.24  


# Construct Information

Crestron Construct Version: 2.801.22.0  
User Interface Plugin: 1.4401.12.0  
CH5 Version Used: 2.17.0  

# UC Enginge Information

__System Information__
UC-ENGNE unified collaboration system  
MS Teams Rooms App version. 5.4.210.0  
Serial Number: UCE04003860  
  
HD-CONV-USB-200: 51.10  
Crestorn Remote: 1.11.00.004  
Controller: TSW-1060 3.002.107.001  
Room Camera: Huddly IQ 1.6.21-156906  
  
Installed Packages   
CCS-300: 1.00.16.096   
Dock: 1.01.050   
eEverDbcl0Driver 1.00.0000.0052   
Environment: 1.00.00.004   
Firmware: 1.21.00.217   
Flex-Hub: 1.3.0238.10139   
HD-cow-usB-200: 010.051   
HD-cow-usB-2S0: 010.051   
HD-covv.usB.260: 010.051   
HD-cow-usB-300: 3.25.28   
Huddly IQ Camera: 1.3-30.104119   
HuddlyIP: 8.4.3   
IntelBios: 0073.2021.0722.1021   
IntelDriverpackage: 1.00.00.66   
JabraXpress: 5.9.55495   
LogiSync: 2.1.273-0   
MercuryFWUpdater: 1.5003.00061.001   
MercurySrv: 1.5003.00061.001   
MercuryXFWUpdater: 1.5003.00061.001   
OneDrive: 21.150.0725.0001  
OOBEApp: 1.00.0000   
OS: 10.17134.16.428   
RemoteSrv: 1.21.00.974   
ToolBoxConsole: 3.0.0.0   
TouchHelper: 1.19.00.01   
Tswx60srv:  3.002.1071.001   
Tswx70srv: 2.006.0067.001   
TSWxx60FwUpdater: 3.002.1071.001   
TSWxx70FWUpdater: 2.006.0067.001   
TSxx70FWUpdater: 2.004.1050.001   
TSxxx70FWUpdater: -2.006.0067. 0011   
UC2FWUpdater: 1.0.7.71   
UC-SB-1 FW: 2.3.98.56   
UC-SB-1.DFU: 1.00.0000   
UC-SB-2 FW: 2.4.1.20   
UC-SB2-CAM: 3.0.4009   
UC2srv: 1.0.7.71  
UCPR-FW: 1.4588.00064  
UCPR-HDBTTX: 7.5.8  


