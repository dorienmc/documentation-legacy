---
## Infill

The infill settings define the strength and rigidity of the final model. More infill means a stronger result, but also longer printing times.

| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | `int` | Percentage of infill (100 is solid) | [0,100] | 10 |
| overlap | `int` | | Amount of overlap with the walls in percentage | [0,100] | 90 |
| pattern | `string` | Pattern type for infilling | see below | "INFILL_AUTOMATIC" |


> Available infill patterns are: INFILL_AUTOMATIC, INFILL_GRID, INFILL_LINES, INFILL_CONCENTRIC, INFILL_CUSTOM
