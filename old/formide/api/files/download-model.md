---
## Download modelfiles
You can download modelfiles from our API when a user made them publicly available or when they authorized your app to access private user data. Files are downloadable in plain text (the original file contents) or with base64 encoding (recommeded when working with JavaScript).

---
### `GET` /files/modelfiles/download?id=FILE_ID&hash=FILE_HASH
Download a modelfile.

---
### `GET` /files/modelfiles/download?id=FILE_ID&hash=FILE_HASH&encoding=base64
Download a modelfile with base64 encoding.