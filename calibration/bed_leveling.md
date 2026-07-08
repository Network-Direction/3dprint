# Bed Leveling

## Goal

The goal of bed leveling is to make sure the print nozzle remains exactly the expected distance from the print bed.

The height of the nozzle from the bed is the Z-axis. For good quality prints, the Z-axis should be accurate to about 0.025mm.

The way this is achieved will depend on the model of printer. Some have automatic bed leveling, others use adjustment screws (this is called bed tramming).


</br></br>
---
## Calibration

The Ender 3 v3 has a single CR-Touch probe, which means bed leveling is automated. No need for adjustment screws.

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


Next, run a repeatibility check. This runs the probe check several times and records values.

1. Home the print head
2. Run 'PROBE_ACCURACY'

Ideally, the max and min values will be the same. However, this isn't usual, as there's always some deviation.

The range value should be 0.025mm or less.


</br></br>
## References

[https://www.klipper3d.org/Bed_Level.html]

[https://www.klipper3d.org/Probe_Calibrate.html]
