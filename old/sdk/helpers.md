---
## Helpers
To make life in the 3D world a bit easier for both developers and end users, we've added some helper functions to our 3D SDK.

---
### Set bed height
Set the height (thickness) of the virtual printbed.

``` js
// set height without animation
formideSDK.setBedHeight({
    height: 2
}, function(response, err) {
    // do something
});

// set height with animation
formideSDK.setBedHeight({
    height: 2,
    animationTime: 2000
}, function(response, err) {
    // do something
});
```

---
### Set canvas size
Set the size of the 3D environment in your HTML structure. Automatically scales camera viewport.

``` js
formideSDK.setCanvasSize({
    width: 500,
    height: 300
}, function(response, err) {
    // do something after resizing canvas
});
```

---
### Set grid size
Set the size of the grid shown on the virtual printbed. The size is in mm per square.

``` js
formideSDK.setGridSize({ size: 20 }, function(response) {
    // do something in callback
});
```

---
### Set printer size
Set the size of the virtual print bed and build volume.

``` js
// without animation
formideSDK.setPrintSize({
    x: 300,
    y: 300,
    z: 300
}, function(response, err) {
    // do something
});

// with animation
formideSDK.setPrintSize({
    x: 300,
    y: 300,
    z: 300,
    animationTime: 3000
}, function(response, err) {
    // do something
});
```

---
### Transform rotate mode
Set the transform mode to rotation (rotate a model with on screen arrows).

``` js
formideSDK.setTransformRotate(function(response, err) {
    // do something
});
```

---
### Transform scale mode
Set the transform mode to sacle (scale a model with on screen arrows).

``` js
formideSDK.setTransformScale(function(response, err) {
    // do something
});
```

---
### Transform translate mode
Set the transform mode to translation (move a model with on screen arrows).

``` js
formideSDK.setTransformTranslate(function(response, err) {
    // do something
});
```

---
### Virtual printbed
Show a vritual printbed to help the user visualize a model in their 3D printer. Listens to setPrinterSize.

``` js
formideSDK.showPrintBed({ show: true, type: 'xyz' }, function(response, err) {
    // do something with response (OK)
});
```

<table class="table table--cells table--compact small ng-scope">
	<thead>
		<tr>
			<th>Parameter</th>
			<th>Type</th>
			<th>Required</th>
			<th>Default</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<!-- ngRepeat: parameter in desc.parameters --><tr ng-repeat="parameter in desc.parameters" class="ng-scope">
			<td class="ng-binding">type</td>
			<td class="ng-binding">string</td>
			<td class="ng-binding">false</td>
			<td class="ng-binding">xyz</td>
			<td class="ng-binding">The type of bed you want to show. Can be 'xyz' or 'delta'</td>
		</tr><!-- end ngRepeat: parameter in desc.parameters --><tr ng-repeat="parameter in desc.parameters" class="ng-scope">
			<td class="ng-binding">show</td>
			<td class="ng-binding">boolean</td>
			<td class="ng-binding">true</td>
			<td class="ng-binding"></td>
			<td class="ng-binding">Show or hide the virtual printbed.</td>
		</tr><!-- end ngRepeat: parameter in desc.parameters -->
	</tbody>
</table>

---
### Virtual build volume
Show a virtual bounding box to indicate the build volume of a 3D printer. Listens to setPrinterSize.

``` js
formideSDK.showPrintSize({
    show: true,
    type: 'xyz'
}, function(response, err) {
    // do something
});
```

<table class="table table--cells table--compact small ng-scope">
	<thead>
		<tr>
			<th>Parameter</th>
			<th>Type</th>
			<th>Required</th>
			<th>Default</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<!-- ngRepeat: parameter in desc.parameters --><tr ng-repeat="parameter in desc.parameters" class="ng-scope">
			<td class="ng-binding">type</td>
			<td class="ng-binding">string</td>
			<td class="ng-binding">false</td>
			<td class="ng-binding">xyz</td>
			<td class="ng-binding">The type of build volume you want to show. Can be 'xyz' or 'delta'</td>
		</tr><!-- end ngRepeat: parameter in desc.parameters --><tr ng-repeat="parameter in desc.parameters" class="ng-scope">
			<td class="ng-binding">show</td>
			<td class="ng-binding">boolean</td>
			<td class="ng-binding">true</td>
			<td class="ng-binding"></td>
			<td class="ng-binding">Show or hide the virtual build volume.</td>
		</tr><!-- end ngRepeat: parameter in desc.parameters -->
	</tbody>
</table>

---
### Show wireframe
Show a wireframe around all models that are currently in the 3D environment.

``` js
// show wireframe
formideSDK.showWireframe({
    show: true
}, function(response, err) {
    // do something
});

// hide wireframe
formideSDK.showWireframe({
    show: false
}, function(response, err) {
    // do something
});
```

---
### Snap to grid
Snap a model to a virtual grid when moving, rotating and scaling. This allows for easier translations for beginning users.

``` js
// snap to relatively small grid
formideSDK.snapToGrid({
    snap: true,
    positionSnap: 5,
    rotationSnap: Math.PI / 8, 
    scaleSnap: 5
}, function(response) {
    // do something in callback
});

// don't snap to grid
formideSDK.snapToGrid({
    snap: false
}, function(response) {
    // do something in callback
});
```
