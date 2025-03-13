# Week 03

## New Technology used this week

- 

## Progress this week

This week we improved our sounds and added new sounds like elevator noises etc.
We have also been looking for materials such as decorations that we will add to our game in the different
classrooms and bring some life to the game. \
... 

[//]: # (TODO add progress)

### Sounds

For the right choice of sounds, suitable free sounds were searched for on the Internet. 
An extensive search was carried out to find the right sound for the game. 
These sounds were then edited again with FL Studio to better adapt the sounds to the game and create a unique modified sound.

Example for a provider of free sounds:

![free_sounds_provider.png](free_sounds_provider.png)

### Assets

Via the FAB marketplace, we have been looking for matching 3D models, which serve as decoration of the environment.
We have selected various decorative elements such as blackboards, projectors, tables, chairs and many other elements which can be added to the room in the next steps.

The following image shows the FAB Marketplace:

![fab_marketplace.png](fab_marketplace.png)

### Movement System

To make the game feel better we improved our movement system, so the players have a better feeling of their character. 
As well as in the multiplayer the other characters should look a bit familiar and not so static, so we also added their some animations.
So we went through the following steps:

### Added Sprint Stamina
In first place we adjusted the character movement by adjusting the walk speed, so the character wont automatically sprint.
Instead the sprint mode can be toggled by holding Shift down, also now if the character sprints he will lose stamina and regenerate if he is back walking or standing still.
The current stamina gets displayed in an progressbar in the bottom left.

### Improved Footsteps
Last week we already added footsteps, which didnt sounded quite good, so we improved them by not only taking on sound, instead we took 10 sounds which get automatically randomized due Unreal Engine Sound Cue Class.

### Crouch
Now we have already sprinting and walking, whats missing is crouching, for that we added a new animation, which let the player crouch. We added both an idle and walk animation for the crouch, which can be entered by holding down CRTL.

We found both of the animations here:
https://www.mixamo.com/#/

#### Adding more animations
In the last step we wanted to make the head movement of each player visible for that we made the whole upper body moveable so, also in the multiplayer all players can see which direction a player is currently looking at, making the game feel better.

#### Multiplayer
We encountered through the steps some issue that the developed features were only visible to the client not to the other players.
So we had to use an UnrealEngine concept that replicates everything to all others players. Thats because UnrealEngine tries to reduce the packets that are send through the multiplayer.
So we had to use the following concept for features like the body movement, when the player moves the camera and making the sprint animation visible to all.

Taking the sprint example it looks like this:

![multiplayer_sync_example.png](multiplayer_sync_example.png)

So instead of just doing it on the client we call an RunOnServer_Sprint Event, which **replicates on the Server** and **MultiCast it to every Player**.
![multiplayer_sync_example_runonserver.png](multiplayer_sync_example_runonserver.png)

That happens through the call of the event MultiCast_Sprint, which Replicate Mode is set to **Multicast**.
![multiplayer_sync_example_multicast.png](multiplayer_sync_example_multicast.png)


## Time spent

[//]: # (TODO insert timesheet)
