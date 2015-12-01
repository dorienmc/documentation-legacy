### Client

``` js
{
    "id": 1,
    "name": "Medium Quality",
    "settings": {
        "fan": {
            "fullSpeedLayer": 3,
            "min": 35,
            "max": 90,
            "factor": 40,
            "minimalSeconds": 23,
            "smart": true
        },
        "raft": {
            "fanSpeed": 25,
            "firstLayerAirGap": 250,
            "surfaceLineWidth": 400,
            "surfaceSpeed": 20,
            "surfaceThickness": 0,
            "surfaceLayers": 4,
            "extraMargin": 2000,
            "baseLineWidth": 1000,
            "airGap": 200,
            "interfaceLineWidth": 400,
            "interfaceThickness": 0,
            "baseLineSpacing": 1500,
            "baseSpeed": 90,
            "baseThickness": 0
        },
        "infill": {
            "amount": 20,
            "pattern": "INFILL_HONEYCOMB",
            "overlap": 40,
            "angle": 0
        },
        "support": {
            "amount": 10,
            "activationAngle": 60,
            "orientationAngle": 0,
            "wallDistance": 1000000,
            "supportEverywhere": false,
            "supportPlatform": true,
            "supportModel": false,
            "XYDistance": 1500,
            "ZDistance": 150,
            "pattern": 0
        },
        "skirt": {
            "lineCount": 2,
            "distance": 30000,
            "minLength": 1500000
        },
        "movement": {
            "smart": true,
            "minimalSeconds": 22,
            "minFactor": 30,
            "maximalSeconds": 50,
            "maxFactor": 0,
            "combing": false,
            "oozeShield": false,
            "printSpeed": 50,
            "travelSpeed": 50,
            "innerWallSpeed": 30,
            "outerWallSpeed": 25,
            "infillSpeed": 50,
            "speedupLayers": 10
        },
        "bottom": {
            "numberOfLayers": 4,
            "layerHeight": 160,
            "speed": 7,
            "solid": true,
            "layerDelay": 0,
            "cutOff": 0,
            "firstLayersWidthFactor": 130
        },
        "top": {
            "numberOfLayers": 4,
            "solid": true,
            "layerHeight": 200
        },
        "retraction": {
            "amount": 5000,
            "speed": 30,
            "extruderSwitch": 14500,
            "minimalExtrusionBeforeRetraction": 200,
            "zHop": 300,
            "minimalDistance": 15000
        },
        "layers": {
            "spiralize": false,
            "simpleMode": false,
            "layerHeight": 200,
            "layerCoolingTime": 0,
            "firstLayersAmount": 100,
            "numberOutlines": 3,
            "solidLayers": 0,
            "sequentialMode": false,
            "wipeTowerSize": 3000
        },
        "gcode": {
            "changeLayerGcode": [],
            "customGcode": [],
            "repeatEvery": 0
        },
        "brim": {
            "lines": 5
        },
        "multiExtrusion": {
            "preSwitchCode": [],
            "postSwitchCode": [],
            "dualOverlap": 0
        },
        "skin": {
            "skin": false,
            "infillOverlap": 20,
            "infillAmount": 100,
            "downSkinSpeed": 20,
            "downSkinCount": 3,
            "upSkinCount": 3,
            "upSkinSpeed": 20
        }
    },
    "version": "1.0.6",
    "createdBy": 2,
    "createdAt": "2015-11-29T13:20:28.952Z",
    "updatedAt": "2015-11-29T13:20:28.952Z"
}
```

### Cloud
The following properties are **added** to sliceProfile in the cloud API:

``` js
{
    "tags": []
}
```
