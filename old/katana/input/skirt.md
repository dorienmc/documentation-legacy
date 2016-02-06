---
## Skirt

The skirt is a set of lines some distance from your model to get the filament flowing and show the outline of the final print.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| lineCount | `int` | Number of lines of skirt | >=0 | 2 |
| distance | `int` | Distance from the skirt to the model in microns | >=0 | 3000 |
| minLength | `int` | Minimal length of the skirt in microns | >=0 | 50000 |
| extruder | `int` | ID of the extruder that will be used to print the support | >=0 | 0 |

> The skirt is either printed per input model (in case of sequential printing or only 1 model) or around all the input models (in case of non-sequential printing with multiple models). The later might still result in multiple skirts if the models lie far from each other, but the lines are all printed at the same time.
