# Ironing and Top Surface Quality

## Overview

Ironing is used to smooth out the top layer of a print. This adds to a nice finished look on the top layer.

The hot printer nozzle slowly passes over a layer, smoothing out the surface. This uses the nozzle heat remelt plastic ridges while pressing them flat.

This also extrudes a small amount of filament to fill in any gaps or pits in the surface.

Ironing is set in Process > Quality > Ironing.


</br></br>
Some good starting values are:

| Setting              | Value                                    |
| -------------------- | ---------------------------------------- |
| Ironing Type         | All top surfaces or Topmost surface only |
| Pattern              | _up to your preference_                  |
| Ironing Flow         | 10%                                      |
| Ironing line spacing | 0.15mm (75% of the nozzle diameter)      |
| Ironing inset        | 0.21mm                                   |
| Ironing angle offset | 45° or 90°                               |
| Ironing Speed        | 50mm/s                                   |



</br></br>
To find to optimal values, use a [top surface ironing test](https://www.printables.com/model/1247198-top-surface-ironing-test/files).

This will print at different speeds and fill rates. From there, just decide which settings are best for your printer and filament.


</br></br>
> [!TIP]
> To further tune your top surface, try reducing the _line width_ by about 0.04mm.
>
> The default is 0.40mm, so try 0.36mm.
>
> Find this setting in Quality > Line width.



</br></br>
## Settings

### Ironing Type

This defaults to 'no ironing'. Options are:
* All top surfaces
* Topmost surface only
* All solid layers (this includes the top layer of internal infill)


</br></br>
### Pattern

This is the pattern the hotend moves in while ironing. This will affect the finish of the print. The two options are:
* Rectilinear
* Concentric


</br></br>
### Flow

While ironging, the printer will extrude a small amount of filament to fill in any gaps.

This is a smaller percentage of the normal filament flow.


</br></br>
### Line Spacing

This is the distance between each line during ironing.

This is measures in millimeters, but is calculated as a percentage of the nozzle diameter.


</br></br>
### Inset

This is the distance the extruder will stay away from the edge of the surface. A setting of zero means it will iron all the way to the edge.

However, ironing all the way to the edge can cause overextrusion.

</br></br>
> [!NOTE]
> This is a setting to tinker with, based on the results you want to achieve


</br></br>
### Angle

The angle of ironing. That is, the direction the nozzle travels relative to the underlying lines of the top layer.

This sets how the nozzle cuts across the "grain" of the top layer.

A negative value will disable the angle function entirely.

</br></br>
> [!NOTE]
> Try 45° and 90° to see which you prefer



</br></br>
### Ironing Speed

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


