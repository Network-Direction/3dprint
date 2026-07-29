# PLA Filament Settings

Useful settings I have found. Tested on the Ender 3 v3 SE with unicorn hotend.



</br></br>
---
## Process Settings

</br></br>
| Tab       | Section            | Setting                   | Value    |
| --------- | ------------------ | ------------------------- | -------- |
| Speed     | First Layer Speed  | First layer               | 30mm/s   |
| Speed     | First Layer Speed  | First layer infill        | 40mm/s   |
| Speed     | First Layer Speed  | First layer travel speed  | 100mm/s  |
| Speed     | Other Layers Speed | Outer wall                | 140mm/s  |
| Speed     | Other Layers Speed | Inner wall                | 160mm/s  |


</br></br>
> [!NOTE]
> These next settings will vary per printer. See the [calibration guides](../calibration) to tune them.


</br></br>
| Tab       | Section            | Setting                   | Value    |
| --------- | ------------------ | ------------------------- | -------- |
| Quality   | Line width         | First layer               | 125%     |
| Quality   | Precision          | X-Y hole compensation     | 0.12mm   |
| Quality   | Precision          | X-Y contour compensation  | 0.2mm    |
| Quality   | Walls and Surfaces | Bottom surface flow ratio | 1.02     |




</br></br>
---
## Basic PLA

Tested using Bambu Labs Basic PLA.


</br></br>
### Filament Settings

| Tab      | Section     | Setting              | Value    |
| -------- | ----------- | -------------------- | -------- |
| Filament | Basic       | Shrinkage (XY)       | 100%     |
| Filament | Basic       | Shrinkage (Z)        | 100%     |
| Filament | Basic       | Min nozzle temp      | 190      |
| Filament | Basic       | Max nozzle temp      | 240      |
| Filament | Flow and PA | Flow Ratio           | 0.98     |
| Filament | Flow and PA | Pressure Advance     | Disabled |
| Filament | Print Temp  | Nozzle: First Layer  | 220      |
| Filament | Print Temp  | Nozzle: Other Layers | 220      |
| Filament | Bed Temp    | Textured PEI         | 60       |
| Filament | Volumetric  | Max vol speed        | 18.81    |




</br></br>
---
## Matte PLA

Tested using Sunlu Matte PLA.


</br></br>
### Filament Settings

| Tab      | Section     | Setting              | Value    |
| -------- | ----------- | -------------------- | -------- |
| Filament | Basic       | Shrinkage (XY)       | 100%     |
| Filament | Basic       | Shrinkage (Z)        | 100%     |
| Filament | Basic       | Min nozzle temp      | 205      |
| Filament | Basic       | Max nozzle temp      | 245      |
| Filament | Flow and PA | Flow Ratio           | 0.97     |
| Filament | Flow and PA | Pressure Advance     | Disabled |
| Filament | Print Temp  | Nozzle: First Layer  | 220      |
| Filament | Print Temp  | Nozzle: Other Layers | 210      |
| Filament | Bed Temp    | Textured PEI         | 60       |
| Filament | Volumetric  | Max vol speed        | 18.81    |


</br></br>
| Tab       | Section     | Setting                 | Value    |
| --------- | ----------- | ----------------------- | -------- |
| Overrides | Retraction  | Length                  | 0.4mm    |
| Overrides | Retraction  | Retraction Speed        | 45mm/s   |
| Overrides | Retraction  | Deretraction Speed      | 35mm/s   |
| Overrides | Retraction  | Retract on Layer Change | Enabled  |
| Overrides | Retraction  | Wipe while retracting   | Enabled  |
| Overrides | Retraction  | Wipe distance           | 1mm      |
| Overrides | Retraction  | Amount before wipe      | 70%      |

