---
title: "Docs - Details of BonVision nodes"
redirect_from: /docs
excerpt: "A quick start guide to installing and running the Bonsai editor."
last_modified_at: 
author_profile: false
toc: true
---

There are _5_ types of BonVision nodes:
 
I. [Primitives](/BonVision/docs/docs#1-primitives)
These are the nodes that define fundamental visual stimulus characteristics.

II. [Environment](/BonVision/docs/docs#2-environment)
These define the aspects of the visual display devices.

III. [Collections](/BonVision/docs/docs#3-collections)
These are nodes that define visual stimuli that comprise a collection of Primitives.

IV. [Logging](/BonVision/docs/docs#4-logging)
These are nodes to help keep log of stimulus parameters for analysis

V. [_Generic_](/BonVision/docs/docs#5-generic)
These are generic helper nodes



# I. Primitives
1. [DrawCheckerboard:](/BonVision/docs/DrawCheckerboard/) Draws a parameterized checkerboard stimulus.

2. [DrawCircle:](/BonVision/docs/DrawCircle/) Draws a single colored circle.

3. [DrawGratings:](/BonVision/docs/DrawGratings/) Draws parameterized 2D sinewave gratings.

4. [DrawImage:](/BonVision/docs/DrawImage/) Draws an affine transformed 2D image.

5. [DrawModel:](/BonVision/docs/DrawModel/) Draws a transformed 3D model stimulus.

6. [DrawQuad:](/BonVision/docs/DrawQuad/) Draws a single axis-aligned colored quad.

7. [DrawText:](/BonVision/docs/DrawText/) Draws affine transformed multi-line text using the specified style.

8. [DrawTexturedModel:](/BonVision/docs/DrawTexturedModel/) Draws a textured and transformed 3D model stimulus.

9. [ParameterRange:](/BonVision/docs/ParameterRange/) Generates a linear range of values between min and max.

10. [PrimitiveResource:](/BonVision/docs/PrimitiveResource/) Loads mesh and shader resources for rendering primitive stimuli.

11. [RangeAnimation:](/BonVision/docs/RangeAnimation/) Animates a linear range of values between min and max at the specified cycles per second.



# II. Environment 
1. [DrawViewport:](/BonVision/docs/DrawViewport) Renders all currently stored draw commands to the specified viewport.

2. [GammaCorrection:](/BonVision/docs/GammaCorrection) Renders the current scene to a texture and applies gamma correction as a post-processing effect.

3. [MeshMapping:](/BonVision/docs/MeshMapping) Renders the current scene to a texture and applies mesh mapping and brightness correction as a post-processing effect.

4. [NormalizedViewport:](/BonVision/docs/NormalizedViewport) Specifies an orthographic viewport with normalized screen coordinates for rapid prototyping of 2D environments.

5. [OrthographicViewport:](/BonVision/docs/OrthographicViewport) 
Specifies an orthographic viewport, commonly used for 2D stimulus environments.

6. [PerspectiveViewport:](/BonVision/docs/PerspectiveViewport) Specifies a perspective camera viewport with the given field of view.

7. [SphereMapping:](/BonVision/docs/SphereMapping) Renders the current viewport to a cubemap texture which can be used for environmental mapping of physical screens around the origin.

8. [ViewingWindow:](/BonVision/docs/ViewingWindow) Renders the sphere map from the perspective of a viewing window of the specified size, position and orientation relative to the origin.



# III. Collections
1. [EnsureGratingParameters:](/BonVision/docs/EnsureGratingParameters) Specifies default values for optional parameters in the gratings specification.

2. [GratingSpecification:](/BonVision/docs/GratingSpecification) Creates a sequence of grating parameters used for stimulus presentation.

3. [SparseNoise:](/BonVision/docs/SparseNoise) Generates and draws a non-overlapping discrete sparse grid of randomly activated quads.



# IV. Logging
1. [EventLogger:](/BonVision/docs/EventLogger) Creates and initializes a CSV file, and matching behavior subject, on which to log events.

2. [LogEvent:](/BonVision/docs/LogEvent) Logs a value into the specified common event stream.

3. [TimeStampedEventLogger:](/BonVision/docs/TimeStampedEventLogger) Creates and initializes a CSV file, and matching behavior subject, on which to timestamp and log events.



# V. Generic
1. [Angle:] Represents a workflow property specifying a single-precision angle, in degrees.
cycles per second.

2. [SampleMany:] Draws multiple random samples from the input distribution.
