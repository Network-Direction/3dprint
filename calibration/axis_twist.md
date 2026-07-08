# Axis Twist Compensation

## What is it?

Some printers, including the Ender 3, have a small twist in the X rail, which can skew probe results.

This guide is about compensating for this twist.


### Location Bias

Some probes have a bias that corrupts the results of probing at certain locations.

As the print head moves along a rail, a slight twist in the rail causes the probe to be slightly off.


</br></br>
---
## Calibration

### Part 1 - Configuration

1. Edit the `printer.cfg` file
2. Check if there is a section called `[axis_twist_compensation]`
3. If it is not there, create it and save/restart

```ini
[axis_twist_compensation]
calibrate_start_x: 20
calibrate_end_x: 200
calibrate_y: 110
```

These settings define the calibration bounds. That is, the safe X and Y boundaries to use during the test.

The values above assume a 220x220mm bed. 20mm is left of the margins of this area for the probe.


</br></br>
### Part 2 - Calibration

1. Preheat the bed and the hot end
2. Clean the nozzle so there's no filament there
3. Home the print head (`G28`)
4. Run `AXIS_TWIST_COMPENSATION_CALIBRATE`
   This will probe at several places on the print bed
   For each one, a manual probe window will pop up
5. Add a sheet of paper to the bed
6. Adjust the height of the probe until the nozzle touches the paper
7. Fine tune until there is some friction when moving the paper around
8. Click accept
9. Repeat for remaining points
   There should be three points in total; Left, centre, and right
10. Run `SAVE_CONFIG`



</br></br>
---
## References

[https://www.klipper3d.org/Axis_Twist_Compensation.html]

[https://www.klipper3d.org/Probe_Calibrate.html#location-bias-check]
