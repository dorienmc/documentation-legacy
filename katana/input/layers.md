---
## Layers
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| spiralize | <code>bool</code>| Toggle for spiralize: continuous change of height instead of per layer | - | FALSE |
| simpleMode | <code>bool</code>| Toggle for simple mode (a.o. no infill and only 1 outline) | - | FALSE|
| sequentialMode | <code>bool</code>| Toggle for sequential printing of volumes | - | FALSE |
| layerHeight | <code>float</code>| Default height of the layer in microns | >=0.5 | 200 |
| layerCoolingTime | <code>int</code>| Seconds of delay per layer | >=0 | 0 |
| firstLayersAmount | <code>int</code>| Percentage of feedrate in first layers | (0,100] | 100 |
| numberOutlines | `int` | Number of lines/walls in the skin/outline | >0 | 2 |
| solidLayers | `int`| A solid layer (infill=100%) is printed every `solidLayers` layer (0 when not used) | >=0 | 0 |
| wipeTowerSize |  <code>int</code>| Size of the wipe tower for multi extrusion in microns | >=0 | 0 |
