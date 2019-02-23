---
title: "Basic workflow in BonVision"
redirect_from: /pages
excerpt: ""
last_modified_at: 
author_profile: false
---
There are five basic sections to making a workflow in BonVision:
![]({{ '/assets/Images/BasicWorkflow/Structure.png' | relative_url }})

`*` *Map Stimuli* and *Define Display* are optional. They can be skipped when prototyping

***

### BonVision window 
This loads up the basic resources (textures, etc) that would be used by BonVision. Th basic structure is:

![]({{ '/assets/Images/BasicWorkflow/BonVisionWindow.PNG' | relative_url }})

This includes: CreateWindow &rarr; [PrimitiveResources](/docs/PrimitiveResources) &rarr; LoadResources
and [RenderFrame](/docs/Shaders)

***

### Drawing Region
This defines which region of visual space is used for the visual world. Note that this can be larger than the actual region used. Ideally one should use [Orthographic Viewport](/docs/OrthographicViewport). This defines everything in terms of visual angles. 

![]({{ '/assets/Images/BasicWorkflow/DrawReg_ortho.PNG' | relative_url }})

If you are just prototypic stimuli, one can use [Normalised Viewport](/docs/NormalisedViewport). 

![]({{ '/assets/Images/BasicWorkflow/DrawReg_norm.PNG' | relative_url }})

***

### Draw Stimuli
This is where you generate all the aspects of the visual environment. Covered in more detail in later sections.

![]({{ '/assets/Images/BasicWorkflow/DrawStim.PNG' | relative_url }})

(Note: in this case DrawStimulus is not a node but a 'BehaviourSubject' node with a name DrawStimulus)

***

### Map Stimuli (optional)
This is where the stimulus is rendered onto a a surface. This can be skipped for prototyping.
Ideally one should use [SphereMapping](/docs/SphereMapping). If SphereMapping is used, the Define display section next is necessary

***

### Define display (optional)
Here we define the parameters of the display system (eg. monitor). It is defined as:

![]({{ '/assets/Images/BasicWorkflow/Output_sphereSingle.PNG' | relative_url }})

This includes a [ViewingWindow](/docs/ViewingWindow) &rarr; [DrawViewport](/docs/DrawViewport)

Adding additional displays is as simple as adding multiple define displays after the map stimulus like this:

![]({{ '/assets/Images/BasicWorkflow/Output_sphereMultiple.PNG' | relative_url }})




