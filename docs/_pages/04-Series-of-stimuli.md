---
title: "Creating a series of stimuli"
redirect_from: /pages
excerpt: "A quick start guide to installing and running the Bonsai editor."
last_modified_at: 
author_profile: false
toc: true
---

This will create a series of stimuli: gratings centred at different x-locations. We continue this from [Creating basic stimuli: two stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

Do keep testing the stimuli frequently during the various steps to make sure it is working.

***

### Step 0: Start from previous tutorial
Load up the stimulus created previously: [Creating basic stimuli: two stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step0.PNG' | relative_url }})

***

### Step 1: Move the Timer to individual stimuli
Rather than have the Timer at the top running for all the stimuli, we can have the Timers attached to individual stimuli, which generates an identical output.

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step1.PNG' | relative_url }})
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step2_1.PNG' | relative_url }})

***

### Step 2: Concat to make a series of Stimuli
We now use a [Concat](https://bonsai-rx.org/docs/operators/concat) node from Bonsai on these two stimuli. 

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step3_Concat.PNG' | relative_url }})

This runs the two stimuli one after another rather than together. If we just repeated the sections to the left of Concat now we can add all the stimuli we want. 
However, this can get quite cumbersome and unmanageable. So, we the next steps will help streamline the process.

***

### Step 3: Externalize property to vary
As we are trying to vary LocationX, it is easiest to expose this parameter outside, rather than having to change it within the properties of each **DrawGratings** node. For that we _'Externalize Property'_: by right clicking on the DrawGratings node and choose _LocationX_. Once _externalized_ you can rename the the property.

(Note that you cannot have two externalized properties with the same name and so renaming is a necessary step in some cases)

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step4_ExternaliseProperty.PNG' | relative_url }})

***

### Step 4: Group stimulus workflow
This step is to make things convenient to deal with, choose nodes and groups them together:

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_1_Group.PNG' | relative_url }})

Rename the Grouped Workflow and do it for both stimuli for ease of interpretation.
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_3_Group.PNG' | relative_url }})

If you double click on the Grouped parameter, you can edit the nodes within:

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_4_Group.PNG' | relative_url }})

***

### Step 5: Externalize variable parameter from group
We can also externalize parameters from the groups the same way as we do for single nodes:

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats.PNG' | relative_url }})

To control the values of the location parameters we can add to a **Float** nodes as inputs to each of them:

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats.PNG' | relative_url }})
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats2.PNG' | relative_url }})
***
### Step 6: Group as _Create Observable_
The following steps are a key strategy we use for creating stimulus series. We send in a series of parameter values into a single stimulus generator section, something grouped as a _CreateObservable_. First, delete the second stimulus (as this will no longer be required). 

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable.PNG' | relative_url }})

Add a second value by using a **Merge** node for two Floats before the _LocationX1_

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_3.PNG' | relative_url }})

Now choose the nodes _LocationX1_ & _Stim1_ and group them as _CreateObservable_. (Right click on selected nodes and choose the _CreateObservable_ option under _Group_).

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_4.PNG' | relative_url }})

Note how the _Concat_ turns blue again as this is now works as having two streams. It is always good to rename grouped nodes to something that is more descriptive of the function. Here we rename it to _GratingAtLocation_

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_5.PNG' | relative_url }})

You can even add another Float to add an additional location

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_6_extraParameter.PNG' | relative_url }})

***

### Step 7: Bringing out another variable (Stimulus Duration)
Just as an example, lets try and keep the stimulus duration as a variable that we can control from outside. For this, we will have to double-click into _GratingAtLocation_ and into _Stim1_ within. Then _Externalize_ _'DueTime'_ from the Timer.

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime.PNG' | relative_url }})

We would then have to externalize _DueTime_ again from _Stim1_ within _GratingAtLocation_.

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_2.PNG' | relative_url }})

Finally, from GratingAtLocation in the main workflow. We can also rename the name to StimDuration

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_3.PNG' | relative_url }})

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_4.PNG' | relative_url }})

***

### Step 8: Going over a range of parameters
We will now go over a range of parameters using the function _PropertyMapping_. These are the steps. First we just leave on float:

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_1.PNG' | relative_url }})

Then remove the _merge_
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_2.PNG' | relative_url }})

and externalise the value of float 
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_3.PNG' | relative_url }})

Now we use the **ParameterRange** node, setting the range and number of values on the right
![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_3.PNG' | relative_url }})

Then connect it as an input to value

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_4.PNG' | relative_url }})

***

### Step 9: Randomize presentation
Finally, we add a random shuffling of the order of the parameters by adding **Permutation** and **Random** nodes after the **ParameterRange** node. 

(Note that _Permutation_ and _Random_ nodes need the Numerics package of Bonsai)

![]({{ '/assets/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step8_Randomize.PNG' | relative_url }})

***

### Done!