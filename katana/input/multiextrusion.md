---
## Multi Extrusion
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| preSwitchCode | <code>string array</code>| Code added before changing extruder | - | empty |
| postSwitchCode | <code>string array</code>| Code added after changing extruder | - | empty |
| dualOverlap | <code>int</code>| The amount of overlap in microns when dual extruding | >=0 | 1500 |

> The multi extrusion variables are ignored if only 1 extruder exists and/or only 1 is used.
