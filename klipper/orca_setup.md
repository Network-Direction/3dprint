# Setup Orca With a Klipper Printer

## Overview

You no longer need to export prints to gcode, and transfer them manually.

Not only can you access your printer through the mainsail UI, you can also configure your slicer to connect directly.

Before starting this, you should have:
* Installed Orca Slicer
* Setup your Raspberry Pi with Klipper, Moonraker, and Mainsail
* Flashed your printer with the Klipper firmware
* Confirmed you can reach the printer from the Mainsail UI

</br></br>
If you have not done this yet, [follow the Klipper setup guide](klipper.md)


</br></br>
---
## Add The Printer

1. Open Orca Slicer
2. In the **prepare** tab, In the **printer** section, find the **connection** button (it looks like a WiFi symbol)
3. Set The host type to Octo/Klipper
4. Set the printer agent to Orca
5. Enter the IP of the printer
6. Enter the API key
7. Click **Test**
8. Click **OK**

<img width="196" height="31" alt="image" src="https://github.com/user-attachments/assets/f238d671-1fd9-4232-ae6b-5e3fe7f59cb7" />

<img width="452" height="312" alt="image" src="https://github.com/user-attachments/assets/44ddeda9-5a3d-407a-b4c8-7eb30983e437" />

