# Z Offset

## Goal

The nozzle of the print head should be just the right distance away from the print bed.

If it is too close, it will scrape away existing printed material. If it's too far away, the filament will not stick to the bed correctly.


</br></br>
---
## Calibration

### The Paper Test

This is almost identical to the axis twist compensation step. The difference is, it is only done in one place.

1. Make sure the nozzle is clean
   Remove any bits of filament
   This may require preheating the nozzle to clean it up
3. Home the printer (`G28`)
4. Run `PROBE_CALIBRATE`
   The print head will probe a few times
   A window will appear with manual tuning information
6. Place a piece of paper on the print bed, below the print head
7. Using the manual probe buttons, adjust the height of the print head
   Moving the paper around should have a small amount of friction
8. When you have the right results, click 'accept'
9. Run 'SAVE_CONFIG'


</br></br>
### Accuracy Check

Next, run a repeatibility check. This runs the probe check several times and records values.

1. Home the print head
2. Run 'PROBE_ACCURACY'

Ideally, the max and min values will be the same. However, this isn't usual, as there's always some deviation.

The range value should be 0.025mm or less.


</br></br>
## References

[https://www.klipper3d.org/Bed_Level.html]

[https://www.klipper3d.org/Probe_Calibrate.html]
