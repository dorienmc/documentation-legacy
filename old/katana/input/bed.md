---
## Bed

The bed settings contain things like the size of your 3D printer and temperatures for the heated bed if your printer has one.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| temperature | `int` | Temperature of heated bed in degrees celsius | >=0 | 0 |
| firstLayerTemperature | `int` | Temperature of heated bed for the first layer(s) in degrees celsius | >=0 | 0 |
| xLength | `int` | Bed length in the x direction in microns | >0 | 200000 |
| yLength | `int` | Bed length in the y direction in microns | >0 | 200000 |
| zLength | `int` | Bed length in the z direction in microns | >0 | 200000 |
