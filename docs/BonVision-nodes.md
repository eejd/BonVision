# BonVision nodes

There are _5_ types of BonVision nodes: 
1. [**Primitives**](../docs//BonVision-nodes#1-primitives): These are the nodes that define fundamental visual stimulus characteristics.
2. [**RigInfo** (to be renamed **Environment**)](../docs//BonVision-nodes#2-environment): These define the aspects of the visual display devices.
3. [**Collections**](../docs//BonVision-nodes#3-collections): These are nodes that define visual stimuli that comprise a collection of **Primitives**.
4. [**Logging**](../docs//BonVision-nodes#4-logging): These are nodes to help keep log of stimulus parameters for analysis
5. [_Generic_](../docs//BonVision-nodes#5-generic): These are generic helper nodes
***

## 1. Primitives
* **CreateGratings:** _Creates and draws fixed parameter 2D sinewave gratings_
* **DrawCheckerboard:** _Draws a parameterized checkerboard stimulus._
* **DrawCircle:** _Draws a single colored circle._
* **DrawGratings:** _Draws parameterized 2D sinewave gratings._
* **DrawImage:** _Draws an affine transformed 2D image_
* **DrawModel:** _Draws a transformed 3D model stimulus._
* **DrawQuad:** _Draws a single axis-aligned colored quad._
* **DrawText:** _Draws affine transformed multi-line text using the specified style._

## 2. Environment (RigInfo)
* **CreateViewingWindow:** _Creates view and projection matrices for an off-center perspective camera covering the specified part of the visual field._
* **FieldOfView:** _Represents a workflow property specifying a camera field of view, in degrees._
* **GammaCorrection:** _Renders the current scene to a texture and applies gamma correction as a post-processing effect._
* **MeshMapping:** _Renders the current scene to a texture and applies mesh mapping and brightness correction as a post-processing effect._
* **NormalizedViewport:** _Specifies a normalized aspect-ratio preserving viewport._
* **PerspectiveViewport:** _Specifies a perspective camera viewport with the given field of view._
* **SphericalMap:** _Creates a non-linear map for describing a spherical scene and specifies its edge limits, in degrees._
* **ViewingWindow:** _Renders the sphere map with an off-center perspective camera covering the specified part of the visual field._
* **ViewportDegrees:** _Specifies the viewport limits, in degrees._

## 3. Collections
* **CreateSparseNoiseGrid:** _Generates a non-overlapping distribution of values in a grid._
* **CreateSphereGrid:** _Creates a UV-mapped spherical vertex grid, with the specified degree boundaries._
* **CreateVertexGrid:** _Converts a sequence of vertices in the format (x,y,u,v,b) into a quad vertex grid._
* **DrawCircleArray:** _Draws multiple colored circles using the input array as position data._
* **GratingSpecification (Or in generic):** _Creates a sequence of grating parameters used for stimulus presentation._
* **SparseNoise:** _Generates and draws a non-overlapping discrete sparse grid of randomly activated quads._

## 4. Logging
* **EventLogger:** _Creates and initializes a CSV file, and matching behavior subject, on which to log events._
* **LogEvent:** _Logs a value into the specified common event stream._
* **TimeStampedEventLogger:** _Creates and initializes a CSV file, and matching behavior subject, on which to timestamp and log events._

## 5. Generic
* **Angle:** _Represents a workflow property specifying a single-precision angle, in degrees._
* **EnsureGratingParameters:** _Specifies default values for optional parameters in the gratings specification._
* **ParameterRange:** _Generates a linear range of values between min and max._
* **PrimitiveResource:** _Loads mesh and shader resources for rendering primitive stimuli._
* **RangeAnimation:** _Animates a linear range of values between min and max at the specified cycles per second._
* **SampleMany:** _Draws multiple random samples from the input distribution._
