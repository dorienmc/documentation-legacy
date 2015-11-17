---
## Infill
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| amount | <code>int</code>| Percentage of infill (100 is solid) | [0,100] | 10 |
| overlap | <code>int</code>| | Amount of overlap with the walls in percentage | [0,100] | 90 |
| pattern | <code>string</code>| Pattern type for infilling | see below | "INFILL\_AUTOMATIC" |


> Infill patterns: {"INFILL\_AUTOMATIC", "INFILL\_GRID", "INFILL\_LINES", "INFILL\_CONCENTRIC","INFILL\_CUSTOM"}
