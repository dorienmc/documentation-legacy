---
## Support

When a model has overhangs, it is adviced to take a look at the support functionality of Katana. This can support these overhangs during printing to prevent your model from falling over. With multiple extruders, you can even set the support material to another extruder that for example has a water dissolvable material.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | `unsigned int` | Infill percentage for support | (0,100] | 10 |
| activationAngle | `int` | Minimal angle where support is needed | [0,90] | 15 |
| orientationAngle | `int` | Angle of support on the XY plane, counter-clockwise around the z-axis (as seen from above) | [0,359] | 45 |
| wallDistance |  `int` | Distance between the border of the support and the support box (see below). | >0 | 4000 |
| supportEverywhere | `unsigned int` | Toggle support everywhere | - | FALSE |
| supportPlatform | `unsigned int` | Toggle support platform, only between bed and model | - | TRUE|
| supportModel | `bool` | Toggle support model only, only between parts of the model | - | FALSE |
| pattern | `int` | Type of support | {0,1} | 0 |
| extruder | `int` | ID of the extruder that will be used to print the support | >=0 | 0 |
| XYDistance | `int` | Distance of the support material from the print, in the X/Y directions (in microns) | >=0 | 700 |
| ZDistance | `int` | Distance from the top/bottom of the support to the print (in microns) | >=0 | 150 |

> A support box is a rectangular structure that increases the strength of the support, choose a very large number for the wallDistance to use no support box.

> Support can have to pattern types "SUPPORT\_GRID" (`pattern` equals 0) or "SUPPORT\_LINES" (`pattern` equals 1).
