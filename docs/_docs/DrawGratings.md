---
title: "Docs"
redirect_from: /docs/DrawGratings
excerpt: "docs"
last_modified_at: 
author_profile: false
---
## Draws parameterized 2D sinewave gratings.
A BonVision primitive that draws a periodic grating stimulus over a specified region. 

## Description
DrawGratings displays a periodic grating of specified size and shape, at the defined location. The spatial frequency, temporal frequency, contrast, direction can all be controlled by the experiment.

### Notes
Best used with _SphereMapping_ transformed coordinate frame

## _Inputs:_
* Needs DrawStimulus (the tag for rendering a frame) as an input to be able to run
* LocationX: x coordinate (this is in the units of the viewport?) (Default: 0)
* LocationY: y coordinate (this is in the units of the viewport?) (Default: 0)
* Angle: 
* Contrast:
* ExtentX:
* ExtentY:
* Edge:
* Opacity:
* Radius:
* SpatialFrequency:
* SquareWave:
* TemporalFrequency:

## _Outputs:_
* This can be an end node
* All the properties that are externalised can be sent forward as outputs.