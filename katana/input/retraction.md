---
## Retraction

Retraction is used to pull the material back in the nozzle when moving around or switching extruders to prevent damaging the model with access material.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | `int` | Amount of retraction in microns (0 when not used) | >=0 | 4000 |
| speed | `int` | Speed at which the filament is retracted in mm/s | >0 | 20 |
| extruderSwitch | `int` | Amount of retraction when switching nozzle with dual-extrusion in microns (0 when not used) | >0 | 14500 |
| minimalExtrusionBeforeRetraction | `int` | The minimal amount of extrusion (in microns) that needs to be done before retracting again. This avoids retracting a lot on the same piece of filament. | >0 | 20 |
| zHop | `int` | When a retraction is done, the head is lifted by this amount (in microns) to travel over the print | >=0 | 0 |
| minimalDistance | `int` | Minimum amount of travel needed for a retraction to happen at all in microns  | >0 | 2500 |
