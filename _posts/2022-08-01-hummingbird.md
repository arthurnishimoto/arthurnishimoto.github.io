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

(2019 - present) - Technical Director/Lead Developer

Virtual Reality (HMD), Live Performance, Oculus Quest, Oculus Quest2, Multi-user, Networked, Unity, C#, Blender, Multi-disciplinary team, Voice Chat, VRTK, Audacity, Kinect Tracking

<!--more--> 

<style>
figure {
    background-color: #222;
    color: #fff;
    font: italic smaller sans-serif;
    padding: 3px;
    text-align: center;
}
.column {
  float: left;
  width: 50%;
  padding: 5px;
}
.row::after {
  content: "";
  clear: both;
  display: table;
}
</style>
## Overview
<iframe
    width="640"
    height="480"
    src="https://www.youtube.com/embed/4JueeyZqh5c"
    frameborder="0"
    allow="autoplay; encrypted-media"
    allowfullscreen
>
</iframe>


A collaboration between the Goodman Theatre Alice Rapoport Center for Education and Engagement in Chicago and the Electronic Visualization Laboratory (EVL) at the University of Illinois at Chicago, this work is funded by the University of Illinois System’s Presidential Initiative to Celebrate the Impact of the Arts and the Humanities. The grant proposal  “Transforming Storytelling: Multi-User Virtual Reality Theater for Collaborative Tele-Immersive Exploration,” outlines our goal of exploring how virtual reality technologies and live theater experiences can be brought together as a storytelling medium to encourage theater participation with younger tech-savvy audiences.


This work combines the talent of Chicago-based theater director Jo Cattell with Project PI and EVL/Design Professor Daria Tsoupikova, EVL Director of Research and CS Associate Professor Andrew Johnson, CS/EVL Senior Research Programmer Lance Long, CS/EVL PhD Candidate Arthur Nishimoto, and CS/EVL PhD Student Sai Priya Jyothula.


  * [Official Site](https://hummingbirdvr.com)
  * [Grant Award Press Release](https://www.evl.uic.edu/events/2414)
  
## Contribution Summary
As one of the lead programmers, it was my responsibility to design the interactions in most of the scenes. I worked closely with playwright and director Jo Cattell to translate story elements and actions into VR interactions.


I also worked on designing and refining the custom network server using to synchronize the position and scene states across all of the Oculus Quest HMDs. I prototyped and deployed the controllerless hand tracked version of the experience for the December 2021 show.


During the June 2021 experimental show and the December 2021 public show as part of Chicago Goodman Theatre's New Stages Festival, I was responsible for the smooth operation of the experience, coordinating with the director, actors, and stage managers throughout multiple show runs per day.


[Detailed Contribution](#detailed-contribution)


## Gallery
WIP


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


## Funding
 * U of I System Presidential Initiative to Celebrate the Impact of the Arts and Humanities
 * UIC Award for Creative Activity
 * National Endowment for the Arts
 * Illinois Arts Council Agency (IACA). Media Arts Award.


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


<figure>
	<img src="/images/Hummingbird/GerardFaceCapture01.jpg" />
	<figcaption>Kinect Studio (Left) to Unity Editor (Right)</figcaption>
</figure>


Using the [Cinema Face Cap Facial Capture for Unity](https://assetstore.unity.com/packages/tools/animation/cinema-face-cap-facial-capture-for-unity-59972) package, I connected the Unity Editor to Kinect Studio, played back the captured sessions, and generate an FBX facial animation that was used to create the 3D Gerard head used in the VR world.


<figure>
	<img src="/images/Hummingbird/GerardFaceCapture02.jpg" />
	<figcaption>Animation Alignment Tool in Unity</figcaption>
</figure>


I created a separate Unity application to combine the exported FBX facial animations and audio recordings into a synchroniced character prefab that can be used in the main Hummingbird application. This app was used as a quick way to share various performance takes of the actor and alternate different 3D face models to the team for critique. The original video was added later to the Unity app for more context.


### Character Animation and Dialog System
Hummingbird using two distinct character modes: The 3D Gerard head using FBX animation facial capture data and 2D cartoon faces using a handful of 2D sprites for eyes, blinking, and various mouth movements. The latter is used for other characters such as the talking crab, flowers, and rocks.


Each dialog line has a specific script attached to it which aligns the animation and the audio files. These dialog scripts are triggered by a parent 'Dialog Manager' which in turn can be triggered by either the actor, stage manager, or another script.


<figure>
	<img src="/images/Hummingbird/characterMouthAnimation.jpg" />
	<figcaption>2D Mouth Images and Animator Script</figcaption>
</figure>


For the 2D character animations, the dialog lines are more complex with each dialog line associated with an array of information consisting of a timestamp and a specific mouth sprite to be displayed. I manually selected the mouth shape image for specific timesteps of the audio file. 


### Opening 'Construct' Scene
The Construct scene is the first scene that introduces the participants to the virtual reality world. The overall design and 3D environment was created by a Design student. I coded two major interactions that take place in that environment.


<figure>
	<img src="/images/Hummingbird/centerTable.jpg" />
	<figcaption>Construct Center Table</figcaption>
</figure>


The first is a selection of 3D origami objects that participants can grab and play with to familiarize themselves with this basic interaction. The collision and grabbing is a mix of custom C# scripts and using interactions provided by [VRTK](https://vrtoolkit.readme.io/docs).


<figure>
	<img src="/images/Hummingbird/teleportPads.jpg" />
	<figcaption>Construct Scene and Teleport Pads</figcaption>
</figure>


The final interaction is the teleportion pads which transport the participants into the next scene once they are standing on the right pad.


For the Immersive Pavilion presentations at SIGGRAPH 2022, I created a custom 3D model of the SIGGRAPH logo which is embedded into the center table. The logo is described as:


> A pair of interlocking partial spheres. The space between the two pieces forms a stylized “S,” alluding to the “S” in the SIGGRAPH. The partial spheres can be represented in either two or three dimensions.


<figure>
	<img src="/images/Hummingbird/centerTable-SIGGRAPH.jpg" />
	<figcaption>Alternate SIGGRAPH Center Table</figcaption>
</figure>


I took on the challenge of translating the 2D image into a full 3D shape which matches the appearence of the logo from the right perspective.




### Orchard 1 Scene


<figure>
	<img src="/images/Hummingbird/Orchard1-01.jpg" />
	<figcaption>Orchard 1 Overview</figcaption>
</figure>


Daria Tsoupikova designed the overall layout and asthetic feel of the Orchard 1 scene. My major contributions to this scene is the scripting of the previously mentioned 2D animated face characters which was applied to three different characters: the 'Rock Rock' duo, the Bedrock, and the Flowers.


<figure>
	<img src="/images/Hummingbird/WaterBucket.jpg" />
	<figcaption>Water Particle Effect</figcaption>
</figure>


One of the extra features I added in for the December show was adding interactable water to the water bucket in the scene. Originally just a water texture, I added in the scripting logic to generate sounds and particle effects when an object collides with the water surface. I also refined the effect by including velocity into the calculation so that objects still colliding, but not moving would have a different behaviour than when moving. Also used that value to determine the size of the particles and the audio type and volume played.


<figure>
	<img src="/images/Hummingbird/ActorDialog.jpg" />
	<figcaption>Actor Dialog Interface</figcaption>
</figure>


This scene also introduces the 'Actor' interface that the lead performer can use to trigger dialog lines to continue the story. This was just a front-end enabled addition to the existing character dialog controller. In some cases, the actor had the option to select different takes of the same dialog line to mix up each performance.


<figure>
	<img src="/images/Hummingbird/Orchard1-03.jpg" />
	<figcaption>Flowers and Pedals</figcaption>
</figure>


The final scripted sequence of the scene finds a hidden elevator revealed in a flying particle system of cherry pedals. The elevator would trigger once all participants were standing on it. More details on that in the cave scene.


A later addition to the scene was footprints that would appear when a participant would step on them. Simple done using a collider trigger and a fading script. Had to make sure the colliders didn't impact the grabbable objects or other physics.


### Cave Scene


<figure>
	<img src="/images/Hummingbird/Cave-00.jpg" />
	<figcaption>Cave</figcaption>
</figure>


Unlike most other scenes which was designed by the artist, the cave scene I actually assembled myself using cave assets from the Unity asset store. As this scene has the most complex interactions, this was the original scene built. Many of the original 3D model assets I had modified in Blender to make the holes in the wall for the drawers, the drawers themselves, and the grabbable stalactites. Numerous custom C# scripts and integrations with VRTK was used to create the interactions in this scene.


<figure>
	<div class="row">
	  <div class="column">
		<img src="/images/Hummingbird/Cave-01.jpg" style="width:100%">
	  </div>
	  <div class="column">
		<img src="/images/Hummingbird/Cave-02.jpg" style="width:100%">
	  </div>
	</div>	
	<figcaption>Cave Interaction</figcaption>
</figure>


The quick overview of these interactions are as follows:
 * Aligning the elevator and participants with the previous scene
 * Glowing ceiling stalactites that lightup when grabbed
 * Drawers are revealed when a specific stalactite is near
 * Drawer opening with physics and momentum (Powered by VRTK)
 * Objects sliding inside the drawer
 * Grabbing the coin and coin slot interaction
 * Planting the seed and spawning a pickaxe
 * Using the pickaxe to break the center column with multiple stages of destruction
 * Grabbing the key and teleport out effect
 
#### Orchard2 Scene
The vast majority of the work on the Orchard2 scene which follows the cave was done by Computer Scientist Sai Priya Jyothula and Artist/Designer Daria Tsoupikova.


I mostly did cleaning up of specfic technical bugs or adding hooks for the story manager and stage manager interfaces to allow for remote triggered of story events.


### Statue Scene


<figure>
	<img src="/images/Hummingbird/Statue-00.jpg" />
	<figcaption>Statue Flight Scene</figcaption>
</figure>




The statue scene went through a number of design revisions due to the changing scope of the project. The final version of the scene I added the following interactions:


 * Floor triggers for raising the partiticants up to the statue face while standing on the moving hands (modified from the Construct teleport pads)
 * Attaching and flying the participants on a pre-designed flight path
 * Creating a portal with a 'generalized perspective projection' effect back toward the previous scene




### Server Stage Manager Control Interface
The Server Stage Manager interface is a graphical interface connecting many of the debug and override features originally scripted into many of the story interaction scripts.


The main interface is divided up into the following parts:
 * Client Status
 * Gerard Dialog
 * Story Manager
 * Audio Mixer


#### Client Status
<figure>
	<img src="/images/Hummingbird/ServerUI-00.jpg" />
	<figcaption>Server UI: Client Status</figcaption>
</figure>


The Client Status display shows all connected Hummingbird clients, whether they're HMDs or Observer clients. Each client has controls for configuring their role (Actor/participant), manually overriding their player ID, avatar, color, or triggering debug/override commands if something goes wrong.


#### Gerard Dialog
<figure>
	<img src="/images/Hummingbird/ServerUI-01.jpg" />
	<figcaption>Server UI: Gerard</figcaption>
</figure>


This screen allows the stage manager to trigger extra dialog lines in reaction to participants in the experience. These are mostly short generic reaction lines that were recorded. For example I would trigger some of these lines as a reaction to something a participant said or did. A common one was a dialog line where Gerard would say 'don't touch my fish' if a participant either mentioned the fish or attempted to interact with one.


#### Story Manager
<figure>
	<img src="/images/Hummingbird/ServerUI-02.jpg" />
	<figcaption>Server UI: Story Manager</figcaption>
</figure>


The Story Manager screen was used to manually trigger or bypass certain story events in the case something went wrong in how participants were supposted to trigger something, or also used to help move the story forward if participants were taking longer than anticipated.


A common use case for this was in the cave scene where participants had to complete a long sequence of grabbing a statactite, grabbing a coin, inserting the coin into a slot, grabbing a seed, planting that seed to grow a pickaxe, and finally grabbing and using the pickaxe to break a stone column.


In other to complete the cave scene, all six participants had to complete this sequence. On occation a stalactite would get stuck, the seed would drop out of the world without spawning a pickaxe, or participants would not hit the center column with the pickaxe correctly to count as a hit.


This interface had numerous reset and skip triggers to respawn objects and force trigger events to allow the story to continue with minimal interruption.


#### Audio Mixer
The audio mixer was a simple interface to adjust audio levels between HMD audio, room/environmental audio, and the master audio level across all clients.




### Integration of Hand Tracking
The original June workshop used the standard Oculus Quest controllers for interaction. With the exception of the actor, participants solely interacted with the world by using the trigger to grab/pickup objects.


<figure>
	<div class="row">
	  <div class="column">
		<img src="/images/Hummingbird/JuneShowControllers.jpg" style="width:100%">
	  </div>
	  <div class="column">
		<img src="/images/Hummingbird/DecShowHandTracking.jpg" style="width:100%">
	  </div>
	</div>	
	<figcaption>June Controllers (Left) and December Hand Tracking (Right). Photos by Lance Long</figcaption>
</figure>


After the June show, I began exploring use of the recent experimental feature for hand tracking via the Oculus Quest's existing camera tracking system.


I quickly adapted the hand tracking API for Hummingbird, simplifiying it a bit so that any finger touching the thumb would be considered a grab gesture. This worked perfectly with the simple grab/pickup interaction of Hummingbird.


<figure>
	<img src="/images/Hummingbird/TreeHand.jpg" />
	<figcaption>Tree Hand Controlled by Hand Tracking</figcaption>
</figure>


The one place where I used the entire hand tracking data was for the tree hands. Since these hands had a fully articulated 5-finger armature, I mapped the finger joint rotations from the hand tracking example prefab into the tree hand's joints. A new network sync message was also created so that participants could see each other's hand movements.


### Observer View and CAVE2 Pre-Show
As a theaterical production, one of the project goals was to maximize the number of people that could see the performance. As only 5 participants could actively experience the VR world, we wanted to have an 'observer' view for passive audiances to see what was happening in the 'VR stage.'


I essentally used a modified version of the HMD client and attached my orbiting 'third-person camera controller' which I wrote years ago and keep reusing and refining as the need arises. Using the mouse or touch screen on the Continuum main wall, we were able to in real time move the camera to focus on interesting moments in the live performance.


<figure>
	<img src="/images/Hummingbird/PXL_20211204_004039214.MP.jpg" />
	<figcaption>EVL Continuum Main and Side Displays</figcaption>
</figure>


Originally just being displayed on the main wall, eventually we had both walls showing a view into the VR world. As test audiances and rehersals went on, it became obvious that we need to have a mechanism for pre-selected views that could be easily toggled between.


For the December 2021 shows, each scene had three or four preset views selectable using the keyboard on an observer client. The views were selected to provide the non-VR audiance members the best view of what was going on in the virtual world. I also designed the image that was projected on the floor.


<figure>
	<img src="/images/Hummingbird/Hummingbird-PreshowCAVE2.jpg" />
	<figcaption>Pre-Show in CAVE2</figcaption>
</figure>


The preshow sequence consisted of both a pre-recorded video of Gerard which introduces himself and the world the Hummingbird show is based. It also provided a place for the actors to discuss any important safety and basic interaction information as the general target audiance for that show was more non-technical, traditional theater patrons.


While we had ways to run video in CAVE2, I decided it was best to run the video inside a CAVE2 Unity application as a render texture and use the rest of the display space for some simple 3D models and animations to complement the video.


### Technical Director
During all three previous performances of Hummingbird (June 2021 workshop, December 2021 New Stages Festival, August 2022 SIGGRAPH Immersive Pavilion), I served in a Technical Director role supervising the setup, preparation, and running of the server, VR HMDs, and auxiliary displays.


<figure>
	<img src="/images/Hummingbird/Hummingbird-DecStage.jpg" />
	<figcaption>December 2021 show stage viewed from audiance seating</figcaption>
</figure>


During the show, it was my primary role to make sure all the VR HMDs are running properly, monitoring the status of the participants, running override and/or show triggers as needed, as well as a supporting actor role in the latter two performances.


### Integration of HMD Voice Chat
In preparation for both future plans to have two remote groups of actors plus participants interacting and for local voice reinforcement in noisy environments (such as a conference show floor setting), I looked into adding a voice chat system into Hummingbird leveraging the existing microphone capabilities of the Oculus Quest.


I looked at a number of existing voice chat solutions available online and on the Unity Asset store and eventually decided on using UniVoice, an open source solution using node.js as the server.


Using all the HMDs as voice clients, they were able to connect to the node.js server running on the same machine as the game server. The game server would do the initial connection, create the chatrooms (one for everyone and a private channel for the actor and directors).


Wrote some additional logic between the game server and HMDs to properly associate HMD connection IDs with voice IDs so that the AudioSource for each voice client can be correctly associated to the correct avatar in the VR world.


### Planning for SIGGRAPH 2022


<figure>
	<div class="row">
	  <div class="column">
		<img src="/images/Hummingbird/SIGGRAPH22-BoothStudy.jpg" style="width:100%">
	  </div>
	  <div class="column">
		<img src="/images/Hummingbird/SIGGRAPH22-Booth.jpg" style="width:100%">
	  </div>
	</div>	
	<figcaption>SIGGRAPH Booth Study (Left) and Actual Booth (Right)</figcaption>
</figure>


While planning for performing Hummingbird at SIGGRAPH 2022's Immersive Pavilion I created a quick mockup of the proposed booth layout in Blender and Unity. While originally created for my own organizational purposes for laying out the space, we eventually used it with the members of the Immersive Pavilion committee for final planning of our booth.


The mockup was exported as a WebGL build and was shared with the team which is still available [here](/HummingbirdSIGGRAPH22BoothStudy)






### Isadora and Video Editing for SIGGRAPH
Most of the video content for Hummingbird was created by designer Liviu Pasare who recorded and edited the pre-rendered video content that played during the show. The more dynamic videos used in the opening scene where the Gerard video needs to interact with the actor playing Aya live, Isadora a programmable media playback and cueing software was used.


While for all three shows Liviu did the programming, I did end up learning a bit of how Isadora works and doing some video editing in DaVinci Resolve to make some minor modifications for the SIGGRAPH 2022 performance.


