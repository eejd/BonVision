## This will take you through the steps to draw two grating stimuli on the screen for a fixed period of time.

### Step 0
Start Bonsai and start a new project
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step0.PNG)
***
### Step 1: Initialize
All Bonvision stimuli start with a **RenderFrame** node.
This node passed the render command from the graphics card. 
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step1_renderFrame.PNG)
***
At this point we need to add a coordinate frame. For simplicity lets use **NormaliszedViewport**
This defined coordinates of the window as -1 to 1 along x and -1 to 1 along y

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step2_normalizedViewport.PNG)
***
### Step 2: Add stimulus
Now we are ready to draw stimuli. We can add the node **DrawGrating**
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step3_1_drawGratings.PNG)

***
### Step 3: Test the grating
You can have a look at the stimulus by hitting **Start** in the options. _Note: on some occasions you might not see the window, in case the window location is outside the screen. In this case, double click 'RenderFrame' and adjust the location parameter (see troubleshooting below)
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step3_2_drawBasicStart.PNG)
***
Hitting start should open up a window showing the grating. You can play around with the parameters of the grating, _Live_ by changing them on the right side of the screen
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step3_3_parameterSettings.PNG)

_You can exit by hitting the Stop button_
***
### Step 5: End the Stimulus at 5s
The next step is to limit the drawing to a limited time. For this we can use the **TakeUntil** node from Bonsai. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step4_TakeUntil.PNG)

You will notice this shows up as Red, this is because this needs some kind of argument that tell it when to stop transmitting the inputs. Since we want to end the stimulus in 5s, we can use a **Timer** node from Bonsai. 

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step5_Timer.PNG)

We then connect the Timer to TakeUntil 
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step5_ConnectTimer.PNG)

And set the time on the timer on the right hand side, under _Due Time_

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step6_SetTimer.PNG)
The stimulus when run, will run for just 5s. 

***
### Step 6: Add Workflow Output
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step7_AddWorkflow.PNG)

***
### Step 7: Add _Behavior Subject_ to enable multiple stimuli generation
The easiest way to create multiple stimulus is to split the output of **NormalizedViewport** to multiple listeners, which will then draw the stimuli. We do so by _"Broadcasting"_ using **BehaviorSubject** and adding _"Followers"_ using **SubscribeSubject**
First add BehaviorSubject:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step8_1_BehaviorSubject.PNG)

Make sure to name it. As a Convention we always use _**DrawStimulus**_ as the name here.

We can then subscribe to this by adding **SubscribeSubject** and choosing DrawStimulus from the dropdown list on the right

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step8_1_SubscribeSubject.PNG)

DrawGratings can now be removed from the top row and placed next to the new node:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step8_2_full.PNG)

***
### Step 7: Make multiple stimuli using _Behavior Subject_
Adding a second stimulus is now quite straightforward. Just choose the two nodes at the bottom, copy and paste them. So see them differently make sure to change the parameters of one of the gratings on the right side menu.

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step8_2_full_twoGratings.PNG)

This is the final output image example:

![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/Creating_Basic_Step8_2_full_twoGratings_output.PNG)
***
### Done!

***
***
### Troubleshooting 
In case you do not see a window on the screen after hitting **Start**: double click 'RenderFrame' and adjust the location parameter:
![](https://github.com/amansaleem/BonVision/blob/master/docs/Images/CreateBasic/ShaderWindow.PNG)
