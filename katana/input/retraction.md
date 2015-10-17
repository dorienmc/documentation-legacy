---
## Retraction
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>unsigned int</code>| Amount of retraction (0 when not used) | >0 | 0 |
| speed | <code>unsigned int</code>| Speed at which the filament is retracted | >0 | 0 |
| extruderSwitch | <code>unsigned int</code>| Amount of retraction when switching nozzle with dual-extrusion (0 when not used) | >0 | 0 |
| minimalExtrusionBeforeRetraction | <code>unsigned int</code>| The minimal amount of extrusion that needs to be done before retracting again. This avoids retracting a lot on the same piece of filament. | >0 | 0 |
| zhop | <code>unsigned int</code>| When a retraction is done, the head is lifted by this amount to travel over the print | - | 0|
| minimalDistance | <code>unsigned int</code>| Minimum amount of travel needed for a retraction to happen at all | >0 | 0 |