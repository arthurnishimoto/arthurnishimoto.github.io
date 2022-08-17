---
title: "Hummingbird"
excerpt_separator: "<!--more-->"
image:
  path: /images/Hummingbird/PXL_20211204_004039214.MP.jpg
  thumbnail: /images/Hummingbird/hummingbird-thumb.jpg
category:
  - Art
  - Technical Highlight
tags:
  - Virtual Reality (HMD)
  - Live Performance
  - Oculus Quest
  - Oculus Quest2
  - Multi-user
  - Networked
  - Unity
  - C# (CS)
  - Blender
  - Multi-disciplinary team
  - Voice Chat
  - VRTK
  - Audacity
  - Kinect Tracking
---
### A Multi-User, Virtual Reality Theatrical Experience Led By A Live Actor

(2019 - present) - Lead Scientist/Developer/Technical Director

Virtual Reality (HMD), Live Performance, Oculus Quest, Oculus Quest2, Multi-user, Networked, Unity, C#, Blender, Multi-disciplinary team, Voice Chat, VRTK, Audacity, Kinect Tracking

<!--more--> 

## Overview
<div id="frameContainer">
<iframe
    width="640"
    height="480"
    src="https://www.youtube.com/embed/4JueeyZqh5c"
    frameborder="0"
    allow="autoplay; encrypted-media"
    allowfullscreen
>
</iframe>
</div>


A collaboration between the Goodman Theatre Alice Rapoport Center for Education and Engagement in Chicago and the Electronic Visualization Laboratory (EVL) at the University of Illinois at Chicago, this work is funded by the University of Illinois System’s Presidential Initiative to Celebrate the Impact of the Arts and the Humanities. The grant proposal  “Transforming Storytelling: Multi-User Virtual Reality Theater for Collaborative Tele-Immersive Exploration,” outlines our goal of exploring how virtual reality technologies and live theater experiences can be brought together as a storytelling medium to encourage theater participation with younger tech-savvy audiences.


This work combines the talent of Chicago-based theater director Jo Cattell with Project PI and EVL/Design Professor Daria Tsoupikova, EVL Director of Research and CS Associate Professor Andrew Johnson, CS/EVL Senior Research Programmer Lance Long, CS/EVL PhD Candidate Arthur Nishimoto, and CS/EVL PhD Student Sai Priya Jyothula.


  * [Official Site](https://hummingbirdvr.com)
  * [Grant Award Press Release](https://www.evl.uic.edu/events/2414)
  
## Contribution Summary
As one of the lead programmers, it was my responsibility to design the interactions in most of the scenes. I worked closely with playwright and director Jo Cattell to translate story elements and actions into VR interactions.


I also worked on designing and refining the custom network server using to synchronize the position and scene states across all of the Oculus Quest HMDs. I prototyped and deployed the controllerless hand tracked version of the experience for the December 2021 show.


During the June 2021 experimental show and the December 2021 public show as part of Chicago Goodman Theatre's New Stages Festival, I was responsible for the smooth operation of the experience, coordinating with the director, actors, and stage managers throughout multiple show runs per day.


[Detailed Contribution](#detailed-contribution)


## Publications
<p float="left">
  <img src="/images/Hummingbird/GoodmanTheatreNewStages2021.jpg" width="200" />
  <img src="/images/Hummingbird/SIGGRAPH22-ImmersivePavilion.jpg" width="200" /> 
</p>
  * [Goodman Theatre New Stages 2021 Festival Page](https://www.goodmantheatre.org/newstages) ([Archived](/archived/GoodmanNewStages2021/index.html))
  * [Goodman Theatre Hummingbird Page](https://www.goodmantheatre.org/Hummingbird) ([Archived](/archived/GoodmanHummingbird/index.html))
  * Tsoupikova, D., Cattell, J., Johnson, A., Nishimoto, A., Jyothula, S.P., Long, L., Shum, S., 2022. Hummingbird: Collaborative Interactive Adventure Bridging Live Theater and VR. SIGGRAPH 2022 Immersive Pavilion (Vancouver, BC, Canada, Aug. 7-11, 2022). DOI: [https://doi.org/10.1145/3532834.3536213](https://dl.acm.org/doi/10.1145/3532834.3536213)


## Awards
  * [UIC Graduate College Image of Research 2022, Honorable Mention](https://www.evl.uic.edu/events/2646)


## Detailed Contribution
My main contributions to Hummingbird can be broken down into the following categories:
  * [Facial Capture of Gerard Actor Using Kinect2](#facial-capture-of-gerard-actor-using-kinect2)
  * [Character Animation and Dialog System](#character-animation-and-dialog-system)
  * [Opening 'Construct' Scene](#opening-construct-scene)
  * [Orchard 1 Scene](#orchard-1-scene)
  * [Cave Scene](#cave-scene)
  * [Statue Scene](#statue-scene)
  * [Server Stage Manager Control Interface](#server-stage-manager-control-interface)
  * [Integration of Hand Tracking](#integration-of-hand-tracking)
  * [Observer View and CAVE2 Pre-Show](#observer-view-and-cave2-pre-show)
  * [Technical Director](#technical-director)
  * [Integration of HMD Voice Chat](#integration-of-hmd-voice-chat)
  * [Isadora and Video Editing for SIGGRAPH](#isadora-and-video-editing-for-siggraph)
  
### Facial Capture of Gerard Actor Using Kinect2
Actor Dwight Sora portrays Gerard, the CEO of the Hummingbird story's Gerard Corportion who introduces the participants into his world as a giant floating head on a screen and later as a 3D avatar in the virtual world. During the green screen video shoots used to create the live-action introduction sequences, I simultaniously recorded Dwight's performance using a Kinect for Windows v2 sensor - capturing the color, depth, and IR information using Kinect Studio.


![Kinect to Cinema Face Cap for Unity](/images/Hummingbird/GerardFaceCapture01.jpg){: .align-center}


Using the [Cinema Face Cap Facial Capture for Unity](https://assetstore.unity.com/packages/tools/animation/cinema-face-cap-facial-capture-for-unity-59972) package, I connected the Unity Editor to Kinect Studio, played back the captured sessions, and generate an FBX facial animation that was used to create the 3D Gerard head used in the VR world.


![Animation Alignment Tool](/images/Hummingbird/GerardFaceCapture02.jpg){: .align-center}


I created a separate Unity application to combine the exported FBX facial animations and audio recordings into a synchroniced character prefab that can be used in the main Hummingbird application. This app was used as a quick way to share various performance takes of the actor and alternate different 3D face models to the team for critique. The original video was added later to the Unity app for more context.


### Character Animation and Dialog System
Hummingbird using two distinct character modes: The 3D Gerard head using FBX animation facial capture data and 2D cartoon faces using a handful of 2D sprites for eyes, blinking, and various mouth movements. The latter is used for other characters such as the talking crab, flowers, and rocks.


Each dialog line has a specific script attached to it which aligns the animation and the audio files. These dialog scripts are triggered by a parent 'Dialog Manager' which in turn can be triggered by either the actor, stage manager, or another script.


![Image of 2D animation script]()


For the 2D character animations, the dialog lines are more complex with each dialog line associated with an array of information consisting of a timestamp and a specific mouth sprite to be displayed. I manually selected the mouth shape image for specific timesteps of the audio file. 


### Opening 'Construct' Scene
The Construct scene is the first scene that introduces the participants to the virtual reality world. The overall design and 3D environment was created by a Design student. I coded two major interactions that take place in that environment.


![Image of center table]()


The first is a selection of 3D origami objects that participants can grab and play with to familiarize themselves with this basic interaction. The collision and grabbing is a mix of custom C# scripts and using interactions provided by [VRTK](https://vrtoolkit.readme.io/docs).


![Image of teleport pads]()


The final interaction is the teleportion pads which transport the participants into the next scene once they are standing on the right pad.


For the Immersive Pavilion presentations at SIGGRAPH 2022, I created a custom 3D model of the SIGGRAPH logo which is embedded into the center table. The logo is described as:
```
A pair of interlocking partial spheres. The space between the two pieces forms a stylized “S,” alluding to the “S” in the SIGGRAPH. The partial spheres can be represented in either two or three dimensions.
```


![Image of SIGGRAPH table]()


I took on the challenge of translating the 2D image into a full 3D shape which matches the appearence of the logo from the right perspective.




### Orchard 1 Scene






### Cave Scene


### Statue Scene


### Server Stage Manager Control Interface


### Integration of Hand Tracking


### Observer View and CAVE2 Pre-Show 


### Technical Director
During all three previous performances of Hummingbird (June 2021 workshop, December 2021 New Stages Festival, August 2022 SIGGRAPH Immersive Pavilion), I served in a Technical Director role supervising the setup, preparation, and running of the server, VR HMDs, and auxiliary displays.


During the show, it was my primary role to make sure all the VR HMDs are running properly, monitoring the status of the participants, running override and/or show triggers as needed, as well as a supporting actor role in the latter two performances.


### Integration of HMD Voice Chat


### Isadora and Video Editing for SIGGRAPH




