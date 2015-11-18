---
## Logs
Slice Logs contain information on the slicing process (divided in so called steps), the output mode (svg or gcode), the total slice time and an estimation of the total print time and total material needed.

This output is created after slicing and creating output files, hence if Katana crashes before it then no output is created. When Katana aborts a slice request itself however (eg. when it detects that the model does not fit on the printbed) the slice log is created.

---
### Structure
```
{
  "status": katana error response, 200 in case of succes,
  "data": {
    "mode": either gcode or svg,
    "hash": model hash,
    "responseId": id of the request,
    "version": version of the slice request that is used,
    "amount": estimated amount of material that is needed,
    "time": estimated print time.
    "totalTime": time needed by Katana for slicing
    "steps": [ list of steps ]
}
```

---
### Step
```
{
  "stepName": Name of the step,
  "stepTime": Time needed to complete the step
    (either successfully or not) in ms,
  "message": Messages given by Katana, eg start time
    or number of layers,
  "success": True in case of succes, false otherwise,
  "code": Error code, 0 in case of success,
}
```

> More information on the katana status and the step (error)codes can be found in the [error response](https://developers.formide.com/#/docs/katana/output/errorResponse/) section.

---
### Example 1: Crashed request
In this case Katana never reaches the code that writes the output, hence no output is returned.

---
### Example 2: Aborted request
This is the slice output corresponding to the other example 2, in this output it also shows why Katana aborted the slicing process and even the bounding boxes of the print bed and the input volume. It shows that Katana aborted after 34 ms and that the "Transforming input volumes" step was aborted after less than 1ms because the model/volume did not fit on the print bed.
It also shows that the requestHandler returns error code 602 (Model too large for printbed) and Katana returns -4 (which is the corresponding internal error code).

```
{
  "status":602,
  "data":{
    "msg":"Model too large for printbed",
    "responseId":"gfbgjrywe",
    "version":"1.0.5",
    "totalTime":34,
    "steps":[{
      "stepName":"Parse slice request",
      "stepTime":1,
      "message":"Started at 16:51:10,
        Finished parsing",
      "success":true,
      "code":0
    },{
      "stepName":"Loading volumes",
      "stepTime":31,
      "message":"Started at 16:51:10, Loaded 1 volumes.",
      "success":true,"code":0
    },{
      "stepName":"Transforming input volumes",
      "stepTime":0,
      "message":"Started at 16:51:10, Volume 0 does not
        fit on the printbed , Size printbed: (0,0,0) by
        (400,400,170000),
        Size volume 0: (-19799,-19800,0) by
        (20200,20199,40000)",
      "success":false,
      "code":-4
    }]
  }
}
```

---
### Example 3: Successful request
In this case Katana has sliced the model successfully (code 200) which took a total time of 611 ms. It expects that printing will take 8773 seconds and 8773 cm(?) of material.

>Note: estimated time and amount seem to be incorrect

```
{
    "status":200,
    "data":{
        "mode":"gcode",
        "hash":"GqA9WfFY3KXDk6H03XO96U4SWq8UMu4oqan28c2f
          HBpHcTXAJR",
        "responseId":"gfbgjrywe",
        "version":"1.0.5",
        "amount":8773,
        "time":8773,
        "totalTime":611,
        "steps":[{
            "stepName":"Parse slice request",
            "stepTime":1,
            "message":"Started at 16:50:22,
              Finished parsing",
            "success":true,
            "code":0
        },{
            "stepName":"Loading volumes",
            "stepTime":10,
            "message":"Started at 16:50:22,
            Loaded 1 volumes.",
            "success":true,
            "code":0
        },{
            "stepName":"Transforming input volumes",
            "stepTime":34,
            "message":"Started at 16:50:22,
            Available volumes: 1",
            "success":true,
            "code":0
        },{
            "stepName":"Create Regions",
            "stepTime":19,
            "message":"Started at 16:50:22, Volume 0,
              Region bottom: 4 layers,
              Region default_copy_640_to_39200: 192 layers,
              Region top: 4 layers,
              Total layers: 200.",
            "success":true,
            "code":0
        },
...
...
...
        {
            "stepName":"Add layers to gcode",
            "stepTime":213,
            "message":"Started at 16:50:23,
              Added skirt around volume 0,
              Added brim around volume 0,
              Added all layers to gcode, ",
            "success":true,
            "code":0
        },{
            "stepName":"Finish gcode",
            "stepTime":42,
            "message":"Started at 16:50:23, ",
            "success":true,
            "code":0
        }]
    }
}
```
