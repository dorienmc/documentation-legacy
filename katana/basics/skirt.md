---
## Skirt
A Skirt is an outline the surrounds your part but does not touch the part.  The skirt is extruded on the print bed before starting to print your model. Skirts serve a useful purpose because they help prime your extruder and establish a smooth flow of filament. Observing your skirt also allows you to detect any printing or leveling errors before you start printing your actual model.

> If you have enabled `supportEveryWhere` or `supportPlatform`, the outline of your skirt may be extended to surround the support.

> For ABS parts, a 'tall skirt' (ooze shield) can be constructed, as high as your model if desired, to thermally insulate the main model from any drafts.

![Skirt](https://github.com/PRINTR3D/documentation/blob/master/katana/img/BSkirt.JPG)

---
## Multiple volumes
In case the model has multiple volumes the skirt can either printed around all of them (it is merged in case they are close enough to each other) in case of non-sequential printing, or each volume has its own skirt which is printed just before the corresponding volume is printed. Below an example of a merged skirt.

![Merged skirt](https://github.com/PRINTR3D/documentation/blob/master/katana/img/BSkirtMerged.JPG)
