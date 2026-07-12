# DroidKlipp and KlipperScreen

## Overview

KlipperScreen is the module that lets you connect a touch screen to Klipper, for local control and monitoring.

Example hardware [can be found here](https://klipperscreen.readthedocs.io/en/latest/Hardware/)


</br></br>
If you don't have one of these screens, another option is to use an old Android device to be your screen.

This uses **XServer-XSDL** on the Raspberry Pi. The phone is connected to the RPi with a USB cable (or optionally a WiFi connection) using [ADB](https://developer.android.com/tools/adb).

Klipper includes [documentation](https://klipperscreen.readthedocs.io/en/latest/Android/) of how this works, and how you can set it up.


</br></br>
A potentially easier option is to use [DroidKlipp](https://github.com/CodeMasterCody3D/DroidKlipp). It manages many of the settings for you.


</br></br>
---
## Process

Here is the high-level process I used to get this working:

1. Unlock the phone and install LineageOS (Optional)
2. Installed DroidKlipp through an APK file
3. Install KlipperScreen and DroidKlipp on the Raspberry Pi
4. Connected the Phone to the RPi, and customised


</br></br>
### Lineage OS

This is an optional step. In my case, I unlocked the bootloader of my old phone, and installed [Lineage OS](https://lineageos.org/).

I did this so I could have a very lightweight setup on the phone. I didn't install any Google apps at all.

How this is done will depend on the device that you want to use. The basic idea is to flash the phone with a lineage recovery image, and let it install.

I'll leave you to investigate the details of how this is done yourself.


</br></br>
### Phone Setup

A mandatory step is to enable USB debugging. To do this, first enable developer mode:

1. Open Settings > About Phone > Software Information
2. Tap the build number 7 times


</br></br>
Now to enable USB debugging;

1. Settings > Developer mode
2. Find USB debugging, and toggle the slider


</br></br>
While you're there, there are some other options that will help (but aren't mandatory):

* Enable _don't keep activities_ (in developer options)
* Limit background processes to 2 (also in dev options)
* Remove the lock screen, so you don't need to unlock the device each time



</br></br>
### DroidKlipp App

[Download the DroidKlipp APK](https://github.com/CodeMasterCody3D/DroidKlipp-Android-APK/releases/latest/download/DroidKlipp.apk) from the [GitHub page](https://github.com/CodeMasterCody3D/DroidKlipp).

Transfer this to your device, and install it as normal.


</br></br>
### Raspberry Pi Setup

To setup the Raspberry Pi, you will need to [run KIUAH](klipper.md) again. Make sure there's no print job running while installing apps.

1. Install KlipperScreen
  1. Use 'standalone mode'
  2. Use **X11** as the server (**Wayland** is not supported yet)
  3. Do not install **Network Manager**

2. Install DroidKlipp
  1. Get this from the _extensions_ area
  2. When asked, skip configuring a manual IP


</br></br>
### Connection and Customization

Connect the phone:

1. Launch the DroidKlipp app on the phone
2. Follow the prompts to set the screen resolution, etc
3. Connect the phone to the RPi with a USB cable
4. Confirm that you have access to the printer


</br></br>
Customization is optional. The default settings work just fine.

However, to customise, follow this process:

1. Restart the KlipperScreen service (use the 'power button' in mainsail)
2. Confirm that a `KlipperScreen.conf` file has been created (it will be empty)
3. Refer to [the documentation](https://klipperscreen.readthedocs.io/en/latest/Configuration/) to see configuratble settings


</br></br>
Sample configuration:

```ini
# ===============================================
# Interface settings
# ===============================================

[main]
# Interface theme
# Options: default, material-dark, colorized, voron-dark
# voron-dark hides some icons and menu items
# default, material-dark, and colorized are very similar
theme = colorized

# Job status timeout after a job (0 is disabled)
job_complete_timeout: 0
job_error_timeout: 0

# Autolock screen (0 is disabled)
autolock_timeout: 0
start_locked: False


[printer Ender]
# Information displayed in the titlebar
# Options: full, short, None
titlebar_name_type: full

# Items in the titlebar, in addition to extruder and bed temp
titlebar_items: None


# ===============================================
# Extra menu items
# ===============================================

[menu __main homing]
name: Home
icon: home
method: printer.gcode.script
params: {"script":"G28"}


#~# --- Do not edit below this line. This section is auto generated --- #~#
#~#
#~# [main]
#~# theme = colorized
#~#
```




