---
## Support
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>unsigned int</code>| Infill amount for support | (0,100] | 0|
| activationAngle | <code>unsigned int</code>| Minimal angle where support is needed | [0,90] | 0 |
| orientationAngle | `int` | ?? | >=0 | 0 |
| wallDistance |  `int` | ?? | >0 | 1000 |
| supportEverywhere | <code>unsigned int</code>| Toggle support everywhere | - | FALSE |
| supportPlatform | <code>unsigned int</code>| Toggle support platform | - | FALSE|
| supportModel | `bool` | Toggle support model only | - | FALSE |
| pattern | <code>int</code>| Type of support | {0,1} | 0 |
| extruder | <code>unsigned int</code>| ID of the extruder that will be used to print the support (-1 if not used) | >=0 | -1 |
| XYDistance | <code>unsigned int</code>| Distance of the support material from the print, in the X/Y directions | - | 0 |
| ZDistance | <code>unsigned int</code>| Distance from the top/bottom of the support to the print | - | 0 |