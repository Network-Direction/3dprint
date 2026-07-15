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



</br></br>
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
---
## Tuning





