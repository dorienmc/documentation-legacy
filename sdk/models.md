---
## Models

---
### Add box
Add a box shape to the 3D environment. X, y and z are the box sizes in millimeters.

``` js
formideSDK.addBox({ x: 10, y: 10, z: 10 }, function(response, err) {
    // do something with response
});
```

---
### Add cylinder
Add a cylinder shape to the 3D environment. RadiusTop, radusBottom and height are in millimiters and segments defines the smoothness of the cylinder.

```
formideSDK.addCylinder({ radiusTop: 10, radiusBottom: 5, segments: 20, height: 20 }, function(response, err) {
    // do something with response
});
```

---
### Add model
There are 3 ways to add a new model to the 3D environment: by URL, by file contents and by a THREE.Geometry object.

```
// By URL
formideSDK.addModel({
    url: './assets/cube.stl'
}, function(response, err) {
    // do something with response or error
});

// By contents
formideSDK.addModel({
    contents: 'solid exported\n facet normal 0 0 -1.....'
}, function(response, err) {
    // do something with response or error
});

// By geometry
var geometry = new THREE.Geometry(); // do something more exciting here
formideSDK.addModel({
    geometry: geometry
}, function(response, err) {
    // do something with response or error
});
```

---
### Add sphere
Add a sphere shape to the 3D environment. The radius is in millimiters and segments defines the smoothness of the sphere.

```
formideSDK.addSphere({ radius: 10, segments: 20 }, function(response, err) {
    // do something with response
});
```

---
### Allow rotation
Allow a model to be rotated in the 3D environment by the end user.

```
formideSDK.allowModelRotate({
    modelId: 0,
    allow: true
}, function(response, err) {
    // do something with response (OK) or error
});
```

---
### Allow scaling
Allow a model to be scaled in the 3D environment by the end user.

```
formideSDK.allowModelScale({
    modelId: 0,
    allow: true
}, function(response, err) {
    // do something with response (OK) or error
});
```

---
### Allow translation
Allow a model to be moved in the 3D environment by the end user.

```
formideSDK.allowModelTranslate({
    modelId: 0,
    allow: true
}, function(response, err) {
    // do something with response (OK) or error
});
```

---
### Autofit model
Autofit the model on the printbed. Useful to make models printable.

```
formideSDK.autofitModel({ modelId: model.modelId }, function(response, err) {
    // do something
});
```

---
### Copy model
Copy a model (duplicate). Automatically puts the copy in the center of the printbed.

```
formideSDK.copyModel({ modelId: 0 }, function(response, err) {
    // do stuff
});

// example to duplicate a selected model and allow it to be translated by the user
formideSDK.getSelectedModel(function(model, err) {
    formideSDK.copyModel({ modelId: model.modelId }, function(response, err) {
        formideSDK.allowModelTranslate({ modelId: response.modelId, allow: true });
        formideSDK.allowModelRotate({ modelId: response.modelId, allow: true });
        formideSDK.allowModelScale({ modelId: response.modelId, allow: true });
    });
});
``` 

---
### Get transformations
Get the transformations of a model (like position, size, rotation and color)

```
formideSDK.getModelTransformations({
    modelId: response.modelId
}, function(response, err) {
    // response is the transform information that you want
});
```

---
### Get models
With this function, you can get an array of all models that have been added to the 3D environment.

```
formideSDK.getModels(function(response, err) {
    // do something with the models
});
```

---
### Get model
Get information about single model from the SDK.

```
formideSDK.getModel({
    modelId: 0,
}, function(response, err) {
    // do something with the model
});
```

---
### Get selected model
Get the model object of the currently selected model in the 3D environment.

```
formideSDK.getSelectedModel(function(response, err) {
    // do something with selected model object (response)
});
```

---
### Put model on bed
Put a model on the printbed when it's floating in the air. Useful to make models printable.

```
formideSDK.putModelOnBed({ modelId: model.modelId}, function(response, err) {
    // do something
});
```

---
### Recenter model
Move a model to the center of the printbed. For now only works with virtual printbed of type xyz.

```
formideSDK.recenterModel({
    modelId: 0
}, function(response, err) {
    // do sometehing
});
```

---
### Remove all models
Remove all models from the 3D environment.

```
formideSDK.removeModel(function(response, err) {
    // do something after removing all models
});
```

---
### Remove model
Remove a single model from the 3D environment.

```
formideSDK.removeModel({
    modelId: 0
}, function(response, err) {
    // do something after removing the model
});
```

---
### Set color
Set the color of a model to any RGB value.

```
formideSDK.setModelColor({
    modelId: 0,
    r: 200,
    g: 200,
    b: 100
}, function(response, err) {
    // do something with response (OK) or error
});
```

---
### Set position
Set the absolute position of a model. The x, y and z parameters are in millimeters from the 0,0,0 point (corner of the print bed).

```
// move to position
formideSDK.setModelPosition({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10
}, function(response, err) {
    // do something in callback
});

// move to position with an animation. animationTime is in milliseconds
formideSDK.setModelPosition({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10,
    animationTime: 2000
}, function(response, err) {
    // do something in callback
});
```

---
### Set rotation
Set the rotation of a model. The x, y and z parameters are in radiants (so Math.PI is half a circle).

```
// move to position
formideSDK.setModelRotation({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10
}, function(response, err) {
    // do something in callback
});

// move to position with an animation. animationTime is in milliseconds
formideSDK.setModelRotation({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10,
    animationTime: 2000
}, function(response, err) {
    // do something in callback
});
```

---
### Set scale
Set the absolute size of a model. The x, y and z parameters are in millimeters.

```
// move to position
formideSDK.setModelScale({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10
}, function(response, err) {
    // do something in callback
});

// move to position with an animation. animationTime is in milliseconds
formideSDK.setModelScale({
    modelId: 0,
    x: 10,
    y: 0,
    z: 10,
    animationTime: 2000
}, function(response, err) {
    // do something in callback
});
```
