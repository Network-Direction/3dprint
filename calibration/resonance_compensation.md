# Resonance Compensation

## Overview

This is also known as _input shaping_.

'Ringing' is a surface defect where edges repeat themselves on a printed surface, leaving a subtle 'echo' of the edge.

This is caused by mechanical vibrations in the printer, which is caused by quick changes in the print direction.

Input shaping is where a signal is used to cancel out vibrations.


</br></br>
---
## Calibration

## The 'Ringing Tower'

Download the ringing tower. Either the 3mf in this repository, or the stl file here: [https://www.klipper3d.org/prints/ringing_tower.stl].

Open in Orca. The 3mf should have the correct settings already. For the stl:

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
---
## References

[https://www.klipper3d.org/Resonance_Compensation.html]
