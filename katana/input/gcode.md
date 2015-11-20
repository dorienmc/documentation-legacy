---
## Gcode

In the gcode settings you can define the output of Katana. Start and end gcodes are different per printer (and are in the printer settings in the interface). Katana also has a feature to insert custom codes every x layers. We support a wide range of gcode flavours to cater to almost every FDM machine out there.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
|startGcode| `string array` | Gcode to add on the top of the file | nonempty | ["G21", "G28", "G1 Z5 F5000", "G90", "G92 E0", "M82", "G92 E0"] |
|endGcode| `string array`  Gcode to add at the bottom of the file | nonempty | ["G92 E0", "M104 S0", "G28 X0", "M84"] |
|_customGcode_| `string array` | Custom gcode to add periodically | - | empty |
|_repeatEvery_ | `int` | Customgcode is repeated every _repeatEvery_ lines | >=0 | 0 |
|_changeLayerGcode_| `string array` | Gcode to add between layers | - | empty |
| gcodeFlavour | `string` | Specific gcode flavour | See below | "GCODE_FLAVOR_REPRAP" |

> Available gcode flavours are: GCODE_FLAVOR_REPRAP, GCODE_FLAVOR_ULTIGCODE, GCODE_FLAVOR_MAKERBOT, GCODE_FLAVOR_BFB, GCODE_FLAVOR_MACH3, GCODE_FLAVOR_REPRAP_VOLUMATRIC, GCODE_FLAVOR_LINUXCNC
