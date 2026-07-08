# G Code

The programming language that tells the printer what to do. This is similar to assembly code in some ways.

This is the language of machines in general, such as CNC machines. It's not just for 3d printers.

You don't generally need to write your own g-code. However, knowing the basics helps when it comes to using macros, and sometimes with troubleshooting.

</br></br>
G-codes start with a letter like 'G' or 'M'.

Some commands take an extra parameter, which also starts with a letter. For example, `M104 S210`


</br></br>
## Commands

### Geometric Commands

Geometric commands control the motion and positioning of the printer's nozzle. These commands start with a 'G', and are followed by a number.


</br></br>
#### Move - G0 and G1

Move the print head in a straight line. It tells the print head where to go, using X, Y, Z coordinates, and what speed to move at.

`G0` is a _rapid move_, while `G1` is a _controlled move_.


</br></br>
#### G28 - Home

Tells the printer to move the print head back to the home coordinates.

Often this needs to be done before other operations can be started.


</br></br>
#### G90 - Positioning

Sets absolute positioning mode. This means the printer will move exactly to the given coordinates. It will not move relative to its current position.



</br></br>
### Miscellaneous Commands

These commands are for non-geometric tasks. They all start with the letter 'M', followed by a number.

Some of these commands need to complete before moving to the next command. Others start the command and move on immediately.


</br></br>
#### Nozzle Temperature - M104 and M109

Both of these will set the nozzle temperature.

`M104` will set the temperature, and let the printer move on to the next command while the hot end heats up.

`M109` requires the hot end to heat up to the given temperature before the printer moves on to the next command.


</br></br>
#### Bed Temperature - M140 and M190

Both set the bed temperature. 

`M140` will set the temperature, and let the printer move on to the next command while the hot end heats up.

`M190` requires the bed to heat up to the given temperature before the printer moves on to the next command.


</br></br>
#### Acceleration - M204

Sets the preferred acceleration of the hotend.


</br></br>
### Ignored Commands

The slicer will create a gcode file which is sent to the printer for processing.

The Klipper firmware will ignore some of the codes, as it does not use them.

These include:
* M201
* M203
* M205





