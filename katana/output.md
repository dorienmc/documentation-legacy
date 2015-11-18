---
## Output
Katana returns two kind of output, log files on the slice process and output files for a 3d-printer.
There are currently two possible output formats; SVG and G-code.

---
### SVG
**SVG** (Scalable Vector Graphics) output contains a map of ``.svg` files (one for each layer) which contains an image of that layer. This output is used by for example DLP resin or powder-bed printers. Note that each layer in the SVG output must have the same height/speed etc. as this information is not part of a svg file, i.e. all layers belong to the same region.

---
### G-code
**G-code** (also RS-274) output returns a `.gcode` file which can tell the printer to move the extruder along a path with a certain speed, extrude a given amount of material, retract extruder, switch extruder, set fan speed, set bed temperature, etc. G-code output is used by for example FDM (Fused deposition modelling) printers. For more information see
[Input > gcode](https://developers.formide.com/#/docs/katana/input/gcode/).

---
### Slice Logs
**Slice Logs** can be found on the FORMIDE site (Setting > Logs) for each finished (either succesfully or not) slice request. It contains information on the slicing process (divided in so called steps), the output mode (svg or gcode), the total slice time and an estimation of the total print time and total material needed. For more information see [Output > Logs](https://developers.formide.com/#/docs/katana/output/logs/).

---
### Error Response
Katana uses error codes to denote if a slice request was succesfull or not and why. See section [error response](https://developers.formide.com/#/docs/katana/output/errorResponse/).
