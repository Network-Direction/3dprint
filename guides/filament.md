# Filament

## Adhesiveness Category

Defines how strongly different materials will bond with each other.

Materials are given a category number. Materials with the same category value will bond well, and are considered to be compatible.

This is used in multi-filament printing, and for management of the prime tower. It enables the slicer to determine if a purge or transition tower is required between layers of different materials.




</br></br>
---
## Density

A measurement in grams-per-cubic-centermeter of how dense the material is.

This value is used to estimate how much of the material is needed for a particular print. This is how the estimated weight and cost of the print are calculated.

</br></br>
> [!NOTE]
> Adjusting this does not improve performance or quality.




</br></br>
---
## Shrinkage

As the material cools it may shrink, resulting in the print being smaller than expected.

The shrinkage parameters enable the slicer to scale the model appropriately, so the final product is the correct size.

* PLA does not shrink a lot; About 0.2-0.5%
* PETG, ABS, and Nylon shrink more; About 1-3%

</br></br>
In the filament profile, a percentage is set. When it is set to 100%, the slicer will assume there is no shrinkage at all.

If PLA shrinks 0.5%, set the shrinkage to 99.5%

This is set in two ways, based on the coordinates:
* Shrinkage (XY)
* Shrinkage (Z)

</br></br>
> [!NOTE]
> This setting helps improve tolerance.

