---
## Top

Just as with the bottom layers, the top is a default region in Katana for which you can change some parameters.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| numberOfLayers | `int` | Number of layers in the top | >=0 | 3 |
| layerHeight | `float` | Height of top layers (use default when set to 0) | >=0 | 200 |
| solid | `bool` | Infill is solid when set to true, equal to Infill.amount when false | - | TRUE |

> The default layer height (from Layers) is used when `layerHeight` is set to zero.
