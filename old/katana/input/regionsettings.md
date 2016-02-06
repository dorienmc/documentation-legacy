---
## Region Settings

Unique to Katana are the `regionSettings`. These allow you to change some parameters at a certain point of the printing. This can be helpful when you want less strength towards the top of your model to save material and printing time. Below you can find the complete list of settings that can be changed per region. Using the `model.settings` parameters, you can assign a set of regions to a specific model.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
|id| `unsigned int`|ID of the regionsettings 'set' the region belongs to. | >0 | 1 |
| startHeight | `float` | Startheight of the region | >=0 | 0 |
| _endHeight_ | `float` | Endheight of the region | >= start height or 0 | 0 |
| _layerHeight_ | `float` | Height of the layers in microns, default layer height if set to 0 or not specified (see layers) |  >=0 | 200 |
| _outerWallSpeed_ | `int` | Speed for the outer wall, default outerwall speed if not specified (see movement) | >0 | 40 |
| _innerWallSpeed_ | `int` | Speed for the inner wall, default innerwall speed if not specified (see movement) |  >0 | 50 |
| _printSpeed_ | `int` | Speed for normal printing, default print speed if not specified (see movement) |  >0 | 60 |
| _infillSpeed_ | `int` | Speed for the infill, default infill speed if not specified (see movement) | >0 | 60 |
| _infillAmount_ | `int` | Percentage of infill, default amount if not specified (see infill) | [0,100] | 10 |
| _infillPattern_ | `string` | Pattern type for infilling, default pattern if not specified (see infill) | see infill.pattern | "INFILL_AUTOMATIC" |
| _extruder_ | `int` | ID of the extruder, default of the corresponding model if not specified | >=0 | 0 |
| _fanSpeed_ | `int` | Speed of the fan, determined on the print height if not specified | >=0 | 35 |
| _coolingTime_ | `int` | Cooling time before going on with the next layer, default coolingtime if not specified (see layers) | >=0 | 0 |

> Note: If a non-mandotory parameter is not specified by the user its default value is
used (these are given in among other the layers and movement settings).


> Note: There can be different regions with the same ID. For example: ID 1 Region
(starting at 3000 microns), ID 1 Region (starting at 6000 microns). This means, if a model
has Settings 1, new settings will be applied after printing 3000 microns, and then, new
settings will be applied again after printing 6000 microns. A set of regions can be
applied to multiple models (called Volumes in Katana).


> Note: When no endheight is specified the region will end as soon as a new region
(either specified by the user, or the top region) starts. When an end height is specified
but the next specified region does not start yet default values are used for the layers
in between.


> Note: A region always has an integer number of layers. I.e. if a region starts at 1000
microns and ends at 2001 microns and has layers of height 100 microns, then this region
has 10 layers and the next region (possible a default region) starts at height 2000 microns.
