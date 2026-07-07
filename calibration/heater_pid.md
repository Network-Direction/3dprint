# Heater PID Calibration

## What is it?

PID is Proportional, Integral, and Derivative. It refers to the steps a controller takes to maintain a steady state of some function.

In this case, the function is the temperature of the bed and the extruder.

The purpose of tuning this is to ensure that the print bed and hot end are heated in the least time possible, and that the temperature is maintained.


</br></br>
---
## How it Works

The Klipper firmware heats and cools the print bed and extruder a few times and measures results.


</br></br>
---
## Calibration

This can be run as Klipper commands, but it's easier to use the built-in macros.

1. Dashboard > Macros area
2. Click the drop down next to 'PID BED'
3. Enter the temperature you typically use, such as 60
4. Wait for ages
   Must be patient, this takes a while, 15min or so
   On the temperature graph you will see the print bed heating up and cooling repeatedly
   When it's done, some new values will appear in the console
6. Run the macro for 'PID EXTRUDER', using your typical temperature
   This is much faster to run
   New values will appear in the console when done
7. Save the new configuration



### Commands

If the macros aren't available, you can run these commands:

Calibrate the bed:
```gcode
PID_BED TARGET=60
```

Calibrate the extruder:
```gcode
PID_EXTRUDER TARGET=220
```

Save the config:
```gcode
SAVE_CONFIG
```



</br></br>
---
## References
https://www.obico.io/blog/klipper-pid-tuning/

