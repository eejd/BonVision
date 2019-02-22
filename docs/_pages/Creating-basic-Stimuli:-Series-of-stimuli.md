## This will create a series of stimuli: gratings centred at different x-locations. We continue this from [Creating basic stimuli: two stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

Do keep testing the stimuli frequently during the various steps to make sure it is working.

***
### Step 0: Start from previous tutorial
Load up the stimulus created previously: [Creating basic stimuli: two stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step0.PNG)
***
### Step 1: Move the Timer to individual stimuli
Rather than have the Timer at the top running for all the stimuli, we can have the Timers attached to individual stimuli, which generates an identical output.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step1.PNG)
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step2_1.PNG)
***
### Step 2: Concat to make a series of Stimuli
We now use a [Concat](https://bonsai-rx.org/docs/operators/concat) node from Bonsai on these two stimuli. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step3_Concat.PNG)

This runs the two stimuli one after another rather than together. If we just repeated the sections to the left of Concat now we can add all the stimuli we want. 
However, this can get quite cumbersome and unmanageable. So, we the next steps will help streamline the process.

***
### Step 3: Externalize property to vary
As we are trying to vary LocationX, it is easiest to expose this parameter outside, rather than having to change it within the properties of each **DrawGratings** node. For that we _'Externalize Property'_: by right clicking on the DrawGratings node and choose _LocationX_. Once _externalized_ you can rename the the property.

(Note that you cannot have two externalized properties with the same name and so renaming is a necessary step in some cases)

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step4_ExternaliseProperty.PNG)

***
### Step 4: Group stimulus workflow
This step is to make things convenient to deal with, choose nodes and groups them together:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_1_Group.PNG)

Rename the Grouped Workflow and do it for both stimuli for ease of interpretation.
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_3_Group.PNG)

If you double click on the Grouped parameter, you can edit the nodes within:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step5_4_Group.PNG)
***
### Step 5: Externalize variable parameter from group
We can also externalize parameters from the groups the same way as we do for single nodes:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats.PNG)

To control the values of the location parameters we can add to a **Float** nodes as inputs to each of them:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats.PNG)
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step6_Externalize_floats2.PNG)
***
### Step 6: Group as _Create Observable_
The following steps are a key strategy we use for creating stimulus series. We send in a series of parameter values into a single stimulus generator section, something grouped as a _CreateObservable_. First, delete the second stimulus (as this will no longer be required). 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable.PNG)

Add a second value by using a **Merge** node for two Floats before the _LocationX1_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_3.PNG)

Now choose the nodes _LocationX1_ & _Stim1_ and group them as _CreateObservable_. (Right click on selected nodes and choose the _CreateObservable_ option under _Group_).

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_4.PNG)

Note how the _Concat_ turns blue again as this is now works as having two streams. It is always good to rename grouped nodes to something that is more descriptive of the function. Here we rename it to _GratingAtLocation_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_5.PNG)

You can even add another Float to add an additional location

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_6_extraParameter.PNG)

***
### Step 7: Bringing out another variable (Stimulus Duration)
Just as an example, lets try and keep the stimulus duration as a variable that we can control from outside. For this, we will have to double-click into _GratingAtLocation_ and into _Stim1_ within. Then _Externalize_ _'DueTime'_ from the Timer.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime.PNG)

We would then have to externalize _DueTime_ again from _Stim1_ within _GratingAtLocation_.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_2.PNG)

Finally, from GratingAtLocation in the main workflow. We can also rename the name to StimDuration

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_3.PNG)

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_7_ChangingDueTime_4.PNG)

***
### Step 8: Going over a range of parameters
We will now go over a range of parameters using the function _PropertyMapping_. These are the steps. First we just leave on float:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_1.PNG)

Then remove the _merge_
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_2.PNG)

and externalise the value of float 
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_3.PNG)

Now we use the **ParameterRange** node, setting the range and number of values on the right
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_3.PNG)

Then connect it as an input to value

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step7_CreateObservable_8_ParameterRange_4.PNG)

***
### Step 9: Randomize presentation
Finally, we add a random shuffling of the order of the parameters by adding **Permutation** and **Random** nodes after the **ParameterRange** node. 

(Note that _Permutation_ and _Random_ nodes need the Numerics package of Bonsai)

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_StimSeries/CreateBasic_StimSeries_Step8_Randomize.PNG)
***
### Done!