---
title: "DrawModel"
redirect_from: /docs/
excerpt: "docs"
last_modified_at: 
author_profile: false
---
Draws a transformed 3D model stimulus

## Description
OpenGL object 
### Notes
Best used with _CubeMapping_ transformed coordinate frame

## _Inputs:_ 
* Needs DrawStimulus (the tag for rendering a frame) as an input to be able to run
* TranslationX: x coordinate (this is in the units of the viewport?) (Default: 0)
* TranslationY: y coordinate (this is in the units of the viewport?) (Default: 0)
* TranslationZ: z coordinate (this is in the units of the viewport?) (Default: 0)
* RotationX:
* RotationY:
* RotationZ:
* ScaleX: Dimension in the x direction
* ScaleY: Dimension in the y direction
* ScaleZ: Dimension in the z direction
* MeshName: 
* _(Model Material)_ Ambient
* _(Model Material)_ Diffuse
* _(Model Material)_ Specular
* _(Model Material)_ SpecularExponent

## _Outputs:_
* _This can be an end node_
* All the properties that are externalised can be sent forward as outputs.
