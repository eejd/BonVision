---
title: "Docs"
redirect_from: /docs/DrawQuad
excerpt: "docs"
last_modified_at: 
author_profile: false
---
## Draws a single axis-aligned colored quad.
A BonVision primitive that draws a 2-dimensional rectangular region. 
***
## Description
DrawQuad as the name suggests displays a quad of specified size, at the defined location. The colour, location and size can all be controlled by the experiment.

### Notes
Best used with _SphereMapping_ transformed coordinate frame

## _Inputs:_ 
* Needs DrawStimulus (the tag for rendering a frame) as an input to be able to run
* LocationX: x coordinate (this is in the units of the viewport?) (Default: 0)
* LocationY: y coordinate (this is in the units of the viewport?) (Default: 0)
* ExtentX: Dimension in the x direction
* ExtentY: Dimension in the y direction* ColorR: Value of Red (0 to 1)
* ColorG: Value of Green (0 to 1)
* ColorB: Value of Blue (0 to 1)
* ColorA: Value of Alpha mask or tranparency (0: Transparent to 1:Opague; Default: 1)


## _Outputs:_
* _This can be an end node_
* All the properties that are externalised can be sent forward as outputs.
