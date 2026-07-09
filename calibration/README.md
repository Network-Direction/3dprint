# Calibration Guide

This is my calibration guide.

While it should work on other printers, it assumes an Ender 3 v3 SE, with the Klipper firmware.


</br></br>
---
## Part 1 - Klipper Calibration

Calibration should be performed in this order:

1. [Approximate bed level](bed_level_estimate.md)
2. [Rotation Distance](rotation_distance.md)
3. [Heater PID Tuning](heater_pid.md)
4. [Axis Twist Compensation](axis_twist.md)
5. [Z-Offset](z_offset.md)
6. [Bed Leveling (AKA 'Bed Mesh')](bed_leveling.md)
7. [Resonance Compensation (AKA 'Input Shaper')](resonance_compensation.md)
8. [Pressure Advance](pressure_advance.md)



</br></br>
---
## Part 2 - Slicer Calibration

These are calibrated in the slicer, not in Klipper.

Results will vary for different filaments. Even the same type (eg, PLA) may vary by brand and colour.

</br></br>
Calibrations are found in the calibration menu at the top of the slicer:

<img width="207" height="242" alt="image" src="https://github.com/user-attachments/assets/1a211546-09fe-4932-83aa-531bc69cb9a5" />


</br></br>
Calibration order:

1. Temperature
2. Max Volumetric Speed
3. Flow Rate
4. Retraction
5. Cornering
6. VFA
7. Tolerance

</br></br>
> [!NOTE]
> Some calibrations are skipped here, as they were calibrated already using Klipper


</br></br>
### Temperature

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/temp_calib]


</br></br>
### Max Volumetric Speed


</br></br>
### Flow Rate


</br></br>
### Retraction


</br></br>
### Cornering


</br></br>
### VFA


</br></br>
### Tolerance



</br></br>
---
## Notes

Z-Offset, Axis twist, and bed leveling should be repeated if the printer is moved or adjusted in any way.

Resonance compensation should be repeated if anything significantly changes the way the printer vibrates. For example, moving the filament spool from the top of the printer to another location.

Orca's calibration guide can be found here: [https://www.orcaslicer.com/wiki/guides/calibration_guide]


