---
## Changelog
We make changes to Katana's input parameters every now and then to add even more functionality. For platform users, there is no action required. If you use manual sliceparameters however, it is advised to check this log to see if your app is still up to date.

---
### v1.0.2
**Added**
- skin: `upskinCount` and `downskinCount`, both `int`

---
### v1.0.1
**Added**
- infill: new pattern `INFILL_CUSTOM`
- infill: `unsigned int angle` (not mandatory)
- infill: `vector<string> customPattern` (with options ??, ?? and Wave) and string `customPatternSize` with the size of the custom pattern given in `customPattern`

---
### v1.0.0
First stable! This v1 release of Katana is the first stable enough version to call it 1.0.0. From now on, all stable versions of Katana (both patches and minor version increases) will be used in the cloud as well as shipped with the formide client package. We automatically update sliceprofiles to migrate from one version to the next to keep them compatible. If you manage your sliceprofiles manually or use a lot of custom parameters in Katana, we advice you to check sliceprofiles after they have been updated (which is done when they are used the first time after an update or when you create or edit a sliceprofile for the first time after an update). You can find updates on the releases page.

**Added**
- infill: new patterns INFILL_TRIANGLES and INFILL_HONEYCOMB
- skin: `bool skin` toggle to use skin
- New object `absSupport`
- absSupport: `activationAngle`, `radius`, `overlap`, `numberOfLayers` (all `int`)

**Changed**
- moved: `wipeTowerSize` from `movement` to `layers`
- moved: `firstLayersWidthFactor` from `movement` to `bottom`

---
### v0.10.0
**Added**
- infill: new pattern INFILL_CUSTOM
- support: `bool supportModel`, `int orientationAngle`, `int wallDistance`
- bottom: `int numberOfOutlines`
- top: `int numberOfOutlines`
- regionSettings: `float startheight` (mandatory), `float endheight` (not mandatory)
- infill: `unsigned int angle` (not mandatory)

**Removed**
- bottom: `thickness`
- top: `thickness`
- regionSettings: `region` (replaced by startheight)
The `thickness` parameters are now calculated in Katana.

**Changed**
- support: Renamed `fillRate` to `amount` and renamed `angle` to `activationAngle`

---
### v0.9.0
**Added**
- New object: `skin`
- New infill patterns : INFILL_AUTOMATIC, INFILL_GRID, INFILL_LINES, INFILL_CONCENTRIC
- regionSettings: `extruder`, `fanSpeed`, `coolingTime` (all `int`)
- skin: `infillOverlap`, `infillAmount`, `upskinSpeed`, `downskinSpeed` (all `unsigned int`)
- layers: `bool sequentialMode`
- layers: `solidLayers` and `numberOutlines` (all `unsigned int`)
- movement: `bool smart` 
- movement: `minimalSeconds`, `maximalSeconds`,`minfactor`, `maxfactor` (all `unsigned int`)
- fan: `bool smart`
- fan: `minimalSeconds`,`factor`  (all `unsigned int`)
- model: `unsigned int finish`

**Removed**
- layers: `wallThickness`, `thickness` and `firstLayersCount` 
- raft: `interfaceLineSpacing`, `surfaceLineSpacing`, `baseLineSpacing`
These are now all computed by Katana, instead of input
 
**Changed**
- movement: `combing` and `oozeshield`, from `int` to `bool`
- support: `type` is renamed to `pattern`

---
### v0.8.0
**Removed**
- layers: `thickness` and `firstLayersCount` 

**Changed type**
- support: `extruder`, `string` to `unsigned int`
- bottom: `thickness`, `layerHeight` and `cutOff`, `int` to `float`
- bottom: `solid`, `int` to `bool`
- top: `solid`, `int` to `bool`
- layers: `spiralize` and `simpleMode`, `int` to `bool`
- layers: `layerHeight`, `int` to `float`
- region: `layer height`, `int` to `float`