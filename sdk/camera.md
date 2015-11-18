---
## Camera

---
### Center camera on bed
Center the camera viewpoint to the center of the printbed.

``` js
formideSDK.centerCameraOnBed(function(response, err) {
    // do something
});
```

---
### Center camera on model
Center the camera viewpoint to the center of a given model.

``` js
formideSDK.centerCameraOnModel({ modelId: 0 }, function(response, err) {
    // do something
});
```

---
### Auto rotation speed
Set the speed for camera auto rotation. We advice a speed between 0.5 and 5 for pleasant viewing.

``` js
formideSKD.setCameraAutoRotationSpeed({
    speed: 1000
}, function(response, error) {
    // do something
});
```
---
### Auto rotation timeout
Set the timeout in milliseconds before the camera should start rotating after being inactive.

``` js
formideSKD.setCameraAutoRotationTimeout({
    ms: 1000
}, function(response, err) {
    // do something
});
```
