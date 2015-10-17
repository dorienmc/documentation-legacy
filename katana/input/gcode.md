---
## Gcode
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
|startGcode| <code>string array</code>|Gcode to add on the top of the file | nonempty | empty |
|endGcode| <code>string array</code>|Gcode to add at the bottom of the file | nonempty | empty |
|_customGcode_| `string array` | Custom gcode to add every _repeatEvery_ lines | nonempty | empty |
|_repeatEvery_ | `int` | Customgcode is repeated every _repeatEvery_ lines | >=0 | 0 |
|_changelayerGcode_| <code>string array </code>|Gcode to add between layers |nonempty | empty |
|gcodeFlavour | <code>string</code>| Specific gcode flavour | See below | "GCODE\_FLAVOR\_REPRAP" |

Gcode flavours: {"GCODE\_FLAVOR\_REPRAP", "GCODE\_FLAVOR\_ULTIGCODE", "GCODE\_FLAVOR\_MAKERBOT", "GCODE\_FLAVOR\_BFB", "GCODE\_FLAVOR\_MACH3", "GCODE\_FLAVOR\_REPRAP\_VOLUMATRIC", "GCODE\_FLAVOR\_LINUXCNC"}