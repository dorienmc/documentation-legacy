---
## Process

The slicing process can be split up in 5 phases:

1. Parsing input data
2. Load and Optimize input models
3. Slicing
4. Process slice data (when generating Gcode)
5. Generate Output

---
## Parsing input data
Before loading the requested models all request parameters in the slice profile are validated.
If no errors are found the slice request is processed.

---
## Load and Optimize input models
The Load and Optimize phase consists of the steps _Loading Volumes_, _Transforming input volumes_ and _Create Regions_.
This phase also validates in the _volumes_ actually fit on the printer bed.

> In Katana each input model is called a _volume_ and all input volumes together are denoted by _model_.

---
## Slicing
The slicing phase consists of the steps _Create Slices_ and _Create Layer Parts_. It determines the cross sections
(2D layers) of the 3D shape(s). The height of each layer depends on the parameters given in the slice request.

In SVG mode no information on layer height is returned, hence it is assumed that all the layers have the same height.

In gcode mode layer height is determined by regions. In this mode a model has a bottom, top and default region by default.
For more information see the [region](https://developers.formide.com/#/docs/katana/basics/regions) section.

---
## Process slice data
The process slice data part handles all the things that should be done between slicing layers and adding them to the gcode,
if the gcode mode is chosen.

Process:
* **Generate support**: Calculated where support is needed, if required.
* **Generate raft offset**: If a raft is required a volume will not start at height zero but after the raft has been printed.
* **Generate multiple volume overlap**: Generate extra overlap between volumes if dual extrusion is used.
* **Generate infill**: Calculate the distance between infill lines
* **Generate insets**: Generate perimeters/walls for each layer part.
* **Generate oozeshield**: Create a shield between volumes to prevent oozing on a layer (only when adding multiple input models and when required).
* **Generate skins**: Determine where the model needs skin (only up and down, because side skin is a wall).
* **Generate wipe tower(s)**: Create places where the extruders can be wiped/cleaned.
* **Generate skirt, brim and raft**: Create skirt, brim and raft if required.

---
## Generate Output
There are currently two possible outputs; SVG and gcode. SVG files are created per layer and gcode files
per request.

After the output files are created Katana is done and returns the output to FORMIDE. For more information see the [output](https://developers.formide.com/#/docs/katana/output/) section.
