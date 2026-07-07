# Rotation Distance Calibration

## What Is It?

Rotation distance is the length of filament that is extruded with one full rotation of the extruder's stepper motor.

Stepper motors have a number of steps within each full rotation.
Most stepper motors in a 3d printer have 200 full steps per rotation, and 16 microsteps per full step.

The number of steps per millimeter of extruded filament depends on the manufacturer.


</br></br>
### Stock Ender 3 Values

| Stepper | Full Steps | Micro Steps | Steps per mm | Rotation Distance |
| ------- | ---------- | ----------- | ------------ | ----------------- |
| NEMA 17 | 200        | 16          | 93.0         | 7.663             |


</br></br>
### Calculation

The typical formula for this is:

`rotation_distance = <full_steps_per_rotation> * <microsteps> / <steps_per_mm>`

However, this comes out at 34.408, which is wildly incorrect.

This is because the extruder has a gearbox with a ratio of 4.5:1 (or something like that).


</br></br>
### Configuration

The rotation distance is stored in `printer.cfg`:

```ini
[extruder]
rotation_distance: 7.663
```


</br></br>
---
## Calibration

### Overview

The main idea is this:
1. Attempt to print a fixed length of filament
2. Measure how much was actually printed
3. If these don't match, adjust the rotation distance


</br></br>
### Procedure - Part 1

1. Heat the extruder to the value you typically use (eg, 200-220°); The bed does not need preheating
2. Measure exactly 120mm from the top of the filament intake
3. Use a marker or pen to mark this point on the filament (a lighter colour filament might help with this)
4. Send g-code commands to the printer, to slowly extrude 100mm of filament (code is below)
5. Meaure the distance from the top of the filament intake to the mark


</br></br>
```gcode
M83            ; Set relative mode
M109 S220      ; Preheat the extruder to 220, and wait for this to complete
G1 E100 F50    ; Extrude 100mm of filament at 50mm/min
```

</br></br>
If the distance from the intake to the mark is 20mm, then your job is done. The rotation distance is set correctly.

If not, move on to part 2.


</br></br>
### Procedure - Part 2

We need to calculate a new rotation distance.

First, get the current setting from `printer.cfg`. This seems to be 7.663 by default (you should double check this).

Next, determine how much filament was actually extruded. To do this, subtract the remaining distance from 120mm.
For example, if there's 21mm left, the printer actually extruded 99mm of filament.

Using this formula, determine the new rotation distance:

```
rotation distance = current rotation distance x actual extruded length / 100
```

</br></br>
Now you have the new value, update `printer.cfg` with the new value.

I would recommend running the test again now to confirm the value is working as expected.


</br></br>
---
## References

[https://www.klipper3d.org/Rotation_Distance.html]
