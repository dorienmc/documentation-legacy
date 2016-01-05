---
## Upload
Uploading 3D files to FORMIDE is really easy. You can upload all kinds of filetypes to the same URL, and we'll figure out which file type it is and how to deal with it. Right now, we support .stl and .gcode files, but many more are coming!

We support 4 methods of posting files to us: a multipart file upload, a post with the file contents as base64 encoded string in the body, by remote URL or by THREE.js geometry export (you need our 3D SDK for that).

---
### `POST` /files/upload (multipart)
This is the common way of uploading files. However, some JavaScript clients don't allow posting files to another domain due to security restrictions (like Google Chrome). That's why the base64 encoded post body is offered as an alternative.

```
POST /files/upload HTTP/1.1
Host: https://api2.formide.com
Authorization: Bearer {{accessToken}}
Cache-Control: no-cache
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7MA4YWxkTrZu0gW
----WebKitFormBoundary7MA4YWxkTrZu0gW
Content-Disposition: form-data; name="file"; filename="cube40mm.stl"
Content-Type: text/plain
```

---
### `POST` /files/upload (base64)
Alternatively you can do a POST to the samer url (/files/upload) with the following parameters:

```
{
    "file": "BASE64_ENCODED_FILE_CONTENTS",
    "encoding": "base64",
    "filetype": "stl",
    "filename": "MyFile"
}
```

Be sure to set the content type to application/json and don't forget to add the access token in an authorization header.

---
### `POST` /files/upload/url
A 3rd option to upload files to us is to just pass a URL from where we can download the file to the user's library.

```
{
    "url": "http://your-file-url.com",
    "filetype": "stl",
    "filename": "MyFile"
}
```

Be sure to set the content type to application/json and don't forget to add the access token in an authorization header.

---
### `POST` /files/upload/geometry
The last option is posting a json encoded geometry export from THREE.js. This is something we came up with ourselves to ensure fast export speeds on the client side as well as not leaking the .stl file on the client side. When exporting a geometry to the API, we will construct a binary .stl file from it on the server side before adding it to the user's library. The 3D SDK automatically handles geometry export, but if you want to do a geometry export from you own app without using our SDK, please contact us to get information about how to export you geometry data to us.