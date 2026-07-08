# Bed Leveling

## Goal

The goal of bed leveling is to make sure the print nozzle remains exactly the expected distance from the print bed.

The height of the nozzle from the bed is the Z-axis. For good quality prints, the Z-axis should be accurate to about 0.025mm.

The way this is achieved will depend on the model of printer. Some have automatic bed leveling, others use adjustment screws (this is called bed tramming).


</br></br>
---
## Calibration

Before starting:
1. Preheat the bed to normal temp
2. Preheat the extruder to a normal temp

In the mainsail UI, you can go to the 'heightmap' tab, and calibrate the bed mesh from there. Once it is done, you can also save it as a profile to be used later.

Alternatively, you can run the `BED_MESH_CALIBRATE` command, which effectively does the same thing.

This profile can now be loaded before print jobs start.



</br></br>
---
## Adaptive Calibration

You can aqlso use a macro that runs at the start of each print. This runs a command like `BED_MESH_CALIBRATE ADAPTIVE=1`.

This runs the same test, but it probes the area that will be used by the print job.

This is good, but will take longer for the print to start.



</br></br>
---
## References

[https://www.klipper3d.org/Bed_Level.html]

[https://www.klipper3d.org/Probe_Calibrate.html]
