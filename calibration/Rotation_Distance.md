# Rotation Distance Calibration

## What Is It?

Rotation distance is the length of filament that is extruded with one full rotation of the extruder's stepper motor.

Stepper motors have a number of steps within each full rotation.
Most stepper motors in a 3d printer have 200 full steps per rotation, and 16 microsteps per full step.

The number of steps per millimeter of extruded filament depends on the manufacturer.


### Stock Ender 3 Values

| Stepper | Full Steps | Micro Steps | Steps per mm | Rotation Distance |
| ------- | ---------- | ----------- | ------------ | ----------------- |
| NEMA 17 | 200        | 16          | 93.0         | 7.663             |


### Calculation

The typical formula for this is:

`rotation_distance = <full_steps_per_rotation> * <microsteps> / <steps_per_mm>`

However, this comes out at 34.408, which is wildly incorrect.

This is because the extruder has a gearbox with a ratio of 4.5:1 (or something like that).


### Configuration

The rotation distance is stored in `printer.cfg`:

```ini
[extruder]
rotation_distance: 7.663
```






This value is stored in the `[extruder]` area of printer.cfg.

The stock value on the Ender 3 v3 SE is 7.663





## References

[https://www.klipper3d.org/Rotation_Distance.html]
