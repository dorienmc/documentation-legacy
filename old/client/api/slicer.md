---
## Slicer

---
### POST /api/slicer/slice
Start a new slicejobs. Depending on the selected files, this can take a while to respond.

#### Example
```
{
    "modelfiles": [2,3],
    "sliceprofile": 32,
    "materials": [31],
    "printer": 20,
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
        }
    }
}
```

#### Response
```
{
    "success": true,
    "printjob": Object
}
```

---
### GET /api/slicer/generaterequest/:printjobID
Get the full slicer config for a printjob.

---
### GET /api/slicer/reference
Get the currently active reference file that the slicer used to check all input parameters.
