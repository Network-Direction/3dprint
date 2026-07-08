# Klipper and Raspberry Pi

## Overview

The Ender 3 comes with the Marlin firmware. Many printers now come with the Klipper firmware, because it's just awesome.

This guide is about installing the Klipper firmware on the Ender 3, and controlling it over the network via a Raspberry Pi rather than needing an SD-CARD. That means we can print straight from the slicer, just like the rich people with fancy printers do.

Most of this is based around [https://athemis.me/projects/klipper_guide/]. There's just a few things I learned along the way that will help.

</br></br>
> [!WARNING]
> A result of this process is the LCD control screen is disabled.
> Some limited functionality can be restored, but it won't be the same as before.
> The web interface is used as a replacement for this


</br></br>
The end result will be:
* A Raspberry Pi (RPi) will be connected to the printer with a USB-C cable
* The RPi will be connected to the network (wired or wireless)
* The printer will run Klipper firmware
* The slicer will see the RPi as the printer, and send prints there


</br></br>
---
## Components

### Hardware

In terms of hardware, all you need is:
* A Raspberry Pi (I used a Pi 4)
* Power for the RPi
* A microSD card for the RPi
* Your usual SD-Card for the printer
* A USB-C cable to connect the RPi to the printer


</br></br>
### Software

There are several software components this project will use, as outlined below.

**KIAUH** - A script used for setting up the environment, and installing other components.

**Klipper** - The firmware that the printer will run.

**Moonraker** - The API that lets us interact with the Klipper firmware.

**Mainsail** - The web GUI that we access (fluidd is an alternative).


</br></br>
---
## Process

### Step 1 - Set up the RPi

1. Download and install the Raspberry Pi Imager tool
2. Run the tool, and select your model of RPi
3. Select the 64-bit Raspberry Pi OS, Lite edition, as the operating system
4. Work through the wizard, entering your username, password, WiFi credentials, and hostname
5. Make sure you have SSH enabled
6. Write the OS to the SD Card
7. Start the RPi up and confirm you can SSH to it


</br></br>
### Step 2 - KIAUH

Install the KIAUH script, which will manage the install of everything else.

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install git -y
cd ~ && git clone https://github.com/dw-0/kiauh.git
```


</br></br>
### Step 3 - Install Other Components

Start the KIAUH script:

```bash
./kiauh/kiauh.sh
```

<img width="371" height="308" alt="image" src="https://github.com/user-attachments/assets/a7cac047-aa7a-430a-98bf-9543018fc054" />
</br></br>

1. Go to 'install'
2. Install Klipper
3. Install Moonraker
4. Install Mainsail



</br></br>
---
## Configuration Files

Open a web browser and navigate to http://IP-of-your-RPi

You will see a dashboard with some error messages. These errors are because the printer is not connected yet.


</br></br>
There will be several configuration files that we will need to work with. These are present regardless of which UI (mainsail or fluidd) you choose to use.

The main ones are:

**printer.cfg** - Configuration for Klipper running on the printer.

**macro.cfg** - A collection of macros, which are a collection of g-code commands to make some tasks easier.

**mainsail.cfg** - Mainsail UI configuration, as well as some built in macros we can use for things like calibration.

**moonraker.conf** - Settings for the moonraker API.

</br></br>
Mostly we will work with `printer.cfg` and `macros.cfg`.

</br></br>
In the mainsail UI, click the 'Machine' tab on the left. This will show you a list of config files.

`printer.cfg` and `macros.cfg` should already be there.

However, we want to replace these with the ones found here: [https://github.com/shubham0x13/ender-3-v3-se-klipper-config].

These are already tuned for the Ender 3 printer. Download them, and replace the existing files with these.



</br></br>
---
## Klipper Firmware

Now to create the custom Klipper firmware that will be installed on the printer.

We generate this on the RPi, and then flash the printer through the standard SD Card.


</br></br>
### Create Firmware

First, SSH to the RPI, and run `menuconfig` from the klipper directory (within your home directory).

```bash
cd ~/klipper
make menuconfig
```


</br></br>
This will start a script that will build the firmware.

<img width="581" height="75" alt="image" src="https://github.com/user-attachments/assets/c9fb25b4-7c8c-4172-9e7e-870416729e97" />

</br></br>
The older models are configured as shown in the image above.

For the newer motherboard (the 'CR4NS200320C14'), change these values:
* Processor Model: STM32F401
* Bootloader Offset: 64KiB


</br></br>
Save your changes and quit.

Next, run `make` to build the firmware. This will create a file called `~/klipper/out/klipper.bin`.

Copy this file to the 'config' directory (this is where `printer.cfg` is):

```bash
cp ~/klipper/out/klipper.bin ~/printer_data/config/
```


</br></br>
### Flash the Printer

Go back to the 'Machine' tab in mainsail. `klipper.bin` should be visible in the file list. Download it.

1. Make sure the printer is off
2. Transfer the new firmware to the SD Card
3. Insert the card into the printer, and turn it on
4. Wait for 15 seconds
5. Turn off the printer
6. Remove the file from the SD card and replace
7. Turn on the printer

> [!WARNING]
> Apparently the newer motherboard required the bin file to be in a directory called `STM32F4_UPDATE` on the SD Card.

The LCD panel on the printer will show a default blue image.


Connect the RPi to the printer with the USB cable, and go back to mainsail.

You may need to click **Restart Firmware** to get it to recognise the printer.

> [!NOTE]
> I found that some USB cables wouldn't work. Some may be for chargins devices only.
> If you have troubles, try changing cables.
> Also see [USB Troubleshooting](usb_tshoot.md)


</br></br>
### Testing

The firmware is installed on the printer, and the software is now ready to go.

A Simple way to test it is working is to click the home button in the 'Toolhead' area.

<img width="204" height="154" alt="image" src="https://github.com/user-attachments/assets/9af31dd1-27c5-4f2a-b2f7-4b0567658d55" />


</br></br>
---
## Next Steps

Now that's done, your next steps are:
* Calibrate the printer
* Learn about Macros
* Configure the slicer






