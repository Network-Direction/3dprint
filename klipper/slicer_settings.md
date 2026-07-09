# Slicer Settings

The settings here are useful to have as defaults. Some of these are for supporting Klipper specfically, while others are just plain good.

These can apply to any slicer, but I've been using Orca.


</br></br>
---
## Filament Settings

Filament settings will vary depending on the filament you use (duh).

However, I recommend disabling **pressure advance**, as this is better managed in Klipper.


</br></br>
If you're interested, here are some settings I used for Sunlu Matte PLA:

| Area     | Category                      | Setting                       | Value    |
| -------- | ----------------------------- | ----------------------------- | -------- |
| Filament | Basic Information             | Recommended nozzle temp (min) | 205°     |
| Filament | Basic Information             | Recommended nozzle temp (max) | 245°     |
| Filament | Flow Ratio & Pressure Advance | Flow ratio                    | 0.95     |
| Filament | Flow Ratio & Pressure Advance | Pressure Advance              | Disabled |
| Filament | Print Temperature             | First Layer                   | 220°     |
| Filament | Print Temperature             | Other Layers                  | 220°     |
| Filament | Bed Temperature               | First Layer                   | 60°      |
| Filament | Bed Temperature               | Other Layers                  | 60°      |


</br></br>
---
## Process Settings

These are in the slicer, over on the left, under the _Printer_ and _Filment_ settings.

<img width="261" height="57" alt="image" src="https://github.com/user-attachments/assets/ef95c08f-4f7e-4181-836e-15a72485b566" />



</br></br>
### Quality

_Default settings are fine_


</br></br>
### Strength

| Section | Setting               | Value  |
| ------- | --------------------- | ------ |
| Infill  | Sparse infill pattern | Gyroid |


</br></br>
### Speed

| Section      | Setting               | Value    |
| ------------ | --------------------- | -------- |
| First Layer  | First Layer           | 60mm/s   |
| First Layer  | Infill                | 80mm/s   |
| Other Layers | Outer Wall            | 140mm/s  |
| Other Layers | Inner Wall            | 160mm/s  |
| Acceleration | Normal Printing       | 0        |
| Acceleration | accel_to_decel        | Disabled |


</br></br>
> [!NOTE]
> Acceleration is disabled here as it is handled by Klipper.


</br></br>
### Support

| Section | Setting               | Value       |
| ------- | --------------------- | ----------- |
| Support | Enable Support        | Enabled     |
| Support | Type                  | Tree (auto) |
| Support | Style                 | Tree Slim   |


</br></br>
### Others

| Section       | Setting               | Value   |
| ------------- | --------------------- | ------- |
| G-Code Output | Label Objects         | Enabled |
| G-Code Output | Exclude Objects       | Enabled |

</br></br>
> [!NOTE]
> This is to support cancelling single objects, such as with the `M486` command.


