# Macros

Macros are a script of g-code to run common commands. For example:
* Commands to run before a print job
* Commands to run after a job completes
* Extrude a test line before starting
* Load or unload filament




</br></br>
---
## Calling Macros from Orca

Macros can be called automatically by referring to them in the gcode. This means the slicer needs to be aware of the macros so it can embed these commands.

In Orca slicer, edit the printer settings, and go to the **Machine G-code** tab.

This contains an area when you can add custom G-code at various points of the print. The two most useful ones are:
* Machine start G-code
* Machine end G-code

</br></br>
These areas run specific commands every time a job starts and ends.

In **Machine start G-code**, replace anything that's already there with:

```gcode
SET_PRINT_STATS_INFO TOTAL_LAYER_COUNT=[total_layer_count]
START_PRINT BED_TEMP=[first_layer_bed_temperature] EXTRUDER_TEMP=[first_layer_temperature]
```

</br></br>
This adds some useful information to the gcode file about the print, such as the total layer count.

The second line is the important one. This calls the [`START_PRINT`](print_start.cmd) macro, and passes the bed and extruder temperature.

> [!WARNING]
> Make sure these macros exist in mainsail if you're going to use them.


</br></br>
In **Machine end G-code**, replace anything that's already there with:

```gcode
END_PRINT
```

</br></br>
This simply calls the [`END_PRINT`](print_end.cmd) macro at the end of a print job.




</br></br>
---
## Macro File

Macros can be placed directly in `printer.cfg`, but it is recommended to put them in a separate file, `macros.cfg`.

The `printer.cfg` file should 'include' this extra file.

```ini
[include macros.cfg]
```

</br></br>
<img width="270" height="128" alt="image" src="https://github.com/user-attachments/assets/a379af6f-5385-4f0a-840d-c014a283c69d" />

Mainsail includes a macro section on the dashboard containing any macros that have been defined.

These include the ones in `macro.cfg`, as well as some predefined ones from `mainsail.cfg`.


</br></br>
---
## Macro Format

### Starting a Macro

Macros all start with a line like this:

```ini
[gcode_macro MACRO_NAME]
```

This identifies the following code as being a macro, as well as giving it a name.


</br></br>
All macros must also have a line like this:

```gcode
gcode:
  ; Commands
```

This defines the start of the g-code. Commands listed under this must be indented (similar to a YAML file).


</br></br>
### Macro Code

Code within the macro can be:
* Jinja2 template code
* G-code
* Klipper commands
* Calls to other macros

For example, this clears the current state (a klipper command), and then heats the print bed:

```gcode
[gcode_macro EXAMPLE]
gcode:
    CLEAR_PAUSE         ; Klipper command
    M190 S60            ; gcode
```



</br></br>
### Arguments

Arguments can be provided to macros. For example, if we want to preheat the extruder, we can include a temperature to preheat it to.

This is done using a combination of jinja2 and `params`.

```gcode
[gcode_macro PREHEAT]
gcode:
    {% set extruder_temp = params.TEMP | default(220) | float %}
    M104 S{extruder_temp}
```


</br></br>
In this example we can see:
* The macro takes an argument called `TEMP`
* This is an optional argument, as it has a default value
* The datatype for the argument is a `float`
* This value is assigned to the `extruder_temp` variable
* The `M104` command uses the `extruder_temp` variable to preheat the extruder


</br></br>
To use arguments, call a macro like this:

```ini
PREHEAT TEMP=200
```

</br></br>
This calls a macro caled `PREHEAT`, and passes the value `200` as the `TEMP` argument.



</br></br>
### Flow Control and Variables

Flow control, like if, then, else, as well as looping, can be implemented using Jinja2.

Variables can be defined before the `gcode` area, or set within the `gcode` area using jinja templates.

```gcode
[gcode_macro HELLO_BED]
variable_greeting_temp: 40      # Variable set BEFORE gcode:
gcode:
    {% set bed_temp = printer.heater_bed.temperature %}   ; Variable set WITHIN gcode:

    {% if bed_temp > greeting_temp %}
        { action_respond_info("Bed is warm!") }
    {% else %}
        { action_respond_info("Bed is cool.") }
    {% endif %}
```

The example above:
* Sets a variable called `variable_greeting_temp` and sets it to 40
* Gets the current bed temperature, and assigns it to the `bed_temp` variable
* Uses an if/else block to print a message based on the bed temperature



