---
## Layers
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| spiralize | <code>bool</code>| Toggle for spiralize | - | FALSE |
| simpleMode | <code>bool</code>| Toggle for simple mode (no infilling) | - | FALSE|
| sequentialMode | <code>bool</code>| Toggle for sequential printing of volumes | - | TRUE |
| layerHeight | <code>float</code>| Height of the layer | >0 | 0 |
| layerCoolingTime | <code>unsigned int</code>| Seconds of delay per layer | - | 0 |
| firstLayersAmount | <code>unsigned int</code>| Percentage of feedrate in first layers | (0,100] | 100 |
| numberOutlines | `unsigned int` | Number of lines/walls in the skin/outline | - | 0 |
| solidLayers | `unsigned int`| A solid layer (infill=100%) is printed every `solidLayers` layer (0 when not used) | - | 0 |