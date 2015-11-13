---
## Extruder
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| temperature | <code>int</code>| Extruder temperature | >=0 | 0|
| firstLayersTemperature | <code>int</code>| Temperature applied to the first layer(s) | >=0 | 0|
| material | <code>string</code>| Material name, currently only for analysis | - | "Invisible filament" |
| feedRate | <code>int</code>| Percentage of material fed to the extruder | >0 | 100 |
| filamentDiameter | <code>int</code>| Filament diameter in microns (0.001mm = 1 micron)| >0 | 1750 |
| nozzleSize | <code>int</code>| Nozzle diameter in microns | >0 | 400 |
