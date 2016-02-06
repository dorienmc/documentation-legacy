---
## Multi Extrusion

Multi extrusion settings are needed when your printer has multiple extruders and you want to use this functionality.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| preSwitchCode | `string[]` | Code added before changing extruder | - | empty |
| postSwitchCode | `string[]` | Code added after changing extruder | - | empty |
| dualOverlap | `int` | The amount of overlap in microns when dual extruding | >=0 | 1500 |

> The multi extrusion variables are ignored if only 1 extruder exists and/or only 1 is used.
