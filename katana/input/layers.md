---
## Layers

Layers are an important part of the slicing and 3D printing process. They can define the overall quality of the final print.

| Name | Type | Description | Range | Default |
| ----- | ----- | ------------ | ------ | -------- |
| spiralize | `bool` | Toggle for spiralize: continuous change of height instead of per layer | - | FALSE |
| simpleMode | `bool` | Toggle for simple mode (a.o. no infill and only 1 outline) | - | FALSE|
| sequentialMode | `bool` | Toggle for sequential printing of volumes | - | FALSE |
| layerHeight | `float` | Default height of the layer in microns | >=0.5 | 200 |
| layerCoolingTime | `int` | Seconds of delay per layer | >=0 | 0 |
| firstLayersAmount | `int` | Percentage of feedrate in first layers | (0,100] | 100 |
| numberOutlines | `int` | Number of lines/walls in the skin/outline | >0 | 2 |
| solidLayers | `int` | A solid layer (infill=100%) is printed every `solidLayers` layer (0 when not used) | >=0 | 0 |
| wipeTowerSize |  `int` | Size of the wipe tower for multi extrusion in microns | >=0 | 0 |
