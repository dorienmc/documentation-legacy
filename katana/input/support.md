---
## Support
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>unsigned int</code>| Infill percentage for support | (0,100] | 10 |
| activationAngle | <code>int</code>| Minimal angle where support is needed | [0,90] | 15 |
| orientationAngle | `int` | Angle of support on the XY plane, counter-clockwise around the z-axis (as seen from above) | [0,359] | 45 |
| wallDistance |  `int` | Distance between the border of the support and the support box (see below). | >0 | 4000 |
| supportEverywhere | <code>unsigned int</code>| Toggle support everywhere | - | FALSE |
| supportPlatform | <code>unsigned int</code>| Toggle support platform, only between bed and model | - | TRUE|
| supportModel | `bool` | Toggle support model only, only between parts of the model | - | FALSE |
| pattern | <code>int</code>| Type of support | {0,1} | 0 |
| extruder | <code>int</code>| ID of the extruder that will be used to print the support | >=0 | 0 |
| XYDistance | <code>int</code>| Distance of the support material from the print, in the X/Y directions (in microns) | >=0 | 700 |
| ZDistance | <code>int</code>| Distance from the top/bottom of the support to the print (in microns) | >=0 | 150 |

> A support box is a rectangular structure that increases the strength of the support, choose a very large number for the wallDistance to use no support box.

> Support can have to pattern types "SUPPORT\_GRID" (`pattern` equals 0) or "SUPPORT\_LINES" (`pattern` equals 1). 
