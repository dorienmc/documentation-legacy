---
## Other

---
### Events
The 3D environment triggers some events when things happen. You can listen to those by using the formideSDK.on function.

```
formideSDK.on('modelSelected', function(event) {
    // do something when a model is selected
});

formideSDK.on('modelUnselected', function(event) {
    // do something when a model is unselected and no other model is selected
});

formideSDK.on('modelChanged', function(event) {
    // do something when a model is changed (translated, settings, changed, etc)
});

formideSDK.on('modelTransformAllowChanged', function(event) {
    // do something when a model changes it's transform allow settings
});

formideSDK.on('geometryChanged', function(event) {
    // do something when a model's geometry was changed (reset root, recenter geometry, etc)
});

formideSDK.on('startTransform', function(event) {
    // do something when a model will be transformed
});

formideSDK.on('endTransform', function(event) {
    // do something when a model has been transformed
});
```

---
### Register app
The safest way to interact with the 3D environment is to register a JavaScript app in your SDK instance. When you do this, we make sure that everything is loaded properly, in the right order and that all APIs are available. Also, you can make use of some functions like init that is fired once the SDK finished loading. Keep in mind that you can still call your SDK instance if you don't use the registerApp function as well.

```
// Create a new SDK instance on a canvas with html id 'v3'
formideSDK = new FormideSDK(document.getElementById("v3"));

// Create a new app function
var myApp = function() {
    
    var self = this;
    
    this.init = function() {
        // Everything in here is executed when the SDK has finished loading
        // We also recommend declaring your event listeners in here
    }
}

// Register an instance of your app in the SDK
formideSDK.registerApp(new myApp());
```

---
### Require
Require an external file using an HTTP get request. Returns the contents of the file. Useful for loading local file assets or config files.

```
// using require in combination with adding a model
formideSDK.require('./assets/cube40mm.stl', function(contents) {
    formideSDK.addModel({ contents: contents }, function(response, err) {
        console.log(response);
    });
});
```