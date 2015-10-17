---
## Infill
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>unsigned int</code>| Percentage of infill (100 is solid) | [0,100] | 0 |
| overlap | <code>int</code>| | Amount of overlap with the walls in percentage | [0,100] | 0 |
| pattern | <code>string</code>| Pattern type for infilling | {"INFILL\_AUTOMATIC", "INFILL\_GRID", "INFILL\_LINES", "INFILL\_CONCENTRIC","INFILL\_CUSTOM"} | "INFILL\_AUTOMATIC" |
| _angle_ | `unsigned int` | Infill pattern angle |[0,360] | 0 |