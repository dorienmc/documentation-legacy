---
## Retraction
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>int</code>| Amount of retraction in microns (0 when not used) | >=0 | 4000 |
| speed | <code>int</code>| Speed at which the filament is retracted in mm/s | >0 | 20 |
| extruderSwitch | <code>int</code>| Amount of retraction when switching nozzle with dual-extrusion in microns (0 when not used) | >0 | 14500 |
| minimalExtrusionBeforeRetraction | <code>int</code>| The minimal amount of extrusion (in microns) that needs to be done before retracting again. This avoids retracting a lot on the same piece of filament. | >0 | 20 |
| zHop | <code>int</code>| When a retraction is done, the head is lifted by this amount (in microns) to travel over the print | >=0 | 0 |
| minimalDistance | <code>int</code>| Minimum amount of travel needed for a retraction to happen at all in microns  | >0 | 2500 |
