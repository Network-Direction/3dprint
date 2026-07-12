# General 3D Printing Concepts

## Hardware

### Nozzle HRC

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
## Filament

### Adhesiveness Category

Defines how strongly different materials will bond with each other.

Materials are given a category number. Materials with the same category value will bond well, and are considered to be compatible.

This is used in multi-filament printing, and for management of the prime tower. It enables the slicer to determine if a purge or transition tower is required between layers of different materials.




</br></br>
---
### Density

A measurement in grams-per-cubic-centermeter of how dense the material is.

This value is used to estimate how much of the material is needed for a particular print. This is how the estimated weight and cost of the print are calculated.

</br></br>
> [!NOTE]
> Adjusting this does not improve performance or quality.




</br></br>
---
### Shrinkage

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

</br></br>
> [!NOTE]
> This setting helps improve tolerance.



</br></br>
---
## Print Quality

### Ironing

Ironing is used to smooth out the top layer of a print. This adds to a nice finished look on the top layer.

The hot printer nozzle slowly passes over a layer, smoothing out the surface. This uses the nozzle heat remelt plastic ridges while pressing them flat.

This also extrudes a small amount of filament to fill in any gaps or pits in the surface.

Ironing is set in Process > Quality > Ironing.


</br></br>
Some good values are:

| Setting              | Value                                    |
| -------------------- | ---------------------------------------- |
| Ironing Type         | All top surfaces or Topmost surface only |
| Pattern              | _up to your preference_                  |
| Ironing Flow         | 20%                                      |
| Ironing line spacing | 0.15mm (75% of the nozzle diameter)      |
| Ironing inset        | 0.21mm                                   |
| Ironing angle offset | 45° or 90°                               |
| Ironing Speed        | 40mm/s                                   |



</br></br>
**Ironing Type**

This defaults to 'no ironing'. Options are:
* All top surfaces
* Topmost surface only
* All solid layers (this includes the top layer of internal infill)


</br></br>
**Pattern**

This is the pattern the hotend moves in while ironing. This will affect the finish of the print. The two options are:
* Rectilinear
* Concentric


</br></br>
**Flow**

While ironging, the printer will extrude a small amount of filament to fill in any gaps.

This is a smaller percentage of the normal filament flow.


</br></br>
**Line Spacing**

This is the distance between each line during ironing.

This is measures in millimeters, but is calculated as a percentage of the nozzle diameter.


</br></br>
**Inset**

This is the distance the extruder will stay away from the edge of the surface. A setting of zero means it will iron all the way to the edge.

However, ironing all the way to the edge can cause overextrusion.

</br></br>
> [!NOTE]
> This is a setting to tinker with, based on the results you want to achieve


</br></br>
**Angle**

The angle of ironing. That is, the direction the nozzle travels relative to the underlying lines of the top layer.

This sets how the nozzle cuts across the "grain" of the top layer.

A negative value will disable the angle function entirely.

</br></br>
> [!NOTE]
> Try 45° and 90° to see which you prefer



</br></br>
**Ironing Speed**

This is in the Process > Speed > Other layers speed area.

This controls the speed at which the ironing is done. Measured in mm/s.

Usually, slower speeds lead to better results (but longer print times).


</br></br>
Sample Values:

| Profile      | Speed       |
| ------------ | ----------- |
| High quality | 15-30 mm/s  |
| Balanced     | 40-60 mm/s  |
| Draft        | 70-100 mm/s |


