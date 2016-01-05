---
## Output
Katana returns two kind of output, log files on the slice process and output files for a 3D printer.
There are currently two possible output formats; SVG and Gcode.

---
### SVG
**SVG** (Scalable Vector Graphics) output contains a map of ``.svg` files (one for each layer) which contains an image of that layer. This output is used by for example DLP resin or powder-bed printers. Note that each layer in the SVG output must have the same height/speed etc. as this information is not part of a SVG file, i.e. all layers belong to the same region.

---
### Gcode
**Gcode** (also RS-274) output returns a `.gcode` file which can tell the printer to move the extruder along a path with a certain speed, extrude a given amount of material, retract extruder, switch extruder, set fan speed, set bed temperature, etc. Gcode output is used by for example FDM (Fused Deposit Modeling) printers. For more information see
[Input > gcode](https://developers.formide.com/#/docs/katana/input/gcode/).

---
### Slice logs
**Slice logs** can be found on the FORMIDE site (Setting > Activity, available in 'nerd mode') for each finished (either successfully or not) slice request. It contains information on the slicing process (divided in so called 'steps'), the output mode (svg or gcode), the total slice time and an estimation of the print time and material needed. For more information see [Output > Logs](https://developers.formide.com/#/docs/katana/output/logs/).

---
### Error Response
Katana uses error codes to tell if a slice request was successful or not and if not why. See section [error response](https://developers.formide.com/#/docs/katana/output/errorResponse/).
