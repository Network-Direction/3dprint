# Hardware

## Nozzle HRC

HRC is the Rockwell Hardness Scale. This measures the hardness of metal materials.

Different nozzles are needed depending on the abrasiveness of the filament. More abrasive filaments will wear down softer nozzles faster.


</br></br>
| Value | Nozzle Type              | Filament Type                         |
| ----- | ------------------------ | ------------------------------------- |
| 0     | Brass                    | PLA, PETG                             |
| 1     | Coated                   | Wood filled PLA, Glow in the dark PLA |
| 2     | Hardened Steel           | Carbon fiber, metal filled filaments  |
| 3     | Hardened Steel (HRC 60+) | Carbon fiber, metal filled filaments  |


</br></br>
This is set in the filament profile in the slicer, so the slicer knows what nozzle is required. If you use a printer with a softer nozzle, it will warn you about this before you proceed.

A value of zero means this will not be checked.

</br></br>
> [!NOTE]
> Changing this setting will not improve performance or quality. It simply enables your slicer to warn you if needed.




</br></br>
---
## Fans (Ender 3 v3)

The Ender 3 has a total of four fans:
* Hot end cooling fan
* Part cooling fan
* Motherboard fan
* PSU fan


</br></br>
### Extruder Fans

The hot end fan and part cooling fan are both in the extruder. These are the ones that get noisy when a print starts.

Both are 24v, and connect with 1.25mm JST headers. These are 2-pin headers, so no PWM is used to control fan speed.

The hot end fan is a 4010 axial fan (40x40x10), while the part cooling fan is a 4010 blower/radial fan.


</br></br>
> [!WARNING]
> The Ender uses 24v for fans. Make sure any replacement is 24v as well.
>
> Alternatively, use a 12v fan (quieter) with a _buck converter_ to convert the 24v to 12v.


</br></br>
These can be upgraded to larger and quieter fans. The stock fans are 40x40x10mm, while some 24v replacements are 40x40x20mm.

This typically means printing a new hotend shroud to house the new fans.

</br></br>
> [!WARNING]
> Due to the heat produced, this should be printed in PETG, not PLA.


</br></br>
Good options seem to include:
* Noctua NF-A4x10 FLX (12v, requires buck converter)
* Sunon 4020



</br></br>
### Motherboard Fans

This is for cooling the stepper motor drivers. This is a 6015 axial fan (60x60x15mm), at 24v.

Quiet fans to replace this are rare, so the alternative is to adapt the base cover of the printer, and include a larger quiet 12v fan with a buck converter.


</br></br>
### PSU Fan

This is also a 6015 24v axial fan. This keeps the power supply cool. It usually kicks in when the bed warms up.

</br></br>
> [!WARNING]
> Be careful when modifying anything related to the PSU. There is a risk of electrical shock.


</br></br>
Modifying this directly has risks, and voids warranty.

An alternative is to print a new shroud for the PSU, and use large quiet PC fans. These move a lot more air at a lower dB.


</br></br>
### References

https://www.reddit.com/r/ender3/comments/gkkli3/quieting_my_ender_3_pro/


