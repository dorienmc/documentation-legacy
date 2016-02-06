---
## Brim

The brim is a few lines around the model that are attached to the base of the model. This helps to prevent your printing
model from falling over on the print bed. In Katana, you can also define which extruders should print the brim.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| lines | `int` | Number of brim lines added for support | >=0 | 3 |
| extruder | `int` | ID of the extruder | >=0 | 0 |
