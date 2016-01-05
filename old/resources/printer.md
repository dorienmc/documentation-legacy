### Client

``` js
{
    "id": 1,
    "name": "MyFirstPrinter",
    "type": "fdm",
    "bed": {
        "x": 200,
        "y": 200,
        "z": 200,
        "heated": true
    },
    "axis": {
        "x": 1,
        "y": 1,
        "z": 1
    },
    "extruders": [
        {
            "id": 0,
            "name": "extruder1",
            "nozzleSize": 400
        }
    ],
    "port": null,
    "baudrate": null,
    "gcodeFlavour": "GCODE_FLAVOR_REPRAP",
    "startGcode": [],
    "endGcode": [],
    "createdBy": 1,
    "createdAt": "2015-11-29T17:08:21.052Z",
    "updatedAt": "2015-11-29T17:08:21.052Z",
}
```

### Cloud
The following properties are **added** to printer in the cloud API:

``` js
{
    "device": null,
    "tags": [],
    "materials": [],
    "sliceProfiles": []
}
```
