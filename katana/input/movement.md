---
## Movement
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| combing | <code>bool</code>| Toggle combing: printhead avoids voids in the model such that any oozing is done inside the model | - | FALSE |
| oozeShield | <code>bool</code>| Toggle ooze shield: a shield around the model on which an extruder can be wiped clean, mostly used for multiple extrusion | - | FALSE |
| printSpeed| <code>int</code>| Default Print speed in mm/s | >0 | 60 |
| travelSpeed| <code>int</code>| Default Travelling speed in mm/s | >0 | 80 |
| innerWallSpeed| <code>int</code>| Default Inner Wall speed in mm/s | >0 | 50 |
| outerWallSpeed| <code>int</code>|  Default Outer Wall speed in mm/s | >0 | 40 |
| infillSpeed | <code>int</code>|  Default Infill speed in mm/s | >0 | 60 |
| speedupLayers | <code>int</code>| Layer number where the fan reaches its maximum value | >0 | 10|
| smart | `bool` | Toggle smartspeed | - | FALSE |
| minFactor | `int` | Percentage the speed can at most reduce with (see maximalSeconds) | [0,100] | 60 |
| maxFactor | `int` | Percentage the speed can at most increase with (see minimalSeconds) | [0,100] | 0 |
| minimalSeconds | `int` | Minimal number of seconds the printing of a layer should take | >=0 | 20 |
| maximalSeconds | `int` | Maximal number of seconds the printing of a layer should take | >= Movement.minimalSeconds | 25 |

> Combing is disabled for the moment, as it does not give the desired results and is absolutely not time efficient!

> The parameters `minFactor`, `maxFactor`, `minimalSeconds` and `maximalSeconds` are only mandatory if `smartSpeed` is set to TRUE.
