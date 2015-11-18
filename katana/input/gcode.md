---
## Gcode
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
|startGcode| <code>string array</code>| Gcode to add on the top of the file | nonempty | ["G21", "G28", "G1 Z5 F5000", "G90", "G92 E0", "M82", "G92 E0"] |
|endGcode| <code>string array</code>| Gcode to add at the bottom of the file | nonempty | ["G92 E0", "M104 S0", "G28 X0", "M84"] |
|_customGcode_| `string array` | Custom gcode to add periodically | - | empty |
|_repeatEvery_ | `int` | Customgcode is repeated every _repeatEvery_ lines | >=0 | 0 |
|_changeLayerGcode_| <code>string array </code>| Gcode to add between layers | - | empty |
| gcodeFlavour | <code>string</code>| Specific gcode flavour | See below | "GCODE\_FLAVOR\_REPRAP" |

> Gcode flavours: {"GCODE\_FLAVOR\_REPRAP", "GCODE\_FLAVOR\_ULTIGCODE", "GCODE\_FLAVOR\_MAKERBOT", "GCODE\_FLAVOR\_BFB", "GCODE\_FLAVOR\_MACH3", "GCODE\_FLAVOR\_REPRAP\_VOLUMATRIC", "GCODE\_FLAVOR\_LINUXCNC"}
