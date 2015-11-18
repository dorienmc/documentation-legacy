---
## Error response
This is the list of error codes and responses returned by Katana in the Slice Logs.

> Note: I think all malformed request and missing parameters errors should have code 400 (Bad request)
And all others have the 500 (internal server error) code. We could catch a segmentation fault with the 520 error.

| Error code | Description           |
| :-------------: |-------------|
| 200 | OK: successful request |
| 400 | General error |  
| 499 | Malformed request (General) |  
| 401 | Malformed request (unknown type) |   
| 402 | Malformed request (data field unknown) |  
| 403 | Missing parameter: model |  
| 404 | Missing parameter: regionsettings |  
| 405 | Missing parameter: extruders |  
| 406 | Missing parameter: fan |  
| 407 | Missing parameter: bed |  
| 408 | Missing parameter: raft |  
| 409 | Missing parameter: infill |  
| 410 | Missing parameter: support |  
| 411 | Missing parameter: skirt |  
| 412 | Missing parameter: movement |  
| 413 | Missing parameter: bottom |  
| 414 | Missing parameter: top |  
| 415 | Missing parameter: retraction |  
| 416 | Missing parameter: multi extrusion |  
| 417 | Missing parameter: layers |  
| 418 | Missing parameter: gcode |  
| 419 | Missing parameter: version |  
| 420 | Old slice request. Please use an updated slice request |  
| 421 | Version number error |  
| 500 | Internal error |  
| 501 | Could not create folder for SVGs |  
| 502 | Failed to move the files to bucket-out |  
| 510 | Region bounds interfere with bottom layers |  
| 511 | Region bounds interfere with top layers |  
| 601 | Bucket-in or model not found |  
| 602 | Model too large for printbed |  
| 603 | Extruder not defined |  
| 604 | Bucket-out directory not found |  
| 605 | Wall thickness not compatible with nozzle size |

---
## Internal error codes
| Katana output | Error code | Description |
| :-----------: | :--------: | ------------|
| -2 | 500 | "Internal Error" |
| -3 | 601 | "Bucket-in or model not found" |
| -4 | 602 | "Model too large for printbed" |
| -5 | 603 | "Extruder Not Defined" |
| -6 | 604 | "Bucket Out directory not found" |
| -7 | 501 | "Could not create folder for SVGs" |
| -8 | 605 | "Wall thickness not compatible with nozzle size" |
| -11| 602 | "Skirt, brim or raft does not fit on printbed" |

> Note -9 and -10 were deprecated
