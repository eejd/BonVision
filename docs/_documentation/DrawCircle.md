## Draws a single colored circle.
A BonVision primitive that draws a 2-dimensional circular/oval region. 
***
## Description
DrawCircle displays a circle/oval of specified size, at the defined location. The colour, location and size can all be controlled by the experiment.

### Notes
Best used with _SphereMapping_ transformed coordinate frame

## _Inputs:_
* Needs DrawStimulus (the tag for rendering a frame) as an input to be able to run

* LocationX: x coordinate (this is in the units of the viewport?) (Default: 0)
* LocationY: y coordinate (this is in the units of the viewport?) (Default: 0)
* Diameter: Diameter of the Circle
* ColorR: Value of Red (0 to 1)
* ColorG: Value of Green (0 to 1)
* ColorB: Value of Blue (0 to 1)
* ColorA: Value of Alpha mask or tranparency (0: Transparent to 1:Opague; Default: 1)
* MinorAxis???: Can we have an oval?

## _Outputs:_
* This can be an end node
* All the properties that are externalised can be sent forward as outputs.