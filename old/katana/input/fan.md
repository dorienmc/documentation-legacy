---
## Fan

The fan on a 3D printer can be used to cool the layers while printing to ensure a good print quality. Normally, printers
run their fan at 100% while printing. Using custom settings in Katana however, you can influence this behavior.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| fullSpeedLayer | `int` | Layer index where the fan reaches its maximum value | >0 | 10 |
| min | `int` | Minimal fan speed in mm/s| >0 | 35 |
| max | `int` | Maximal fan speed in mm/s | >= Fan.min | 90 |
| smart | `bool` | True when smart options are used, false otherwise | - | FALSE |
| factor | `unsigned int ` | Maximal percentage the fanspeed can be increased with at most (when layer printing is to fast, see minimalSeconds) | [0,100] | 20 |
| minimalSeconds | `int` | If layer is printed in less than 'minimalSeconds' the fan should work harder | >=20 | 42 |

> The `factor` and `minimalSeconds` variables are only mandatory when `smart` is set to TRUE, which means that the fan speed is increased when the printing of a layer is done very fast (takes less than `minimalSeconds`).
