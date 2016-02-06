---
## Slicer
We have a powerful cloud version of Katana running all the time, ready to receive your 3D files and prepare them for printing.

> We change the parameter input set of Katana every now and then to add even more features. It might be that your current sliceprofiles are
> out of date. We try to update them as automated as possible. Check the [Katana changelog](/#/docs/katana/changelog) for exact changes.

---
### `POST` /slice
FORMIDE allows you to slice 3D files with very little input. The post type should be application/json and this is an example input.

```
{
    "modelfiles": ["55c86307508c2c3f31cad6de"],
    "sliceprofile": "55b7e1a8507cf3389de724ff",
    "materials": ["55b7d766d2e8a1f89aed6753"],
    "printer": "55c9c44ed4beab38774ff5f5",
    "settings": {
        "brim": {
            "use": false
        },
        "raft": {
            "use": false
        },
        "support": {
            "use": false
        },
        "skirt": {
            "use": false
        },
        "fan": {
            "use": true,
            "speed": 100
        },
        "override": {
            "layers": {
                "layerHeight": 100
            }
        }
    }
}
```

| **name** | **type** | **details** |
|:---|:---|:---|
| modelfiles | String[] | Array of valid modelfile IDs |
| sliceprofile | String | A valid Sliceprofile ID |
| materials | String[] | Array of valid material IDs |
| printer | String | A valid printer ID |
| settings | Object | Slice settings |
| settings.brim | Object | Brim settings |
| settings.brim.use | Boolean | Use brim or not |
| settings.raft | Object | Raft settings |
| settings.raft.use | Boolean | Use raft or not |
| settings.support | Object | Support settings |
| settings.support.use | Boolean | Use support or not |
| settings.skirt | Object | Skirt settings |
| settings.skirt.use | Boolean | Use skirt or not |
| settings.fan | Object | Fan settings |
| settings.fan.use | Boolean | Use fan or not |
| settings.fan.speed | Boolean | Fan speed (0 to 100) |
| settings.override | Object | Override settings. The structure of this object is the same as a sliceprofile and you can override any sliceprofile parameter by adding it to this object. |

#### Response
Example response for the above request.
```
{
  "printjob": {
    "sliceRequest": {
      "responseID": "5e565534-2259-4d8d-aadf-a407018f8188",
      "bucketOut": "formide-gcode",
      "extruders": [
        {
          "feedrate": 100,
          "filamentDiameter": 1750,
          "firstLayersTemperature": 190,
          "temperature": 190,
          "nozzleSize": 400,
          "material": "PLA",
          "name": "New Extruder"
        }
      ],
      "model": [
        {
          "extruder": 0,
          "z": 0,
          "y": 100,
          "x": 100,
          "bucketIn": "formide-modelfiles",
          "hash": "40b3614c-61c1-46de-a645-61de6c78e267"
        }
      ],
      "bed": {
        "firstLayersTemperature": 0,
        "temperature": 0,
        "zlength": 200000,
        "ylength": 200000,
        "xlength": 210000
      },
      "fan": {
        "speed": 100,
        "fullspeedLayer": 10,
        "min": 35,
        "max": 90
      },
      "infill": {
        "amount": 20,
        "pattern": "grid",
        "overlap": 15
      },
      "multiExtrusion": {
        "preSwitchCode": [],
        "postSwitchCode": [],
        "dualOverlap": 1500
      },
      "movement": {
        "combing": false,
        "oozeShield": false,
        "printSpeed": 40,
        "travelSpeed": 40,
        "innerWallSpeed": 15,
        "outerWallSpeed": 15,
        "infillSpeed": 35,
        "speedupLayers": 10,
        "firstLayersWidthFactor": 120,
        "wipeTowerSize": 0
      },
      "bottom": {
        "thickness": 600,
        "layerHeight": 200,
        "speed": 15,
        "solid": true,
        "layerDelay": 0,
        "cutOff": 0
      },
      "top": {
        "thickness": 600,
        "solid": true,
        "layerHeight": 200
      },
      "retraction": {
        "amount": 3000,
        "speed": 30,
        "extruderSwitch": 14500,
        "minimalExtrusionBeforeRetraction": 20,
        "zhop": 0,
        "minimalDistance": 1500
      },
      "layers": {
        "spiralize": false,
        "simpleMode": false,
        "layerHeight": 100,
        "layerCoolingTime": 0,
        "firstLayersCount": 0,
        "firstLayersAmount": 100,
        "thickness": 200,
        "wallThickness": 800
      },
      "gcode": {
        "startGcode": [
          "G21",
          "G28",
          "G1 Z5 F5000",
          "G90",
          "G92 E0",
          "M82",
          "G92 E0"
        ],
        "endGcode": [
          "G92 E0",
          "M104 S0",
          "G28 X0",
          "M84"
        ],
        "changelayerGcode": [],
        "gcodeFlavour": "GCODE_FLAVOR_REPRAP"
      }
    },
    "createdAt": "2015-09-01T12:53:17.350Z",
    "updatedAt": "2015-09-01T12:53:17.710Z",
    "printer": "55c9c44ed4beab38774ff5f5",
    "sliceprofile": "55b7e1a8507cf3389de724ff",
    "sliceFinished": false,
    "sliceSettings": {
      "override": {
        "layers": {
          "layerHeight": 100
        }
      },
      "fan": {
        "speed": 100,
        "use": true
      },
      "skirt": {
        "use": false
      },
      "support": {
        "use": false
      },
      "raft": {
        "use": false
      },
      "brim": {
        "use": false
      }
    },
    "responseId": "5e565534-2259-4d8d-aadf-a407018f8188",
    "user": "552d4a55db99a3c7449c891f",
    "_id": "55e59fbd733ebe034c65ed64",
    "sliceMethod": "cloud",
    "materials": [
      "55b7d766d2e8a1f89aed6753"
    ],
    "modelfiles": [
      "55c86307508c2c3f31cad6de"
    ]
  },
  "pubsub": [
    "2191911428061"
  ]
}
```