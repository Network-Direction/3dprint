# G Code

The programming language that tells the printer what to do. This is similar to assembly code in some ways.

G-codes start with a letter like 'G' or 'M'.

Some commands take an extra parameter, which also starts with a letter. For example, `M104 S210`


</br></br>
## Commands

### Geometric Commands

Geometric commands control the motion and positioning of the printer's nozzle. These commands start with a 'G', and are followed by a number.

Common Commands:

| Command | Description                                                              |
| ------- | ------------------------------------------------------------------------ |
| G0      | Move the print head in a straight line                                   |
| G1      | Move the print head in a straight line                                   |
| G28     | Auto home - Tell the printer to move the print head to home coordinates  |
| G90     | Set absolute positioning mode. The printer will use absolute coordinates |
| G91     |                                                                          |
| G92     |                                                                          |


</br></br>
### Miscellaneous Commands

These commands are for non-geometric tasks. They all start with the letter 'M', followed by a number.

Some of these commands need to complete before moving to the next command. Others start the command and move on immediately.

| Command | Description                                                                     |
| ------- | ------------------------------------------------------------------------------- |
| M83     |                                                                                 |
| M104    | Set the nozzle temperature, and move to the next command                        |
| M109    | Set the nozzle temperature, and wait until it has been reached before moving on |
| M140    | Set the print bed temperature, and move on                                      |
| M190    | Set the print bed temperature and wait                                          |
| M204    | Set the preferred acceleration                                                  |


</br></br>
> [!NOTE]
> The slicer will create a gcode file which is sent to the printer for processing
> The Klipper will ignore some of the codes in this file, such as M201, M203, and M205







