---
## API
The FORMIDE API wrapper for JavaScript is integrated in the 3D SDK to make it really easy to download and upload user files from and to the API. You can override the default API settings when you create a new instance of the SDK in your app:

```
formideSDK = new FormideSDK(document.getElementById("v3"), {
    api: {
        baseUrl: "https://api2.formide.com",
        accessToken: "YOUR_MANUAL_ACCESS_TOKEN"
    }
});
```

---
### Download (base64)
Download a file from the user's account by ID and hash. We use base64 encoding to prevent issues with strange characters in binary files.

```
formideSDK.api.downloadBase64({
    id: 0,
    hash: "RANDOM_FILE_HASH"
}, function(response, err) {
    // do something with the response (the file contents with base64 encoding
    // example: add a model based on contents
    formideSDK.addModel({
        contents: window.atob(response)
    }, function(response, err) {
        // do something with response or error
    });
});
```

---
### Upload (base64 STL)
Upload a created model to the API on behalf of the user. We use base64 encoding to prevent issues with strange characters in binary files.

```
formideSDK.api.uploadBase64({ file: 'solid exported\n facet normal 0 0 -1.....', filename: 'test.stl', filetype: 'stl' }, function(response, err) {
    // do something with API response (info about the uploaded model like ID and hash)
});

// implementation with scene exporting:
formideSDK.exportScene({ type: 'ascii' }, function(response, err) {
    formideSDK.api.uploadBase64({ file: response.stl, filename: 'test.stl', filetype: 'stl' }, function(response, err) {
        // do something after upload
    });
});
```

---
### Upload (geometry)
Next to uploading a generated STL file, FORMIDE can also handle STL generation in the back-end. The only thing you have to do in your app is use the export geometry function. The result is a big speed increase because our cloud servers can generate STL much faster than a front-end can. Also, we generate binary STLs instead of ASCII, cutting the storage size of the model back to 1/8th of an ASCII file.

```
// implementation with scene exporting:
formideSDK.exportScene({ type: 'geometry' }, function(response, err) {
    formideSDK.api.uploadGeometry({ file: response.geometry, filename: 'test.stl', filetype: 'stl' }, function(response, err) {
        // do something after upload
    });
});
```

---
### Set access token
Set the access token for API uploading and downloading manually. Normally, the access token is automatically set for the current user.

```
formideSDK.api.setAccessToken("myNewAccessToken");
```

---
### Set base url
Set the base URL of the API. Normally, this is automatically set to the real API URL.

```
formideSDK.api.setBaseUrl("http://api2.formide.com");
```