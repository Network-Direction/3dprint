# General 3D Printing Concepts

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

> [!NOTE]
> Changing this setting will not improve performance or quality. It simply enables your slicer to warn you if needed.




</br></br>
---
## Adhesiveness Category

Defines how strongly different materials will bond with each other.

Materials are given a category number. Materials with the same category value will bond well, and are considered to be compatible.

This is used in multi-filament printing, and for management of the prime tower. It enables the slicer to determine if a purge or transition tower is required between layers of different materials.




</br></br>
---
## Density

A measurement in grams-per-cubic-centermeter of how dense the material is.

This value is used to estimate how much of the material is needed for a particular print. This is how the estimated weight and cost of the print are calculated.

> [!NOTE]
> Adjusting this does not improve performance or quality.




</br></br>
---
## Shrinkage

As the material cools it may shrink, resulting in the print being smaller than expected.

The shrinkage parameters enable the slicer to scale the model appropriately, so the final product is the correct size.

* PLA does not shrink a lot; About 0.2-0.5%
* PETG, ABS, and Nylon shrink more; About 1-3%

</br></br>
In the filament profile, a percentage is set. When it is set to 100%, the slicer will assume there is no shrinkage at all.

If PLA shrinks 0.5%, set the shrinkage to 99.5%

This is set in two ways, based on the coordinates:
* Shrinkage (XY)
* Shrinkage (Z)

> [!NOTE]
> This setting helps improve tolerance.






