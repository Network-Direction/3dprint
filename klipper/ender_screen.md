# Restoring the Ender Screen

## Overview
After upgrading the firmware to Klipper, the default screen will no longer work. It is proprietary, and does not work with Klipper natively.

There are three options from here:
1. Don't use it at all, and just use Mainsail
2. Use a different screen with KlipperScreen
3. Restore some of the functionality to the stock screen

</br></br>
This guide is about restoring the sceen functionality (option #3).

The idea behind this is to replace the Klipper firmware with a customised firmware that knows how to 'talk' to the screen.


</br></br>
> [!NOTE]
> Not all features are fully restored.



</br></br>
## Process

This is based on this project: https://github.com/jpcurti/ender3-v3-se-klipper-with-display

</br></br>
> [!WARNING]
> This project assumes the LCD screen is running firmware version 1.0.6


</br></br>
### Part 1 - Build the Firmware

1. SSH to the Raspberry Pi
2. Clone the project (commands below)
3. Run `make menuconfig`
4. Use the same settings you used [during the normal Klipper installation](klipper.md)
5. Enable **extra low level configuration** options
6. Enable **Serial Bridge**
7. Enable **USART2**
8. Save and quit
9. Run `make` to build the firmware as a binary

</br></br>
```bash
git clone https://github.com/jpcurti/ender3-v3-se-klipper-with-display
cd ender3-v3-se-klipper-with-display
make menuconfig
```


</br></br>
### Part 2 - Flash the Printer

This part is the same as a regular Klipper firmware flash. To summarise:

1. Rename the existing `klipper.bin` file
2. Copy the new `klipper.bin` from the `out` directory to the printer's config directory
3. From Mainsail, download the new binary
4. Place the binary on the SD Card
5. Proceed to flash the printer as normal


</br></br>
```bash
mv ~/printer_data/config/klipper.bin ~/printer_data/config/klipper_vanilla.bin
cp ~/ender3-v3-se-klipper-with-display/out/klipper.bin ~/printer_data/config/
```



</br></br>
> [!NOTE]
> Refer to the FAQ on the project repository if you have issues.




