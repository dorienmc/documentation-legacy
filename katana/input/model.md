---
## Model

THe model settings are really specific to Katana. Here you can define the location of the 3D model file, which extruder to print it with and if it needs to be transformed before printing (move, rotate and scale).

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| hash | `string` | Name of the output file/folder | nonempty | empty |
| bucketIn | `string` | Name of the Google Cloud Storage bucket where the model(s) is/are located or local path to the model(s)  | nonempty | empty |
| extruder | `int` | ID of the default extruder used to print the model, can be overwritten per region |>=0 | 0 |
| _settings_ | `int` |  ID of the set of regions that will be applied to this model. Set to 0 if no regions are used in the model | >=0 | 0 |
| _finish_ | `int` | Height at which the model should stop printing, used for partial printing. A value of zero means the complete model is printed. | >=0 | 0 |
| _scale_ (x,y,z) | `float` | Scale factor in x,y and z directions | >=0 for all | 1 for all |
| _rotation_ (x,y,z) | `float` | Rotation around original model axis (in XYZ order) | [-Pi,Pi] for all | 0 for all|
| _position_ (x,y,z) | `int` | Position of the midpoint (of the boundary box around) the model | - | 0 for all|

> The parameters `scale`, `rotation` and `position` each have three sub-parameters,
for each of the three directions. Katana makes use of the right-handsided axes system
in which the z-axis goes up (commonly used by mathematicians). Scale, rotation and position
 are automatically calculated in the viewer for each model (and clone). When a `position`
of (0,0,0) is given the model is centered on the bed and put on the bed
(the lowest point touches the bed).

> The extruder ID is determined by the order in which extruders are added in the input file, the first extruder has ID 0.
