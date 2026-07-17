# Mainsail Tools and Customizations

## Macros

There are several [macros](../macros.README.md) which are included by default, and of course, we can add our own. These show up in a widget on the dashboard:

<img width="420" height="342" alt="image" src="https://github.com/user-attachments/assets/64da4451-bacd-42f3-ad9f-6bbfcc66aa09" />


</br></br>
### Hiding Macros

That's a bit cluttered though. There's some macros there we use regularly, some occasionally, and some that we never touch manually.

To tidy this up, go to **Interface Settings**, then to the **Macros** tab.

Here, we can toggle which macros are visible, and which aren't. This is useful to hide things like `END_PRINT`, which is called automatically at the end of a print, not manually.

<img width="689" height="341" alt="image" src="https://github.com/user-attachments/assets/71a3cc03-9a58-4cf2-aa69-38579edef873" />


</br></br>
### Grouping Macros

We can take this one step further and group macros into categories. In the **Macros** settings, change the **Management** type to **Expert**.

This will change the view to include _Groups_. There are none by default, so click **Add Group**.

Now give the group a name. I'm going to create one for **Calibration**. Under **Status** I'm going to click the 3rd button to hide this group while the printer is active.

Next, I'll add the **PID_BED** and **PID_EXTRUDER** macros to this group.

<img width="688" height="406" alt="image" src="https://github.com/user-attachments/assets/3ec8734f-022b-42c0-a70d-4ee3de93bab4" />


</br></br>
Repeat this to create more groups as you need to.



</br></br>
---
## Toolhead Position

The toolhead widget in the dashboard lets us control the position of the toolhead, both while the printer is idle, and while it is printing.


</br></br>
### Idle Printer

While the printer is idle, we can use buttons to move the toolhead. The home button sends a `G28` code to move the toolhead to the home position.

The 'disable motors' button turns off the stepper motors, so we can physically move the print head. Useful for maintenance on the printer.

The three bars following that lets us move the print head to different locations. I like using the '+25' button on the Z-axis to raise the tool head so I can get access to the nozzle for cleaning.


</br></br>
### Print in Progress

Here is the toolhead widget while printing is in progress:

<img width="400" height="521" alt="image" src="https://github.com/user-attachments/assets/2637c69d-cba2-47fb-9f7a-466a4de75177" />

</br></br>
We can finetune the Z-Offset while printing here, to test different heights in real time.

We've also got the option to slow down or speed up the print using the speed factor setting.

The top of the widget shows some information about current settings. The `position` is set to `absolute`. This will have been set using a `G90` code within the gcode file or in a start print macro.

The `adaptive-` part shows the bed mesh profile that was loaded. In this case, it was set dynamically as part of the print job.


</br></br>
### Customization

To customize, click the gears in the top right of mainsail to get the _Interface Settings_ window. Then go to _Control_.

Optionally change the style of the widget:

<img width="678" height="146" alt="image" src="https://github.com/user-attachments/assets/9d6451de-f82d-46fb-b920-0637ddeb0ee0" />

</br></br>
Additionally, you can change the buttons available to move the toolhead. For example, you may want an option to move the Z-axis up by 100mm.

<img width="683" height="64" alt="image" src="https://github.com/user-attachments/assets/b46ff9f8-2f4d-48f6-9ef3-ac5062242179" />



