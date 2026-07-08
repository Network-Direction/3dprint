# Resonance Compensation

## Overview

This is also known as _input shaping_.

'Ringing' is a surface defect where edges repeat themselves on a printed surface, leaving a subtle 'echo' of the edge.

This is caused by mechanical vibrations in the printer, which is caused by quick changes in the print direction.

Input shaping is where a signal is used to cancel out vibrations.


</br></br>
---
## The 'Ringing Tower'

Download the ringing tower. Either the 3mf in this repository, or the stl file here: [https://www.klipper3d.org/prints/ringing_tower.stl].


</br></br>
### Slicer Setup

Open in Orca. The 3mf should have the correct settings already.

For the stl:

| Parameter            | Setting   | Location                                                 |
| -------------------- | --------- | -------------------------------------------------------- |
| Layer height         | 0.2mm     | Process > Quality                                        |
| Infill               | 0%        | Process > Strength > Infill                              |
| Top layers           | 0         | Process > Strength > Top/bottom shells                   |
| Walls loops          | 2         | Process > Strength > Walls                               |
| Outer wall speed     | 100mm/sec | Process > Speed > Other layers                           |
| Min layer time       | <= 3s     | Material Settings > Cooling > Max fan speed > Layer time |
| Dynamic acceleration | Disabled  | Process > Speed > Aceleration > Normal printing = 0      |
| accel_to_decel       | Disabled  | Process > Speed > Aceleration > Enable accel_to_decel    |


</br></br>
### Klipper Setup

A few Klipper settings before printing the model.

First, add an `[input_shaper]` section to `printer.cfg`.

Next, check these settings:

| Parameter              | Setting   | Notes                                            |
| ---------------------- | --------- | ------------------------------------------------ |
| square_corner_velocity | 5.0       | This is the default setting                      |
| minimum_cruise_ratio   | Disabled  | Run `SET_VELOCITY_LIMIT MINIMUM_CRUISE_RATIO=0`  |
| Pressure Advance       | Disabled  | Run `SET_PRESSURE_ADVANCE ADVANCE=0`             |


</br></br>
Run this command: `SET_INPUT_SHAPER SHAPER_FREQ_X=0 SHAPER_FREQ_Y=0`

If this returns 'unknown command', ignore it and move on.


</br></br>
Run this command: `TUNING_TOWER COMMAND=SET_VELOCITY_LIMIT PARAMETER=ACCEL START=1500 STEP_DELTA=500 STEP_HEIGHT=5`

This sets high levels of acceleration to make the ringing effect more pronounced.


</br></br>
### Print the Model

Start printing the model.

If ringing is clearly visible, you can stop the print early. Also, if acceleration is getting too high for the printer, causing excessive shaking and starts skipping steps, stop the print early.


</br></br>
### Interpreting the Results




</br></br>
---
## References

[https://www.klipper3d.org/Resonance_Compensation.html]
