---
Our javascript SDK allows you to work with 3D printing and 3D modeling right in your browser. Create rich content apps with just a few lines of code (or soon, with no code at all!). Just register your app to the SDK, load up some 3D models and start playing with them!

---
### SDK instance
To use the 3D SDK, just include http://downloads.formide.com/sdk/sdk-0.8.18.min.js as source script in your application.

The first thing you have to do is create a new instance of the SDK. You can do this using the following piece of code:

```
formideSDK = new FormideSDK(document.getElementById("v3"), {});
```

This creates a new instance of the 3D SDK in a DOM element with id 'v3'. The type of this DOM element should be an HTML5 canvas:

```
<!DOCTYPE html>
<html lang="en" xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title></title>
        <style>
            #v3
            {
                width: 100%;
                height: 100%;
            }
        </style>
    </head>
    <body>
        <canvas id="v3"></canvas>
        
        <script src="http://downloads.formide.com/sdk/sdk-0.8.60.min.js"></script>
        <script src="app.js"></script>
    </body>
</html>
```

Check the documentation on how to create apps for more details on what an app should look like.

---
### Updates
Every now and then we push updates to the SDK. We don't have a automatic 'latest' file online because this can break your app when we update that. We advice to load a specific version and keep an eye on [this page](/#/docs/sdk/changelog) to see if we updated to a new version so you can update your app.

The latest version is 0.8.60 and can be found on http://downloads.formide.com/sdk/sdk-0.8.60.min.js.