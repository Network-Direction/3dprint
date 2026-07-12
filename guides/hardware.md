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


