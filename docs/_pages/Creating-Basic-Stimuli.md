---
title: "Creating basics stimuli"
redirect_from: /pages
excerpt: "A quick start guide to installing and running the Bonsai editor."
last_modified_at: 
author_profile: false
---

This will take you through the steps to draw two grating stimuli on the screen for a fixed period of time.

### Step 0
Start Bonsai and start a new project
![](BonVision/assets/Images/Creating_Basic_Step0.PNG)

### Step 1: Initialize
All Bonvision stimuli start with a **RenderFrame** node.
This node passed the render command from the graphics card. 
A![](../assets/Images/Creating_Basic_Step0.PNG)
B![](BonVision/docs/assets/Images/Creating_Basic_Step0.PNG)
C![](../docs/assets/Images/Creating_Basic_Step0.PNG)
D![](BonVision/assets/Images/Creating_Basic_Step0.PNG)
E![](/assets/Images/Creating_Basic_Step0.PNG)
F![]({{'/assets/Images/Creating_Basic_Step0.PNG' | relative_url}})
#(BonVision/docs/assets/Images/CreateBasic/Creating_Basic_Step1_renderFrame.PNG)
***
At this point we need to add a coordinate frame. For simplicity lets use **NormaliszedViewport**
This defined coordinates of the window as -1 to 1 along x and -1 to 1 along y

![](/assets/Images/CreateBasic/Creating_Basic_Step2_normalizedViewport.PNG)
***
### Step 2: Add stimulus
Now we are ready to draw stimuli. We can add the node **DrawGrating**
![](/assets/Images/CreateBasic/Creating_Basic_Step3_1_drawGratings.PNG)

***
### Step 3: Test the grating
You can have a look at the stimulus by hitting **Start** in the options. _Note: on some occasions you might not see the window, in case the window location is outside the screen. In this case, double click 'RenderFrame' and adjust the location parameter (see troubleshooting below)
![](/assets/Images/CreateBasic/Creating_Basic_Step3_2_drawBasicStart.PNG)
***
Hitting start should open up a window showing the grating. You can play around with the parameters of the grating, _Live_ by changing them on the right side of the screen
![](/assets/Images/CreateBasic/Creating_Basic_Step3_3_parameterSettings.PNG)

_You can exit by hitting the Stop button_
***
### Step 5: End the Stimulus at 5s
The next step is to limit the drawing to a limited time. For this we can use the **TakeUntil** node from Bonsai. 

![](/assets/Images/CreateBasic/Creating_Basic_Step4_TakeUntil.PNG)

You will notice this shows up as Red, this is because this needs some kind of argument that tell it when to stop transmitting the inputs. Since we want to end the stimulus in 5s, we can use a **Timer** node from Bonsai. 

![](/assets/Images/CreateBasic/Creating_Basic_Step5_Timer.PNG)

We then connect the Timer to TakeUntil 
![](/assets/Images/CreateBasic/Creating_Basic_Step5_ConnectTimer.PNG)

And set the time on the timer on the right hand side, under _Due Time_

![](/assets/Images/CreateBasic/Creating_Basic_Step6_SetTimer.PNG)
The stimulus when run, will run for just 5s. 

***
### Step 6: Add Workflow Output
![](/assets/Images/CreateBasic/Creating_Basic_Step7_AddWorkflow.PNG)

***
### Step 7: Add _Behavior Subject_ to enable multiple stimuli generation
The easiest way to create multiple stimulus is to split the output of **NormalizedViewport** to multiple listeners, which will then draw the stimuli. We do so by _"Broadcasting"_ using **BehaviorSubject** and adding _"Followers"_ using **SubscribeSubject**
First add BehaviorSubject:

![](/assets/Images/CreateBasic/Creating_Basic_Step8_1_BehaviorSubject.PNG)

Make sure to name it. As a Convention we always use _**DrawStimulus**_ as the name here.

We can then subscribe to this by adding **SubscribeSubject** and choosing DrawStimulus from the dropdown list on the right

![](/assets/Images/CreateBasic/Creating_Basic_Step8_1_SubscribeSubject.PNG)

DrawGratings can now be removed from the top row and placed next to the new node:

![](/assets/Images/CreateBasic/Creating_Basic_Step8_2_full.PNG)

***
### Step 7: Make multiple stimuli using _Behavior Subject_
Adding a second stimulus is now quite straightforward. Just choose the two nodes at the bottom, copy and paste them. So see them differently make sure to change the parameters of one of the gratings on the right side menu.

![](/assets/Images/CreateBasic/Creating_Basic_Step8_2_full_twoGratings.PNG)

This is the final output image example:

![](/assets/Images/CreateBasic/Creating_Basic_Step8_2_full_twoGratings_output.PNG)
***
### Done!

***
***
### Troubleshooting 
In case you do not see a window on the screen after hitting **Start**: double click 'RenderFrame' and adjust the location parameter:
![](/assets/Images/CreateBasic/ShaderWindow.PNG)
