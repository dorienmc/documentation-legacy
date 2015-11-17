---
## Raft
| Name | Type | Description | Range | Default |
| ----- | -----| ------------| ------| --------|
| baseThickness | <code>uint</code>| Layer height of the raft base layer in microns (0 means no raft) | >=0 | 300|
|baseLineWidth| `int` | Extrusion width of the raft base layer in microns | >0 | 1000 | 
|baseSpeed| <code>int</code>| Print speed of the raft base layer in mm/s | >0 | 90 |
|interfaceThickness| `int` | Layer height of the raft interface layer in microns (0 means no raft) | >=0 | 300 |
|interfaceLineWidth| `int` | Extrusion width of the raft interface layer in microns | >0 | 400 |
|airGap| `int` | Each layer is offset by the thickness of the raft plus this airgap (except for the first layer, which has its own airgap parameter), in microns | >=0 | 250 |
|firstLayerAirGap| `int` | Airgap between first layer and the raft in microns | >=0 | 250 |
|extraMargin|`int` | Distance between the outermost part of the raft and the model in microns | >0 | 2000 |
|surfaceLayers| `int` | Number of surface layers" | >0 | 2 |
|surfaceThickness| `int` | Layer height of the raft surface layers in microns | >0 | 300 |
|surfaceLineWidth| `int` | Extrusion width of the raft surface layers in microns | >0 | 400 |
|surfaceSpeed| `int` | Print speed of the raft surface layers in mm/s | >0 | 40 |
|fanSpeed| `int` | Fan speed in the raft layers in mm/s | >0 | 25 |
|extruder| `int` | ID of the extruder used for the raft | >=0 | 0 |

> If either `baseThickness` are `interfaceThickness` is set to zero no raft is used.

> Make `firstLayerAirGap` at least as large as the `airGap` otherwise the second layer will overlap with the first.
