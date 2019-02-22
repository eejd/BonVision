## Here we create a stimulus with an adaptor before each presentation.

For this we convert the program written to a series of directions first. And then add the adaptor. This follows on from [Creating Series of Stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-basic-Stimuli:-Series-of-stimuli), which in turn follows from [Create Basic Stimuli](https://github.com/amansaleem/BonVision/wiki/Creating-Basic-Stimuli)

*** 
### Step 1: Convert from x-location series to direction series
First step is to go into the grouped workflows and change the variable parameter from _Location_ to _**Angle**_
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step1_2_convert%20location%20to%20angle.PNG)

This is within the _Stim1_ node of the _GratingAtLocation_. Also, once we change the variable, it would be good to rename the group from _GratingAtLocation_ to _DirectionalGrating_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step1_convert%20location%20to%20angle.PNG)
*** 
### Step 2: Change Range
We previously had the inputs going from -1 to 1 on Parameter Range for location in Normalized Coordinates. We can make these now go from 0 to 180 degrees.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step2_ChangeRange.PNG)
*** 
### Step 3: Add Adaptor to workflow
Within _Stim1_ we add another datastream that is a basic _DrawGratings_ stimulus with some timing. It will have to Subscribe to _DrawStimuli_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor.PNG)

We group the newly made nodes and rename as _AdaptorStimulus_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_2.PNG)

We can externalize _DueTime_ from the Timer, which will be the time the adaptor will remain on for. 


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_3.PNG)

And bring this out further to the main workflow


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_4.PNG)

We can now rename this as 'AdaptorTime'

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step3_AddAdaptor_5.PNG)
***
### Step 4: Concat Adaptor with stimulus
We can now place the adaptor in front of the stimulus within the _DirectionalGrating_ group. First _Remove Connection_ between _Stim1_ and _WorkflowOutput_ 

(Right click on _Stim1_, choose _RemoveConnection_ and then click on _WorkflowOutput_)
 
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_1.PNG)

Add a concat after the _AdaptorStimulus_.


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_2.PNG)

Connect the output of _Stim1_ to _Concat_ and the output of _Concat_ to _WorkflowOutput_.


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step4_ConcatAdaptor_3.PNG)
***
### Step 5: Add a delay, use make random a broadcasted signal

Add a delay after the _DirectionalGrating_ and _Concat_ if you want to add a inter-stimulus interval. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step5_AddDelay.PNG)

In case we use random numbers in multiple places, we like to broadcast a Random number across multiple places. Therefore, we convert it into a _BehaviorSubject_.


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step6_BroadcastRandom.PNG)

In this example, _Permutation_ needs to subscribe to it. 


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step6_SubscribeRandom.PNG)
***
### Step 6: Create Initial adaptor
We are no going to add an adaptation stimulus to before the onset of all the directional stimuli. The easiest way to do this in this workflow, is to first go into the _DirectionalGrating_ node and choose the _Adaptation Stimuli_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_1_createFirstAdaptor.PNG)


We can then copy these nodes, and paste them into the main Workflow. 


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_2_createFirstAdaptor.PNG)

***
### Step 7: Concat Initial adaptor
We now _Concat_ this with the original datastream.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_5_createFirstAdaptor.PNG)

We also add another delay before moving onto the set of DirectionalGratings.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step7_6_createFirstAdaptor.PNG)

***
### Step 8: Fine tuning with grouping
For ease with understanding what is happening, we can group a series of nodes for Convienience. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step8_1_fineTune.PNG)

This was we can just see that we first have the _InitialAdaptor_, followed by _AllStim_ which includes the _DirectionalGratings_.


![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic_DirectioSeries/CreatingBasic_Direction_Step8_2_fineTune.PNG)
***
***
### Done!
