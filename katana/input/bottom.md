---
## Bottom

Bottom is one of the default regions that Katana has.
You can define parameters like a different layerHeight for only the bottom part of your model.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| numberOfLayers | `int` | Number of layers in the bottom | >0 | 2 |
| layerHeight | `float` | Height of each bottom layer | >=0 | 250 |
| speed | `int` | Printing speed in the bottom layers | >0 | 30 |
| solid | `bool` | Infill is solid when set to true, equal to Infill.amount when false | TRUE |
| layerDelay | `int` | Delay in seconds (after printing) before printing next layer | >=0 | 0 |
| firstLayersWidthFactor | `int` | Increase of extrusion width for first layers | >=10 | 120 |

> bottom.layerHeight will use layers.layerHeight when 0 is given as value.
