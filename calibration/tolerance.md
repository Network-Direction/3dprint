# Tolerance

This refers to how accurate the print jobs are. This is especially important if you are cutting and joining large parts, or are using nuts, bolts, screws, etc, in your prints.

Some tolerance is based around the quality of the printer, which can't really be changes.

Other tolerance issues happen when filament shrinks when cooling.

This calibration aims to determine how much shrinkage occurs, and compensates by scaling some area of the print up.


</br></br>
---
## Filament Compensation

Filament Settings > Filament (Tab) > Basic Information.

In this area there are two settings:
* Shrinkage (XY)
* Shrinkage (Z)

</br></br>
These relate to how much a filament shrinks once it has cooled. For PLA, this is negligable, but other filaments may need tuning.

If you were to print a cube, 10mm x 10mm x 10mm, it ideally should keep those sizes after completely cooling.

If, for example, it changes to 9.6mm wide, and 9.5mm high, then you will need to adjust the filament shrinkage settings.

In this example, the **XY** would be set to 96%, and the **Z** would be set to 95%.



</br></br>
---
## Hole and Contour

The _hole_ is any part that is cut out of a print. The _countour_ is the edge around the outside of the print.

This is shown well on [Bambu Labs Wiki](https://wiki.bambulab.com/en/software/bambu-studio/xy-hole-contour-compensation):

</br></br>
<img width="472" height="369" alt="image" src="https://github.com/user-attachments/assets/b1ee6a12-af2f-482d-b12f-9e77c211cae6" />


</br></br>
These settings are tuned in the slicer.

Process Settings > Quality (tab) > Precision.


</br></br>
---
### X-Y Hole Compensation

To calibrate this, start a new project in Orca Slicer. Right click on the build plate, and go to _handy models_. Then add **Orca Tolerance Test**.

</br></br>
<img width="426" height="175" alt="image" src="https://github.com/user-attachments/assets/e0ab8b63-dbc6-4951-9336-b60cebbd5cd0" />

</br></br>
<img width="612" height="235" alt="image" src="https://github.com/user-attachments/assets/9193c3ec-8af2-4059-87dc-5515d8d2cd8d" />

</br></br>
Now print the model. If the tolerance is good, the hexagonal insert should very easily slide out of the **0.4** hole, and it should fit snugly into the **0** hole.

Also, a **6mm** allan key should fit into the '0' hole.

</br></br>
If this does not happen, the tolerance is off.

If, for example, the allan key fits nicely into the **0.1** hole, then the tolerance is off by about 0.1mm.

Adjust the **X-Y Hole Compensation** setting in the slicer to **0.1**

</br></br>
Now repeat the process. You may need to adjust to smaller values to get it just right.

I found that **0.12** was a good value on my Ender 3, using PLA.



</br></br>
---
### X-Y Contour Compensation

This calibration involved printing a known sized object, and measuring the result.

I used the basic process in [Bambu Labs Wiki](https://wiki.bambulab.com/en/software/bambu-studio/xy-hole-contour-compensation).

</br></br>
Download the [XY Contour Calibration without Calipers](https://makerworld.com/en/models/2172676-xy-contour-calibration-without-calipers#profileId-2356707) model from Maker World.

Even though it says you can do this without calipers, using calipers is better.

</br></br>
Add the STL to Orca Slicer. There's a lot more here than we need, so I recommend slicing a bunch of material off the top, leaving about 15-20 layers.

The result is a 55mm disc.

</br></br>
Print the model, and wait for it to completely cool down. Then measure its width. It should come out to 55mm.

If not, it's time to tune our settings.

Subtract the result you got from 55mm. In my case, it was 54.6mm, so I was left with 0.4mm. Now halve that value. So, 0.2 in my case.

Now go to the Contour Compensation section, and add this value in.

</br></br>
<img width="360" height="69" alt="image" src="https://github.com/user-attachments/assets/72bc035e-a080-4b12-95c3-f0683a459ed9" />



