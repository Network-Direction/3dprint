# G Code

## Overview

The programming language that tells the printer what to do. This is similar to assembly code in some ways.

This is the language of machines in general, such as CNC machines, laser cutters, and engravers. It's not just for 3d printers.

You don't generally need to write your own g-code. However, knowing the basics helps when it comes to using macros, and sometimes with troubleshooting.

> [!NOTE]
> There are some differences in gcode between CNC machines and 3d printers.
> This article is only for 3d printers.


</br></br>
### Commands
G-codes start with a letter like 'G' or 'M'.

Some commands take an extra parameter, which also starts with a letter. For example, `M104 S210`


</br></br>
### Parameters

Letters like 'S', 'T', 'V', and others are used as arguments to a command to set values.

For example, in `M104 S210`, the 'm104' part is the command to heat the nozzle. The 'S210' is the temperature to set it to.

Here are some of the letters and what they are for. The 'name' is sometimes historical, and doesn't always accurately represent the use on a 3d printer.


</br></br>
| Letter | Name       | Usage                                                             |
| ------ | ---------- | ----------------------------------------------------------------- |
| S      | Speed      | Sets temperatures or fan speeds                                   |
| X      | Coordinate | An X target coordinate                                            |
| Y      | Coordinate | A Y target coordinate                                             |
| Z      | Coordinate | A Z target coordinate                                             |
| F      | Feedrate   | Usually the speed the print head moves at                         |
| E      | Extrude    | Used with extruder commands. Defines how much filament to extrude |




</br></br>
## Commands

### Geometric Commands

Geometric commands control the motion and positioning of the printer's nozzle. These commands start with a 'G', and are followed by a number.


</br></br>
#### Move - G0 and G1

These are linear movement commands. It tells the print head where to go, using X, Y, Z coordinates, and what speed to move at. The print head will move there in a straight line.

`G0` is a _rapid move_, while `G1` is a _controlled move_. In modern 3d printing, they functionally the same thing.

</br></br>
**Arguments:**

| Argument | Description                            |
| -------- | -------------------------------------- |
| `X`      | The X coordinate posistion             |
| `Y`      | The Y coordinate posistion             |
| `Z`      | The Z coordinate posistion             |
| `F`      | Speed of the print head move in mm/min |
| `E`      | The amount of filament to extrude      |

</br></br>
Not all coordinates are needed, only the ones that are changing.


</br></br>
**Example**

```gcode
G1 X100 Y50 Z0.2 F1500 E5    ; Move to 100,50,0.2 at a rate of 1500mm/min, and extrude 5mm of filament
```

</br></br>
A negative value on `E` will retract the filament:

```gcode
G1 E-1.0 F2100                ; Retracts 1mm of filament
```


</br></br>
#### Dwell - G4

Pauses the command queue, and waits for a period of time. With no arguments, this is the same as `M400`, which causes g-code processing to pause until all other commands are complete (eg, waits for heating or cooling)

</br></br>
**Arguments:**

| Argument | Description                            |
| -------- | -------------------------------------- |
| `S`      | Number of milliseconds to dwell        |
| `P`      | Number of seconds to dwell             |

</br></br>
If both arguments are supplied, `S` will take precedence.



</br></br>
#### Home Position - G28

Tells the printer to move the print head back to the home coordinates.

Often this needs to be done before other operations can be started.


</br></br>
#### Positioning - G90 and G92

`G90` sets absolute positioning mode. This means the printer will move exactly to the given coordinates. It will not move relative to its current position.

`G92` tells the printer to rename the current position as _zero_. This is like telling the printer where to start from.

</br></br>
**Example**

```gcode
G92 E0    ; Reset the extruder's position reference, and extrude nothing
```



</br></br>
### Miscellaneous Commands

These commands are for non-geometric tasks. They all start with the letter 'M', followed by a number.

Some of these commands need to complete before moving to the next command. Others start the command and move on immediately.


</br></br>
#### Relative Mode - M83

Sets the extruder to _relative_ mode. The extruder is also known as the **E-Axis**.

This means each extrusion commands will just extrude the amount of filament they're told to in the instruction, not work on a cumulative total.


</br></br>
#### Disable Motors - M84

Turns the motors off, typically when a print job has been completed.


</br></br>
#### Nozzle Temperature - M104 and M109

Both of these will set the nozzle temperature.

`M104` will set the temperature, and let the printer move on to the next command while the hot end heats up.

`M109` requires the hot end to heat up to the given temperature before the printer moves on to the next command.

</br></br>
**Arguments:**

| Argument | Description                            |
| -------- | -------------------------------------- |
| `S`      | The temperature to set                 |

</br></br>
**Example**

```gcode
M104 S220
```


</br></br>
#### Bed Temperature - M140 and M190

Both set the bed temperature. 

`M140` will set the temperature, and let the printer move on to the next command while the hot end heats up.

`M190` requires the bed to heat up to the given temperature before the printer moves on to the next command.

</br></br>
**Arguments:**

| Argument | Description                            |
| -------- | -------------------------------------- |
| `S`      | The temperature to set                 |

</br></br>
**Example**

```gcode
M104 S220
```


</br></br>
#### Acceleration - M204

Sets the preferred acceleration of the hotend.


</br></br>
#### Cancel Objects - M486

Used to cancel specific items on the print bed. When printing multiple items at once, you may want to cancel one of them without cancelling the entire print job. This command can do this.

To support this, the slicer needs:
* Label Objects:    Enabled
* Exclude Objects:  Enabled

</br></br>
**Arguments:**

| Argument   | Description                               |
| ---------- | ----------------------------------------- |
| `C`        | Cancel the current object                 |
| `P<index>` | Cancel an object with a given index       |
| `S<index>` | Set the index of the current object       |
| `T<index>` | Reset state and set the number of objects |
| `U<index>` | Un-cancel object with the given index     |



</br></br>
### Ignored Commands

The slicer will create a gcode file which is sent to the printer for processing.

The Klipper firmware will ignore some of the codes, as it does not use them.

These include:
* M201
* M203
* M205


</br></br>
---
## References

Gcodes can be found here: [https://marlinfw.org/docs/gcode/G004.html]


