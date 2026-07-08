# Troubleshoot USB Connections

If you have problems connecting the RPi to the printer through USB, here are a few things to try.

First, run `lsusb` to check if the device is listed.

```bash
admin@my-rpi:~ $ lsusb
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
Bus 001 Device 002: ID 2109:3431 VIA Labs, Inc. Hub
Bus 001 Device 007: ID 1a86:7523 QinHeng Electronics CH340 serial converter
Bus 002 Device 001: ID 1d6b:0003 Linux Foundation 3.0 root hub
```

</br></br>
We can see it here listed as `QinHeng Electronics CH340 serial converter`.

If it's not there, you could try checking the `dmesg` logs.

```bash
admin@my-rpi:~ $ dmesg | grep usb
[172655.364024] usb 1-1.2: new full-speed USB device number 6 using xhci_hcd
[172655.458174] usb 1-1.2: New USB device found, idVendor=1a86, idProduct=7523, bcdDevice= 2.64
[172655.458203] usb 1-1.2: New USB device strings: Mfr=0, Product=2, SerialNumber=0
[172655.458216] usb 1-1.2: Product: USB Serial
[172655.468513] usb 1-1.2: ch341-uart converter now attached to ttyUSB0
```

</br></br>
The output above shows just part of the logs, focusing on when I connected the USB cable.

This shows that the device is connected, as is represented as `ttyUSB0`.

If you're not seeing this at all, you may want to try some different cables. Some cables don't work. I think some are for charging only and will not carry data.


</br></br>
`/dev/ttyUSB0` is a friendly name that represents the USB device. The thing is, this name can be different each time the device is connected. It may be `/dev/ttyUSB0` one time, or `/dev/ttyUSB1` another time, or some other number.

The friendly name is actually a link (technically a _symlink_) to the real device, which is located at `/dev/derial/by-id`.

We can see the link between the friendly name and the real or _stable_ name like this:

```bash
admin@my-rpi:~ $ ls -l /dev/serial/by-id/
total 0
lrwxrwxrwx 1 root root 13 Jul  9 09:09 usb-1a86_USB_Serial-if00-port0 -> ../../ttyUSB1
```

</br></br>
Here, we see the friendly name is `ttyUSB1`, and the real name is `usb-1a86_USB_Serial-if00-port0`.

Why is this important? Klipper needs to know what USB device is used to connect to the printer. This is in `printer.cfg`, in the `[mcu]` section.

If this uses a friendly name like `ttyUSB1`, it will be _unstable_. That is, if the USB name changes, klipper will no longer be able to connect to the printer.

Instead, make sure you're using the real name of the device.

```ini
[mcu]
serial: /dev/serial/by-id/usb-1a86_USB_Serial-if00-port0
```



