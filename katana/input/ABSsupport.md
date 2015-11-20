---
## ABS support
Printing with ABS might give warped corners at the bottom of the model, to prevent this ABS corner support can be used.
Katana automatically generates these ABS corners, so there is no need to model these or add them manually before slicing.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| activationAngle | `int` | Give all corners sharper than this ABS support (in degrees) | [0,360) | 90 |
| radius | `int`| Radius of support circles in micron | >0 | 1000 |
| overlap | `int` | Percentage of the radius that overlaps with the model | [0,100] | 100 |
| numberOfLayers | `int` | Number of layers in which the ABS support is added | >=0 | 2 |

> An overlap of 100% means that the center of the circle is on the corner and an overlap
of 0% means that only the wall of the circle touches the corner. We advice to use 100%.
