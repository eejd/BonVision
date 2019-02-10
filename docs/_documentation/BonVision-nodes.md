<!--right-side-panel
Example Navigation:

* [Home](index.html)
  * [Installation](index.html#Installation)
  * [Pre-defined section names](index.html#pre-defined-section-names-)
* [Layout](layout.html)
-->

# BonVision nodes

There are _5_ types of BonVision nodes:
 
I. [**Primitives**](../wiki/BonVision-nodes#1-primitives)
These are the nodes that define fundamental visual stimulus characteristics.

II. [**RigInfo** (to be renamed **Environment**)](../wiki/BonVision-nodes#2-environment)
These define the aspects of the visual display devices.

III. [**Collections**](https://github.com/amansaleem/BonVision/wiki/BonVision-nodes#3-collections)
These are nodes that define visual stimuli that comprise a collection of **Primitives**.

IV. [**Logging**](https://github.com/amansaleem/BonVision/wiki/BonVision-nodes#4-logging)
These are nodes to help keep log of stimulus parameters for analysis

V. [_Generic_](https://github.com/amansaleem/BonVision/wiki/BonVision-nodes#5-generic)
These are generic helper nodes
***

## I. Primitives
1. [**CreateGratings:**](../wiki/CreateGratings) _Creates and draws fixed parameter 2D sinewave gratings_
2. [**DrawCheckerboard:**](https://github.com/amansaleem/BonVision/wiki/DrawCheckerboard) _Draws a parameterized checkerboard stimulus._
3. [**DrawCircle:**](../wiki/DrawCircle) _Draws a single colored circle._
4. [**DrawGratings:**](https://github.com/amansaleem/BonVision/wiki/DrawGratings) _Draws parameterized 2D sinewave gratings._
5. [**DrawImage:**](https://github.com/amansaleem/BonVision/wiki/DrawImage) _Draws an affine transformed 2D image_
6. [**DrawModel:**](https://github.com/amansaleem/BonVision/wiki/DrawModel) _Draws a transformed 3D model stimulus._
7. [**DrawQuad:**](https://github.com/amansaleem/BonVision/wiki/DrawQuad) _Draws a single axis-aligned colored quad._
8. [**DrawText:**](https://github.com/amansaleem/BonVision/wiki/DrawText) _Draws affine transformed multi-line text using the specified style._

## II. Environment (RigInfo)
1. **CreateViewingWindow:** _Creates view and projection matrices for an off-center perspective camera covering the specified part of the visual field._
2. **FieldOfView:** _Represents a workflow property specifying a camera field of view, in degrees._
3. **GammaCorrection:** _Renders the current scene to a texture and applies gamma correction as a post-processing effect._
4. **MeshMapping:** _Renders the current scene to a texture and applies mesh mapping and brightness correction as a post-processing effect._
5. **NormalizedViewport:** _Specifies a normalized aspect-ratio preserving viewport._
6. **PerspectiveViewport:** _Specifies a perspective camera viewport with the given field of view._
7. **SphericalMap:** _Creates a non-linear map for describing a spherical scene and specifies its edge limits, in degrees._
8. **ViewingWindow:** _Renders the sphere map with an off-center perspective camera covering the specified part of the visual field._
9. **ViewportDegrees:** _Specifies the viewport limits, in degrees._

## III. Collections
1. **CreateSparseNoiseGrid:** _Generates a non-overlapping distribution of values in a grid._
2. **CreateSphereGrid:** _Creates a UV-mapped spherical vertex grid, with the specified degree boundaries._
3. **CreateVertexGrid:** _Converts a sequence of vertices in the format (x,y,u,v,b) into a quad vertex grid._
4. **DrawCircleArray:** _Draws multiple colored circles using the input array as position data._
5. **GratingSpecification (Or in generic):** _Creates a sequence of grating parameters used for stimulus presentation._
6. **SparseNoise:** _Generates and draws a non-overlapping discrete sparse grid of randomly activated quads._

## IV. Logging
1. **EventLogger:** _Creates and initializes a CSV file, and matching behavior subject, on which to log events._
2. **LogEvent:** _Logs a value into the specified common event stream._
3. **TimeStampedEventLogger:** _Creates and initializes a CSV file, and matching behavior subject, on which to timestamp and log events._

## V. Generic
1. **Angle:** _Represents a workflow property specifying a single-precision angle, in degrees._
2. **EnsureGratingParameters:** _Specifies default values for optional parameters in the gratings specification._
3. **ParameterRange:** _Generates a linear range of values between min and max._
4. **PrimitiveResource:** _Loads mesh and shader resources for rendering primitive stimuli._
5. **RangeAnimation:** _Animates a linear range of values between min and max at the specified cycles per second._
6. **SampleMany:** _Draws multiple random samples from the input distribution._
