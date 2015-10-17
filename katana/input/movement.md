---
## Movement
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| combing | <code>bool</code>| Toggle combing | - | FALSE |
| oozeShield | <code>bool</code>| Toggle ooze shield | - | FALSE |
| printSpeed| <code>unsigned int</code>| Print speed | >0 | 0 |
| travelSpeed| <code>unsigned int</code>| Travelling speed | >0 | 0 |
| innerWallSpeed| <code>unsigned int</code>| Innerwall speed | >0 | 0 |
| outerWallSpeed| <code>unsigned int</code>|  Outerwall speed | >0 | 0 |
| infillSpeed | <code>unsigned int</code>|  Infill speed | >0 | 0 |
| speedupLayers | <code>unsigned int</code>| Layer number where the fan reaches its maximum value | >0 | 0|
| firstLayersWidthFactor | <code>unsigned int</code>| Increase of extrusion width for first layers | - | 0 |
| wipeTowerSize |  <code>unsigned int</code>| Size of the wipe tower for multi extrusion | - | 0 |
| smart | `bool` | Toggle smartspeed | - | FALSE |
| minfactor | `unsigned int` | Percentage the speed can at most reduce with (see maximalSeconds) | [0,100] | 0 |
| maxfactor | `unsigned int` | Percentage the speed can at most increase with (see minimalSeconds) | [0,100] | 0 |
| minimalSeconds | `unsigned int` | Minimal number of seconds the printing of a layer should take | - | 0 |
| maximalSeconds | `unsigned int` | Maximal number of seconds the printing of a layer should take | >= Movement.minimalSeconds | 0 |