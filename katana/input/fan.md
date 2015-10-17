---
## Fan
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| fullspeedLayer | <code>unsigned int</code>| Layer number where the fan reaches its maximum value | - | 0 |
| min | <code>unsigned int</code>| Minimal fanspeed | >0 | 0 |
| max | <code>unsigned int</code>| Maximal fanspeed | >= Fan.min | 0 |
| _smart_ | <code>bool</code>| True when smart options are used, false otherwise | - | FALSE |
| factor | <code>unsigned int </code>| Percentage the fanspeed can be increased with at most (when layer printing is to fast, see minimalSeconds) | [0,100] | 20 |
| minimalSeconds | `unsigned int` | If layer is printed in less than 'minimalSeconds' the fan should work harder | - | 42 |