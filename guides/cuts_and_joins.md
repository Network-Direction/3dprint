# Cutting and Joining Parts

## Overview

With a smaller print bed, there are times that a print needs to be cut into parts and joined later.

In Orca slicer, there is a **cut** tool in the **prepare** tab.

There are two modes:
* Planar
* Dovetail


</br></br>
These can be used for simple cuts, which allows parts to be glued back together.

Alternatively, we can use a dovetail joint, or connectors, to _potentially_ join parts without glue. Or, they can be used as guides, so gluing pieces together is more accurate.

The problem is, printer tolerances mean that we can't just print up some joints. There's a few settings to be tuned.


</br></br>
> [!WARNING]
> This guide assumes that you have already calibrated the tolerance of your printer


</br></br>
> [!NOTE]
> It seems likely that settings mentioned here will vary based on filament, and possibly the number of walls.




</br></br>
---
## Types

### Planar

A planar cut is a straight cut down an object.

</br></br>
<img width="390" height="358" alt="image" src="https://github.com/user-attachments/assets/343e4f6c-bc76-40de-a25b-a2f157ed6d34" />


</br></br>
If you just want to cut an object up, just use this cut and adjust it's position.

If you want to join the objects you're cutting, you can click **add connectors**.

</br></br>
<img width="290" height="147" alt="image" src="https://github.com/user-attachments/assets/a044c41f-dbf4-4655-91eb-e6389f91c059" />

</br></br>
There are three types of connectors:
* Plug
* Dowel
* Snap

</br></br>
<img width="335" height="130" alt="image" src="https://github.com/user-attachments/assets/d9de51c0-4b1e-45d0-a507-fe248b492aec" />

</br></br>
While in this mode, you will see the cross section of your object. Click on that cross section to add connectors.

</br></br>
<img width="807" height="311" alt="image" src="https://github.com/user-attachments/assets/3d16bc5c-2f03-4ae6-8e3b-916cf10d54b3" />


</br></br>
#### Plug Connectors

The plug connector is a simple part extruding from one side of the cut. The other side of the cut will have a corresponding hole for the plug to be inserted into.

There are two styles available:
* **Prism** - A simple cylinder (shown on the right in the image below)
* **Frustrum** - A tapered cylinger (shown on the left)

</br></br>
<img width="239" height="214" alt="image" src="https://github.com/user-attachments/assets/8e03b7dc-62c5-45f4-8fde-dfa3c92be8be" />


</br></br>
There are four shapes for plugs:
* Circle
* Hexagon
* Square
* Triangle

</br></br>
<img width="460" height="280" alt="image" src="https://github.com/user-attachments/assets/5a48841b-f7da-4659-9163-1767f0af1780" />

</br></br>
All these shapes support both _prism_ and _frustrum_ types.


</br></br>
> [!TIP]
> Adding connectors will leave holes on one side of the cut. This will likely need supports when printing.
>
> Use the [support trick](supports.md) to make supports easier to remove from the holes.



</br></br>
#### Dowel Connectors

A dowel connector is very similar to a plug. The difference is, both sides of the cut object have a hole. A _dowel_ piece is created as a separate object.

</br></br>
<img width="467" height="438" alt="image" src="https://github.com/user-attachments/assets/c2dddb43-4779-4839-95e9-68be0b2ca114" />

</br></br>
_Prism_ is the only type available for a dowel connector.

All four shapes (circle, hexagon, square, and triangle) are supported for dowels.

</br></br>
<img width="323" height="127" alt="image" src="https://github.com/user-attachments/assets/3e59e1e9-0ef9-47a2-8552-6c20a241a296" />



</br></br>
#### Snap Connectors

Snap connectors create something that looks like a plug, but it tapered in the middle (called the _bulge_), and has a split down the centre.

These are meant to create a snap fit between the two parts. This requires the material to have a bit of flexibility, so it may not be suitable in all cases.

</br></br>
<img width="220" height="202" alt="image" src="https://github.com/user-attachments/assets/2e6bfaed-787a-4583-bc5e-1f878ad5bb36" />

</br></br>
The type and shape are fixed for the snap connector. However, it does come with a lot of configurable settings.

</br></br>
<img width="380" height="294" alt="image" src="https://github.com/user-attachments/assets/dcffdb50-8d18-4b5b-8778-cc91f26db66a" />




</br></br>
---
### Dovetail

The dovetail will cut the model, and leave a _dovetail_ joint, just like you [might see in woodworking](https://en.wikipedia.org/wiki/Dovetail_joint).

</br></br>
<img width="381" height="425" alt="image" src="https://github.com/user-attachments/assets/196726e8-b9d9-4369-a3a4-60d08b760bda" />


</br></br>
Here are some settings that I have found to be useful.

For larger dovetails:

| Setting         | Value   |
| --------------- | ------- |
| Depth           | 6.0mm   |
| Depth Tolerance | 0.20mm  |
| Width           | 20.00mm |
| Width Tolerance | 0.35mm  |
| Flap Angle      | 60°     |
| Groove Angle    | 0°      |


</br></br>
<img width="383" height="164" alt="image" src="https://github.com/user-attachments/assets/e6fe8972-3e7f-4e5f-9324-763186a4a002" />



</br></br>
For smaller dovetails:

| Setting         | Value  |
| --------------- | ------ |
| Depth           | 3.00mm |
| Depth Tolerance | 0.19mm |
| Width           | 3.00mm |
| Width Tolerance | 0.32mm |
| Flap Angle      | 60°    |
| Groove Angle    | 0°     |


</br></br>
<img width="384" height="169" alt="image" src="https://github.com/user-attachments/assets/8411c144-2701-4b30-8001-fe7e6eb027f4" />


</br></br>
These settings will create a tight fit that will generally mean you won't need glue.

For a looser fit, increase the width tolerance a little.



</br></br>
---
## Tuning

Once you perform a cut, that creates two objects. The way the object is cut then becomes part of those objects.

What I'm trying to say is, you can't edit cuts after they're done. This makes tuning these settings a bit of a pain.

</br></br>
The best option is to start a new project in orca, right click the plate, and add a primitive. A cube will do.

Then, make sure all your other settings are typical of a normal print. That is, number of walls, filament type, speed, etc.

</br></br>
Now, cut this object using the settings above. That is, a planar cut with connectors, or a dovetail cut. Slice the objects, print them, and see how they go.

From there, adjust the tolerances to make the fit tighter or looser as needed.







