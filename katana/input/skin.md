---
## Skin
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| skin | `bool` | Toggle the use of skin | - | FALSE |
| _infillOverlap_ | `int` | Overlap with the infill in percentage | (0,100] | 20 or Infill.overlap |
| _infillAmount_ | `int` | Percentage of infill | (0,100] | 90 or Infill.amount |
| _downSkinSpeed_ |`int` |  Infill speed of the lower skin | >0 | 30 & Movement.infillSpeed |
| _upSkinSpeed_ | `int` | Infill speed of the upper skin | >0 | 30 & Movement.infillSpeed |
| _downSkinCount_ | `int` | Number of layers applied to lower skin | >0 | 3 & Bottom.numberOfLayers |
| _upSkinCount_ | `int` | Number of layers applied to upper skin | >0 | 3 & Top.numberOfLayers |

> The parameters `infillOverlap`, `infillAmount`, `downskinSpeed` and `upskinSpeed` are not mandatory and parameters from the Infill and Movement are used when they are not given. The front end interface will use its own default values however.

> The parameters `downskinCount` and `upskinCount` are used to determine when skin is needed. Skin is used to make the top and bottom of a model more sturdy (like walls are used to make the side of a model more sturdy). In this case the top of a model is defined as a part of the model above which there is air for at least a given amount of layers (`upskinCount`) and hence upskin is added. The same holds for a bottom, `downskinCount` and downskin. 
Note that top and bottom 'parts' can occur anywhere in the model and not only in the bottom and top layers.
If no input is given for `downskinCount` and `upskinCount` the number of layers in respectively Bottom and Top objects are used. 

> The input `_skin` is used to denote if skin parameters are given, if not normal infill is used where skin would be used.
