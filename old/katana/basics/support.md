---
## Support
For any part of the model where there is an overhang or gap between parts, a support material is laid down (as it would be impossible to print into thin air). The support material is removed once the print has finished, revealing the desired print. This removal can be accomplished by washing, dissolving, or breaking the support material off of the object (depending on the material of the support).

Support can be added in three ways, by toggling the following support parameters:
- `supportPlatform`: Add support between the bed and the model (and not inside the model)
- `supportModel`: Add support inside the model (but not between the bed and the model)
- `supportEverywhere`: Add support both between the bed and the model and inside the model (overrides the other parameters when set to true).

![Support](https://raw.githubusercontent.com/PRINTR3D/documentation/master/katana/img/Support.JPG)
