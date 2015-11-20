---
## Extruder

With the extruder settings you can define the number of extruders, temperatures and filaments used.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| temperature | `int` | Extruder temperature | >=0 | 0|
| firstLayersTemperature | `int` | Temperature applied to the first layer(s) | >=0 | 0|
| material | `string` | Material name, currently only for analysis | - | "Invisible filament" |
| feedRate | `int` | Percentage of material fed to the extruder | >0 | 100 |
| filamentDiameter | `int` | Filament diameter in microns (0.001mm = 1 micron)| >0 | 1750 |
| nozzleSize | `int` | Nozzle diameter in microns | >0 | 400 |
