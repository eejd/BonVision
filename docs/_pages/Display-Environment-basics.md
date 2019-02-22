---
title: "Display Environment basics"
redirect_from: /pages
excerpt: "A quick start guide to installing and running the Bonsai editor."
last_modified_at: 
author_profile: false
---
Visual neuroscience is almost always carried out in eye-centric coordinate, which defines stimuli in terms of _Visual angle_ subtended at the eye. This helps keep the definition of the image that reaches the retina consistent. However, visual displays work in pixel coordinates (with specific physical characteristics) and to draw accurate stimuli one has to calculate the conversion between the two coordinate frames. This requires a new transform function to be calculated for any display, and few programs are available to help with this. 

The general solution we have with BonVision is to separate the [_**Stimulus Generation**_](https://github.com/amansaleem/BonVision/wiki/Display-Environment-basics#stimulus-generation) and the [_**Display**_](https://github.com/amansaleem/BonVision/wiki/Display-Environment-basics#display-types) aspects of the process. 
* [_**Stimulus Generation**_](https://github.com/amansaleem/BonVision/wiki/Display-Environment-basics#stimulus-generation): Stimuli are always generated and rendered in eye-centric coordinate frame on virtual surfaces. 
* [_**Display**_](https://github.com/amansaleem/BonVision/wiki/Display-Environment-basics#display-types): And the visual displays (screens/projectors) act as windows into the rendered images. 

# Stimulus Generation
BonVision has the following solutions for _**Stimulus Generation**_:
## A. Sphere Mapping
### _This is best for creating 2D stimuli_
Note: Needs a Display object: preferably a ViewingWindow

In this case, stimuli are always rendered onto the inside of a sphere. This allows easy eye-centric definitions pf stimuli in visual angle units. The displays are then windows that observe these rendered stimuli. We use Spherical coordinates to define all stimulus parameters in this case. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/SphericalCoord.png)

[The details of the implementation of Sphere mapping](https://en.wikibooks.org/wiki/Blender_3D:_Noob_to_Pro/UV_Map_Basics)

## B. Cube Mapping
### _This is best for creating 3D stimuli, for Virtual or Augmented Reality Systems_

Note: Needs a Display object: preferably a PerspectiveViewingWindow

[The details of Cube Mapping are explained here:](https://en.wikipedia.org/wiki/Cube_mapping)

In this case all the stimuli are created in eye-centric physical coordinates (centimeters for example) and rendered onto a unit Cube. The displays (Perspective cameras) are then windows into these rendered images.
<probably easiest with a whiteboard drawing here>

### For Virtual Reality (VR)
VR can be easily defined as a situation where the eye, and the screens (windows) are fixed positions, while the all the objects (or VR environment) moves across the eye.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/VRcartoon.png)

> Example rendering to be added here

### For Augmented Reality (AR)

This is a scenario where, generally, the screens remain in a fixed position and the animal can move around. Since we have an eye-centric coordinate frame, the objects and the screen move around to generate an AR. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/ARcartoon.jpg)

> Example rendering to be added here

## C. Normalized Viewport
### _This is convenient while designing and testing, prior to an actual experiment_
It just scales the screen from -1 to 1 on the two axes

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/NormalizedViewport.png)

# Display Types
BonVision has the following solutions for _**DisplayTypes**_:
## I. ViewingWindow
### _This is best for creating 2D stimuli_
This is a flat screen defined by 6 measurements (for a complete discription). Multiple display objects can be added by just adding additional ViewingWindows.

These are the measures that need to be added for each display object:
1. Distance of left bottom corner (from eye)
2. Distance of left top corner (from eye)
3. Distance of right top corner (from eye)
4. Distance of right bottom corner (from eye)
5. Azimuth (horizontal angle from straight ahead) of the centre of the display
6. Elevation (vertical angle from horizon) of the centre of the display


This is an example of the same stimulus rendered on different displays:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/DisplayWindowLogic-01.png)
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/DisplayWindowLogic-03.png)
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/DisplayLogic/DisplayWindowLogic-05.png)

<Images on A, B and C>

## II. PerspectiveViewingWindow
### _This is best for creating 3D VR/AR stimuli_

## III. MeshMapping
### _When using a projector in conjunction with a mirror or lens_
Lens or mirrors cause distortions in the image, such that pixels across the display surface might not have the same physical dimensions. In this case, one would have to measure the distortions and use these to warp the images to display them correctly. In the case of 3D worlds, they might be best use in conjunction with multiple PerspectiveViewingWindows looking at different parts of the world.

## IV. GammaCorrection
### _When using a projector in conjunction with a mirror or lens_
This is simple intensity mapping of the three colors, to make sure the stimuli are linear. It uses a simple LUT (Look-up-table), for Red, Green and Blue. 

