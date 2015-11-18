---
## Infill
Infill is the material used to fill the empty space
inside the shell/skin (number of times the outline of a
layer is retraced) of an object, it refers to the
density. Infill is measured by percentage, so an object
printed at 100% infill will be 100% solid. More infill
will make an object stronger, heavier, and slower to
build. Likewise, less infill is lighter and quicker to
print.

A 3D printer can extrude infill in several patterns
(currently: automatic, grid, line, and concentric). The
automatic infill creates either lines or a grid,
depending on the amount (density) of the infill. Items
printed for display purposes rarely need more than 10%-20% infill, but functioning mechanical parts and pieces that will take more abuse will need 75%-100% infill.

> Rule-of-thumb: Use less infill on test objects and prototypes that wont be subjected much stress, use more infill on functional mechanical parts and objects that need to be durable.

---
## Infill density
In Katana each region can have its own infill density, which ranges between 0 and 100%.

In the picture below each layer of the pyramid has a triangle infill, but the density/amount is different (note: each layer of the piramid actually corresponds with a region). The top and bottom part have the highest density (approx. 70%), while the second (50%) and third (30%) have less infill.

![infill density](https://developers.formide.com/#/docs/katana/img/Traingle_Piramid.JPG)

---
### Infill patterns
In Katana each region can have its own infill pattern, currently the following patterns are available: lines, grid, concentric, triangles, honeycomb and automatic (chooses either line or grid depending on the size of the layer).

The pictures below show various infill densities for the patterns _Triangle_ and _HoneyComb_ (from left to right, 80%, 60%, 40% and %20).

![triangle infill](https://developers.formide.com/#/docs/katana/img/Triangle_Infill.JPG)
![honeycomb infill](https://developers.formide.com/#/docs/katana/img/HoneyComb_Infill.JPG)
