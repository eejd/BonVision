---
title: "Sequence of stimuli"
redirect_from: /pages
excerpt: "A quick start guide to installing and running the Bonsai editor."
last_modified_at: 
author_profile: false
toc: true
---

Here we create a stimulus with an adaptor before each presentation.

For this we convert the program written to a series of directions first. And then add the adaptor. This follows on from [Creating Series of Stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-basic-Stimuli:-Series-of-stimuli), which in turn follows from [Create Basic Stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

*** 

### Step 1: Convert from x-location series to direction series
First step is to go into the grouped workflows and change the variable parameter from _Location_ to _**Angle**_
![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step1_2_convert%20location%20to%20angle.PNG' | relative_url }})

This is within the _Stim1_ node of the _GratingAtLocation_. Also, once we change the variable, it would be good to rename the group from _GratingAtLocation_ to _DirectionalGrating_

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step1_convert%20location%20to%20angle.PNG' | relative_url }})

*** 

### Step 2: Change Range
We previously had the inputs going from -1 to 1 on Parameter Range for location in Normalized Coordinates. We can make these now go from 0 to 180 degrees.

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step2_ChangeRange.PNG' | relative_url }})

*** 

### Step 3: Add Adaptor to workflow
Within _Stim1_ we add another datastream that is a basic _DrawGratings_ stimulus with some timing. It will have to Subscribe to _DrawStimuli_

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor.PNG' | relative_url }})

We group the newly made nodes and rename as _AdaptorStimulus_

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_2.PNG' | relative_url }})

We can externalize _DueTime_ from the Timer, which will be the time the adaptor will remain on for. 


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_3.PNG' | relative_url }})

And bring this out further to the main workflow


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_4.PNG' | relative_url }})

We can now rename this as 'AdaptorTime'

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_5.PNG' | relative_url }})

***

### Step 4: Concat Adaptor with stimulus
We can now place the adaptor in front of the stimulus within the _DirectionalGrating_ group. First _Remove Connection_ between _Stim1_ and _WorkflowOutput_ 

(Right click on _Stim1_, choose _RemoveConnection_ and then click on _WorkflowOutput_)
 
![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_1.PNG' | relative_url }})

Add a concat after the _AdaptorStimulus_.


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_2.PNG' | relative_url }})

Connect the output of _Stim1_ to _Concat_ and the output of _Concat_ to _WorkflowOutput_.


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_3.PNG' | relative_url }})

***

### Step 5: Add a delay, use make random a broadcasted signal

Add a delay after the _DirectionalGrating_ and _Concat_ if you want to add a inter-stimulus interval. 

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step5_AddDelay.PNG' | relative_url }})

In case we use random numbers in multiple places, we like to broadcast a Random number across multiple places. Therefore, we convert it into a _BehaviorSubject_.


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step6_BroadcastRandom.PNG' | relative_url }})

In this example, _Permutation_ needs to subscribe to it. 


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step6_SubscribeRandom.PNG' | relative_url }})

***

### Step 6: Create Initial adaptor
We are no going to add an adaptation stimulus to before the onset of all the directional stimuli. The easiest way to do this in this workflow, is to first go into the _DirectionalGrating_ node and choose the _Adaptation Stimuli_

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_1_createFirstAdaptor.PNG' | relative_url }})


We can then copy these nodes, and paste them into the main Workflow. 


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_2_createFirstAdaptor.PNG' | relative_url }})

***

### Step 7: Concat Initial adaptor
We now _Concat_ this with the original datastream.

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_5_createFirstAdaptor.PNG' | relative_url }})

We also add another delay before moving onto the set of DirectionalGratings.

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_6_createFirstAdaptor.PNG' | relative_url }})

***

### Step 8: Fine tuning with grouping
For ease with understanding what is happening, we can group a series of nodes for Convienience. 

![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step8_1_fineTune.PNG' | relative_url }})

This was we can just see that we first have the _InitialAdaptor_, followed by _AllStim_ which includes the _DirectionalGratings_.


![]({{ '/assets/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step8_2_fineTune.PNG' | relative_url }})

***

***

### Done!
