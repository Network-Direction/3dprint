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
2. Max Volumetric Speed (Flow Rate)
3. Flow Ratio
4. Retraction
5. Cornering
6. VFA
7. Tolerance

</br></br>
> [!NOTE]
> Some calibrations are skipped here, as they were calibrated already using Klipper


</br></br>
### Temperature

This is to calibrate the temperature of the nozzle, which affects the viscosity of the filament.

This calibration affects quality, bed adhesion, extrustion levels, and stringing.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/temp_calib]


</br></br>
---
### Max Volumetric Speed

This is the maximum amount of filament that can be melted and extruded per second.

This represents a physical limit of the hardware and filament. The max volumentric speed is a value we provide that the printer will not exceed.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/volumetric_speed_calib]


</br></br>
---
### Flow Ratio

This determines how much filament is extruded. This setting affects print Quality.

> [!NOTE]
> There are two ways this calibration can be performed. One is a 2-Pass method, and the other is called YOLO.
>
> The 2-Pass method is considered legacy. Use the 'YOLO (Recommended' method.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/flow_ratio_calib]


</br></br>
---
### Retraction

Retraction is where the extruder pulls back the filament (retracts) a little when moving the print head to a new location.

The point of this is to prevent small extrusions (stringing) during non-extruding moves.

This calibration affects print quality (stringing).

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/retraction_calib]


</br></br>
---
### Cornering

Cornering is how well the printer handles changes in direction during moves.

This calibration affects quality and accuracy of the prints. This reduces ringing, ghosting, and overshooting.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/cornering_calib]

</br></br>
> [!NOTE]
> If you're not experiencing issues with corners, ringing, etc, you may wish to skip this test.


</br></br>
---
### VFA

VFA (Vertical Fine Artifacts) are surface imperfections on walls. These are often caused by mechanical vibrations.

This calibration aims to determine print speeds that trigger these artifacts.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/vfa_calib]


</br></br>
---
### Tolerance

This refers to how accurate the print jobs are. This is especially important if you are cutting and joining large parts, or are using nuts, bolts, screws, etc, in your prints.

Some tolerance is based around the quality of the printer, which can't really be changes.

Other tolerance issues happen when filament shrinks when cooling.

This calibration aims to determine how much shrinkage occurs, and compensates by scaling some area of the print up.

Follow the guide here: [https://www.orcaslicer.com/wiki/calibration/tolerance_calib]



</br></br>
---
## Notes

Z-Offset, Axis twist, and bed leveling should be repeated if the printer is moved or adjusted in any way.

Resonance compensation should be repeated if anything significantly changes the way the printer vibrates. For example, moving the filament spool from the top of the printer to another location.

Orca's calibration guide can be found here: [https://www.orcaslicer.com/wiki/guides/calibration_guide]


