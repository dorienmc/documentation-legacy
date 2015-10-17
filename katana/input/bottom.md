---
## Bottom
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| numberOfLayers | <code>int</code>| Number of layers in the bottom | >0 | 2 |
| layerHeight | <code>float</code>| Height of bottom layers | >0 | 0 |
| speed| <code>unsigned int</code>| Printing speed at bottom layers | >0 | 0 |
| solid | <code>bool </code>| Infill is solid when set to true, equal to Infill.amount when false | FALSE |
| layerDelay | <code>unsigned int</code>| Delay in seconds (after printing) before printing next layer | - | 0 |
| cutOff | <code>float</code>| Object sinking in microns | >=0 | 0 |