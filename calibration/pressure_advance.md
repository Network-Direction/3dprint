# Pressure Advance

This feature is helpful for reducing ooze during non-extrude moves and blobbing during cornering.

Settings may vary for different filaments.


</br></br>
---
## Calibration

### Slicing

Get the square tower print, and add it to the slicer. Either use the 3mf file in the repository, or the stl file here: [https://www.klipper3d.org/prints/square_tower.stl]

| Setting              | Value          |
| -------------------- | -------------- |
| Speed                | 100mm/s        |
| Infill               | 0              |
| Layer height         | Coarse (0.3mm) |
| Dynamic acceleration | Disabled       |
| Scarf joint seams    | Disabled       |


</br></br>
What is a 'coarse' layer height? It just means a thicker than usual layer height.

0.3mm is a suggested value based on a 0.4mm nozzle.


</br></br>
### Running the Calibration

Run these commands to prepare for the print:

```
SET_VELOCITY_LIMIT SQUARE_CORNER_VELOCITY=1 ACCEL=500
```

```
TUNING_TOWER COMMAND=SET_PRESSURE_ADVANCE PARAMETER=ADVANCE START=0 FACTOR=.005
```

Next, start the print.


</br></br>
### Interpreting the Results

The commands above tell klipper to adjust the pressure advance values on each layer of the print. Higher layers have a higher value.

Layers below the ideal value will have blobbing at the corners.

Layers above the ideal value will have more rounded corners, and may have poor extrusion leading up to the corner.

If the print seems to have passed the ideal value, the print can be cancelled.


</br></br>
Use calipers to find the height that has the best quality corners. If in doubt, use the lower values.

Calculate the best pressure advance value with this formula:

```
pressure_advance = <start> + <measured_height> * <factor>
```

The <start> and <factor> values come from the previous `TUNING_TOWER` command. They are '0' and '0.005' respectively.



</br></br>
---
## Configuration

Once the best pressure advance value is known, set it in the `printer.cfg` file:

```ini
[extruder]
pressure_advance = <calculated_value>
```



</br></br>
---
## References

[https://www.klipper3d.org/Pressure_Advance.html]
