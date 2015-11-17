---
## Fan
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| fullSpeedLayer | <code>int</code>| Layer index where the fan reaches its maximum value | >0 | 10 |
| min | <code>int</code>| Minimal fan speed in mm/s| >0 | 35 |
| max | <code>int</code>| Maximal fan speed in mm/s | >= Fan.min | 90 |
| smart | <code>bool</code>| True when smart options are used, false otherwise | - | FALSE |
| factor | <code>unsigned int </code>| Maximal percentage the fanspeed can be increased with at most (when layer printing is to fast, see minimalSeconds) | [0,100] | 20 |
| minimalSeconds | `int` | If layer is printed in less than 'minimalSeconds' the fan should work harder | >=20 | 42 |

> The `factor` and `minimalSeconds` variables are only mandatory when `smart` is set to TRUE, which means that the fan speed is increased when the printing of a layer is done very fast (takes less than `minimalSeconds`).
