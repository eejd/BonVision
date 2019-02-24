---
title: "DrawImage"
redirect_from: /docs/DrawImage
excerpt: "docs"
last_modified_at: 
author_profile: false
---
Draws an affine transformed 2D image

## Description

### Notes
Best used with _SphereMapping_ transformed coordinate frame

## _Inputs:_ 
* Needs DrawStimulus (the tag for rendering a frame) as an input to be able to run
* Angle:
* LocationX: x coordinate (this is in the units of the viewport?) (Default: 0)
* LocationY: y coordinate (this is in the units of the viewport?) (Default: 0)
* ExtentX: Dimension in the x direction
* ExtentY: Dimension in the y direction
* ShiftX: 
* ShiftY: Value of Blue (0 to 1)
* TextureName: 

## _Outputs:_
* _This can be an end node_
* All the properties that are externalised can be sent forward as outputs.
