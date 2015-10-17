---
# 3D API
Our API's and javascript SDK allow you to create really cool apps for 3D printing. In the manual below, we'll show you step by step how to create a simple app. After that, you can explore the API documentation and extend your app.

---

### How to write an app

#### Start a new project
There are 2 ways of creating a new project. The first one is via the CLI tool. Run the following command in the folder that your app will be placed in inside of a subfolder:

```
formide init
```

The CLI tool will ask you a few questions to setup your app correctly.

#### Required files
There are several required files that you need to have before you can upload your app to the app store.

* index.html (your main view)
* README.md (description in app store)
* app.json (app configuration)
* icon.png (app store icon)

If you miss any of these file, you will receive an error from the api when trying to upload telling you which file is missing.

---

### Files

#### index.html
This file presents your app to a user. We load in an iframe from a remote storage location. This also means that you can't access javascript that is running on our website, only the scrips that you include are available.

```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <title>My Awesome App</title>
        <link rel="stylesheet" href="style.css">
    </head>
    <body>
        <canvas id="v3"></canvas><!-- This is where the 3D viewer will be placed -->
        <script src="http://downloads.formide.com/sdk/sdk-0.8.18.min.js"></script><!-- Load the SDK -->
        <script src="scripts/app.js"></script><!-- Load your app -->
    </body>
</html>
```

#### app.json
This file tells us who made the app, which version it is and which app ID it belongs to.

```
{
    "id":"123456789",
    "version":"0.0.1",
    "author":{
        "name":"Chris ter Beke",
        "email":"chris@printr.nl"
    }
}
```

#### app.js
This is not a required file, but many apps will have something like this. In this example, we placed it in scripts/app.js as you can see in the index.html file. This example is a very basic application registered to the javascript SDK.

```
formideSDK = new FormideSDK(document.getElementById("v3"), {});

var myApp = function() {
    this.init = function() {
        formideSDK.showPrintBed({ show: true, type: 'xyz' });
        formideSDK.setBackgroundColor({ r: 220, g: 220, b: 220 });
        
        formideSDK.api.downloadBase64({ id: '55b0aa0dce0bd27c23d612d5', hash: 'e7f6184f-de4e-4ab8-95c4-87aa5a83a841' }, function(response, err) {
            formideSDK.addModel({ contents: window.atob(response) }, function(response, err) {
            	formideSDK.setModelColor({ modelId: response.modelId, r: 200, g: 200, b: 100 });
            	formideSDK.allowModelTranslate({ modelId: response.modelId, allow: true });
            	formideSDK.allowModelRotate({ modelId: response.modelId, allow: true });
            	formideSDK.allowModelScale({ modelId: response.modelId, allow: true });
            });
        });
    }
};

// Register a new instance of your app
formideSDK.registerApp(new myApp());
```

#### README.md
This file is used to add a description of your app in the app store. You also get a preview in the app center. When you have your app on GitHub, because of the name, it will also appear there.

```
# example-app
Shows a cube
### Functions
* Showing a cube
```

#### icon.png
The last step is adding an app icon to your app. You can just upload any .png file with the name icon.png in the root of your project. We advice to use square images that have a minimum size of 200x200 pixels.