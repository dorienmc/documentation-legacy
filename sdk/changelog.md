---
## Changelog
The JavaScript SDK is maintained actively and will change with each version. Use this page to keep track of changed that might affect your app when you switch to a newer version. Version numbers might not be incremental since we don't push very minor changes all the time to the SDK cdn.

---
### v0.8.86 (Nov 8, 2015)
* Cleanup and 3rd party sdk release.

---
### v0.8.84 (Oct 11, 2015)
* Updates for Katana slice engine to handle transformations for models during slicing.
* Fix axis to reflect mathematical axis model.
* Added auto deploy to CDN for 3rd party developer releases.
* Fixes for changed endpoints in Formide API.

---
### v0.8.68 (Sep 25, 2015)
* Moved to event based rendering in favor of fps based rendering. Results in huge performace increases!
* Added loading spinner when loading models.
* Fixes for AngularJS directive.
* Small fixes for scrolling and zooming.

---
### v0.8.60 (Sep 9, 2015)
* Removed automatically calculating faceNormals and vertexNormals when adding a geometry. They caused shading issues with some types of models and were not helpful in any other way to the SDK.
* Added a models root point (0,0,0 point) to the list of items in the getModelTransformations() function.
* Added screenshot uploading function to the API (not documented yet).
* Started with implementing automatic side views.
* Started with implementing switching between perspective and orthographic camera modes.

---
### v0.8.54 (Aug 21, 2015)
* Fixed minor issues in exporting functions.
* Added function to copy existing model.
* Updated export API URL.
* Updated print bed to no use any dependencies anymore (now completely constructed in three.js).
* Added functions to manually switch between transform modes.
* Added auto fit, put on bed and auto center functions for models.
* Fixed model rotation issue when adding a new model.
* Started Gcode parser, still very laggy so has to be improved.
* Updated shadow and lighting settings (now a much cleaner look).

---
### v0.8.18 (Jul 25, 2015)
* Automatically set access token when available as query parameter, used in app store.
* Automatically set correct API root URL.

---
### v0.8.17 (Jul 24, 2015)
* First public three.js SDK release.
