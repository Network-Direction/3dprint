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



