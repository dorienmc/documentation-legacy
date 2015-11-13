---
## Bottom
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| numberOfLayers | <code>int</code>| Number of layers in the bottom | >0 | 2 |
| layerHeight | <code>float</code>| Height of each bottom layer | >=0 | 250 |
| speed | <code>int</code>| Printing speed in the bottom layers | >0 | 30 |
| solid | <code>bool </code>| Infill is solid when set to true, equal to Infill.amount when false | TRUE |
| layerDelay | <code>int</code>| Delay in seconds (after printing) before printing next layer | >=0 | 0 |
| firstLayersWidthFactor | <code>int</code>| Increase of extrusion width for first layers | >=10 | 120 |

> The default layer height (from Layers) is used when the layer height is set to 0.
