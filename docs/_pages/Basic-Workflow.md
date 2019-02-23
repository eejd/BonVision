---
title: "Basic workflow in BonVision"
redirect_from: /pages
excerpt: ""
last_modified_at: 
author_profile: false
---
There are four basic section to making a workflow in BonVision:
![]({{ '/assets/Images/BasicWorkflow/Structure.PNG' | relative_url }})

`*` *Map Stimuli* and *Define Display* are optional. They can be skipped when prototyping

### BonVision window 
This loads up the basic resources (textures, etc) that would be used by BonVision. Th basic structure is:

![]({{ '/assets/Images/BasicWorkflow/BonVisionWindow.PNG' | relative_url }})

This includes: CreateWindow &rarr; [PrimitiveResources](/docs/PrimitiveResources) &rarr; LoadResources
and [RenderFrame](/docs/Shaders)

###Drawing Region
