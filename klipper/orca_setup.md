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

###  Moonraker API

The connection between the slicer and printer will use the Moonraker API. This means we need to get an API key to be allowed to connect.

1. Open a web browser
2. Browse to http://your-printer-ip/access/api_key
3. You will get some text like this: `{"result":"xxxxxxxxxx"}`
4. The second part, shown as "xxxxxxx" here, is the API key; Copy this key


</br></br>
> [!WARNING]
>
> API keys are like passwords. You should keep them secret.



</br></br>
### Printer Connection

1. Open Orca Slicer
2. Prepare > Printer
3. Find the **connection** button (it looks like a WiFi symbol)
4. Enter a name for your printer
5. Set The host type to **Moonraker**
6. Set the printer agent to Orca
7. Enter the IP of the printer
8. Enter the API key
9. Click **Test**
10. Click **OK**

<img width="196" height="31" alt="image" src="https://github.com/user-attachments/assets/f238d671-1fd9-4232-ae6b-5e3fe7f59cb7" />

<img width="452" height="312" alt="image" src="https://github.com/user-attachments/assets/f1b354f2-1c13-46a4-88ae-b4add69c77d6" />

</br></br>
If this is all working, when you go to the **Device** tab, you should immediately get access to Mainsail.


</br></br>
---
## Printer Settings

We need to tune the printer settings a bit to get the best out of it.

Click the **edit** button next to the printer (it looks like a pencil).


</br></br>
**Printable Space**

In the _Basic Information_ tab, click the **Set** button next to _Printable area_.

Enter the size of the print bed. For the Ender 3, this is 220mm x 220mm.

<img width="174" height="98" alt="image" src="https://github.com/user-attachments/assets/cd56416e-1419-48ff-86bd-3ba8cce20d17" />


</br></br>
**G-Code Flavour**

Still in the _Basic Information_ tab, under the _Advanced_ area, set **G-code flavor** to Klipper.


</br></br>
**Machine G-code**

Refer to [the macros](../macros/README.md) section for information on setting start and end macros.


