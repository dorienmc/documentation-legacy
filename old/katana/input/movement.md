---
## Movement

Movement settings define how and how fast the extruders move to lay down the materials. They have a big effect on the quality of the final print.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| combing | `bool`| Toggle combing: printhead avoids voids in the model such that any oozing is done inside the model | - | FALSE |
| oozeShield | `bool`| Toggle ooze shield: a shield around the model on which an extruder can be wiped clean, mostly used for multiple extrusion | - | FALSE |
| printSpeed| `int` | Default Print speed in mm/s | >0 | 60 |
| travelSpeed| `int` | Default Travelling speed in mm/s | >0 | 80 |
| innerWallSpeed| `int` | Default Inner Wall speed in mm/s | >0 | 50 |
| outerWallSpeed| `int` |  Default Outer Wall speed in mm/s | >0 | 40 |
| infillSpeed | `int` |  Default Infill speed in mm/s | >0 | 60 |
| speedupLayers | `int` | Layer number where the fan reaches its maximum value | >0 | 10|
| smart | `bool` | Toggle smartspeed | - | FALSE |
| minFactor | `int` | Percentage the speed can at most reduce with (see maximalSeconds) | [0,100] | 60 |
| maxFactor | `int` | Percentage the speed can at most increase with (see minimalSeconds) | [0,100] | 0 |
| minimalSeconds | `int` | Minimal number of seconds the printing of a layer should take | >=0 | 20 |
| maximalSeconds | `int` | Maximal number of seconds the printing of a layer should take | >= Movement.minimalSeconds | 25 |

> The parameters `minFactor`, `maxFactor`, `minimalSeconds` and `maximalSeconds` are only mandatory if `smartSpeed` is set to TRUE.
