---
## Regions
A region is a set of layers that uses the same settings, in this way the settings for the layers can be changed halfway through the model. A model has different settings for the bottom and top by default (although one can choose to have no top layers).

Regions can for example be applied when printing a statue, the pillar can be printed with high speed and large layer heights (reducing print time but quality as well) while the rest of the print can be printed with a lower speed and smaller layer heights (for better accuracy). It is also smart to give the pillar more infill so the center of gravity becomes lower and the statue does not topple over.

---
## Region parameters
Each region has the following settings, which apply to all the layers in the region. Below is an overview of all the settings a region contains, more settings will be added in the future.

- _**_name**: Name of the region (eg. bottom, top, default, URV0R1*), the name is set by Katana._
- **id**: ID of the regionset' the region belongs to.
- **startHeight**: Height at which the region starts.
- **endHeight**: Height at which the region ends, start of the next region by default.
- **layerHeight**: Height of layers.
- **outerWallSpeed**
- **innerWallSpeed**
- **printSpeed**
- **fanSpeed**
- **infillSpeed**
- **infillAmount**: Percentage of infill amount.
- **infillPatter**: Pattern of infill, pattern of model by default.
- **extruder**: ID of the extruder used in the region.
- **coolingTime**: Time needed to cool before going on with the next layer.

> *Abbreviation for: User Region Volume 0 Region 1

> Only the `id` and `startHeight` parameters are mandatory, other parameters are retrieved from the `model`, `movement` and `layer` parameter groups.

---
## Default Region
When a layer is not part of either the bottom, the top or a user specified region it will belong to the default region. The parameters in the default region are also used when parameters are not specified in a user specified region, i.e. if an user creates a region but does not specify the print speed then the default print speed is used.

The parameters from the default region mostly come from the _movement_ and _layers_ input parameters. An overview is given below. The default region is given the name `default` and is not part of any regionset specified by the user (hence `_regionsetID = 0`) but is added to every volume.

| Parameter (in Katana) | Set (in JSON) | Parameter (in JSON) |
| --- | --- | --- |
| _layerHeight | Layers | layerHeight |
| _printSpeed | Movement | printSpeed |
| _outerWallSpeed | Movement | outerWallSpeed |
| _innerWallSpeed | Movement | innerWallSpeed |
| _infillSpeed | Movement | infillSpeed |
| _infillAmount | Infill | amount |
| _extruderID | Model | extruder |
|_coolingTime | Layers | layerCoolingTime |

> The fan speed is by default calculated using the Fan `fullspeedLayer` parameter and can be overwritten in User Specified Regions, hence it is set to zero for the default region.

> The start and end height of the default region are set to zero, for more information on that see the next paragraphs.

---
## Mandatory Regions
Each volume must at least have a bottom and default region. A top region is advised but not mandatory.

These regions are automatically created in Katana using the parameters in the slice profile (JSON input).
The bottom region must have at least one layer, the default region is applied to all layers to which no region is applied (top,bottom or user specified) and hence might be empty.

The bottom parameters are set as followed:

| Parameter (in Katana) | From | Value |
| --- | --- | --- |
| _name | Katana | "bottom" |
| _startHeight | Katana | 0 |
| _endHeight | Katana | `bottom.thickness`|
| _layerheight | JSON - Bottom | layerHeight |
| _printspeed | JSON - Bottom | speed |
| _outerwallspeed | Default Region | _outerwallspeed |
| _innerwallspeed | Default Region | _innerwallspeed |
| _infillspeed | JSON - Bottom | speed |
| _infillamount | Katana | 100 when `bottom.solid` is true, otherwise the default `_infillamount` |
| _extruderID | Default Region | _extruderID |
| _extrusionWidth | Default Region | _extrusionWidth|
| _fanspeed | Default Region | _fanspeed|
|_coolingTime | JSON - Bottom | layerDelay |

The top parameters are set as followed:

| Parameter (in Katana) | From | Value |
| --- | --- | --- |
| _name | Katana | "top" |
| _startHeight | Katana | `volume.height - top.thickness` |
| _endHeight | Katana | `volume.height`|
| _layerheight | JSON - Top | layerHeight |
| _printspeed | Default Region | _printspeed |
| _outerwallspeed | Default Region | _outerwallspeed |
| _innerwallspeed | Default Region | _innerwallspeed |
| _infillspeed | Default Region | _infillspeed |
| _infillamount | Katana | 100 when `top.solid` is true, otherwise the default `_infillamount` |
| _extruderID | Default Region | _extruderID |
| _extrusionWidth | Default Region | _extrusionWidth|
| _fanspeed | Default Region | _fanspeed|
|_coolingTime | Default Region | _coolingTime |

> Note: The bottom/top thickness is calculated in Katana and given by the layer height of bottom/top layers times the number of layers in the bottom/top.

Both bottom and top are not part of any user specified regionset and hence get `_regionsetID = 0`. The volume height is the height of the volume the top region belongs to. Note that for each volume a top region is created, but all top regions have the same characteristics (except their start and end height).

---
## User specified regions
In the extended/advanced settings of the slice profile users can choose to add their own regions. All layers between the bottom and the top regions can be added to a user specified region (at most 1 region per layer).

All user regions must belong to a region set (which determines to which 3d model(s) the region should be added) and must have a start height (in microns). An end height is not mandatory and if not given it is the start height of the next region (possibly the top).

Note that user regions are not allowed to overlap with each other (in that case one region will end earlier) and should be between the bottom and top region (they are ignored otherwise), for examples see below.

---
# Examples
To give a better insight into how (user) regions work, several examples are given below.

---
## 1. No user specified regions
When no regions are specified by the user each volume has only a bottom, top and (possibly) default region.
Note that bottom and top cannot overlap, if such input is given the top will be started later.

### Example 1

In this example three 3d models are used as input, the first is so small that the bottom and top overlap, the second is exactly big enough to fit the bottom and top and the third is large enough that a default region is used.

The following parameters will be used:

| Region | Layer height | Number of layers |
| --- | --- | --- |
| Bottom | 500 | 2 |
| Top | 250 | 2|
| Default | 100 | - |

| Volume | height |
| --- | --- |
| 0 | 1250 |
| 1| 1500 |
| 2 | 2000|

Note: Volume 0 denotes the first 3d model.

![Example 1](https://github.com/PRINTR3D/documentation/blob/master/katana/img/BRegions_example1.png)

---
## 2. With user specified regions
A user can specify one or multiple regions for one or multiple volumes. It is possible to give multiple volumes the same set of regions but also to give each volume a different set of regions (or none at all).

### Example 2A
In this example region sets are explained. Volume 0 and 1 will share the same regionset (which has ID 1), volume 2 will have its own regionset (with ID 2) and volume 3 will have no regionset (user specified regions) at all.

Below is the code used for the regions, all regions have a layer height of 100 and the bottom and top have 2 layers each. All volumes have a height of 1000, except volume 0 which has a height of 700.

```
"regionSettings":[
    {
      "id": 1,
      "startheight": 200,
    },
    {
      "id": 1,
      "startheight": 400,
    },
    {
      "id": 2,
      "startheight": 200,
    },
  ],
```

![User regions, set 1 in blue, set 2 in red](https://github.com/PRINTR3D/documentation/blob/master/katana/img/BRegions_example2A.png)

Set 1 in blue, set 2 in red. Note that region 2 in volume 0 is smaller than region 2 in volume 1, it ends earlier because the top of volume 0 starts earlier.

### Example 2B
This example shows what happens if a region is given an endheight, it shows volumes with multiple default regions and also what happens if a user specified region has a non-integer number (eg. 4.2) of layers. To show this we create 3 volumes each with 1 user specified region(set), all regions start at 400 and have a layer height of 100. The region in volume 0 has no specified end height, and the regions in volume 1 and 2 end at respectively 600 and 550.

![User region without endheight, with correct endheight and updated endheight](https://github.com/PRINTR3D/documentation/blob/master/katana/img/BRegion_example2B.png)

As all user specified regions start at 400 but the bottom ends at 200 all models are given a default region between the bottom and the user specified region. In volume 0 this user region has no specified end height and therefore stops when the top region begins. In volume 1 an end height of 600 is specified by the user, which results into another default region from 600 - 800. In the last volume the end height was set to 550, but the region was given layer heights of 100 (which results in 1.5 layers), hence the end height was adapted to 500.
Note that if we would have chosen an end height below 500 the user specified region would not be created at all (as it has less than 1 layer).

---
## 3. Ignoring user regions
This example shows cases in which (part of) a user region is ignored. A user region is (partly) ignored if:

* **The region starts before the bottom ends** In this case the region will start as soon as the bottom ends, unless it has been ended by then do to its given end height or the start of another region.
* **The region starts after the top begins** In this case the region is completely ignored.
* **The region ends after the top begins** In this case the region end height is set to the start height of the top region, which shrinks the region and might possible remove it completely (due to rounding down, see next point).
* **The difference between start and endheight is less than the layer height** In this case the region would have 0.something number of layers, which rounded down gives 0 layers and hence no region at all.
* **The region has a non-integer number of layers** (`endheight - start height / layer height` is non integer) In this case the number of layers is rounded down and the region is shrunk (to possibly zero layers). The gap is filled up with default layers.
