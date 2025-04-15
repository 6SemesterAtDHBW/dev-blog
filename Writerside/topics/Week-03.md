# Week 03

## Addictive Patterns
This week focus of the class were addictive patterns. Especially what kind of addictive pattern we will have in our game and how we implement them. Basically they can be divided in the categories Create, Collobarate, Compete and Explore. 
For each game the categories have an different impact and a different weight. The thoughts we made for each category are summarized below:

### Create

- Character Selector

### Collobarate

- Multiplayer with Friends
- Multiplayer only actions or locations, you need to be together to find certain places or do certain actions

### Compete

- Achievemnents like Finish in Time, Fins Easter Eggs, Special Items

### Explore

- Unique Map
- Find special places, Easter Eggs, hidden content
- Find items

Some of the points are already implemented, some are still in the planning phase. We will see how we can implement them in the next weeks.

## Progress this week

This week we improved our sounds and added new sounds like elevator noises etc.
We have also been looking for materials such as decorations that we will add to our game in the different
classrooms and bring some life to the game. We also further improved the movement system, added new animations and
improved the camera effects.
...

### Improved Starter Room

We improved the starter room further over the last week.
The mirror in the last week had some issues with lighting - there were flickering dots flying around on all textures and
no color was visible. After some information gathering, we found out that the issue was caused by the `Lumen` system for
Global Illumination, which has some issues with reflections in the newest Unreal Engine version.

![illumination-settings.png](illumination-settings.png)

To fix this, we changed to the newer `Screen Space` system for our First Person Camera. This comes with a few major
improvements, even tho it is currently only in Beta. You can see a real difference:

<video src="illumination-old.mp4" preview-src="illumination-old-thumbnail.png"/>

This is the old system. Not only are the flickering dots gone, but if you compare it to the new system, you can see a
few more real improvements:

- Textures are fully visible in the mirror
- The wall textures appear much more detailed
- The lighting is much more realistic, seeming a bit more dim
- If you look around, the effect of bending on the side of the mirror doesn't look as weird (in the old system, it looks
  as if that's not a reflection, but the real texture)

<video src="illumination-new.mp4" preview-src="illumination-new-thumbnail.png"/>

Together with this, we improve our lamps the make them invisible through walls if looked at through the mirror.
We also changed the room layout a bit, so that the starter room resembles the room better.

### Sounds

For the right choice of sounds, suitable free sounds were searched for on the Internet.
An extensive search was carried out to find the right sound for the game.
These sounds were then edited again with FL Studio to better adapt the sounds to the game and create a unique modified
sound.

Example for a provider of free sounds:

![free_sounds_provider.png](free_sounds_provider.png)

### Assets

Via the FAB marketplace, we have been looking for matching 3D models, which serve as decoration of the environment.
We have selected various decorative elements such as blackboards, projectors, tables, chairs and many other elements
which can be added to the room in the next steps.

The following image shows the FAB Marketplace:

![fab_marketplace.png](fab_marketplace.png)

### Movement System

To make the game feel better we improved our movement system, so the players have a better feeling of their character.
As well as in the multiplayer the other characters should look a bit familiar and not so static, so we also added their
some animations.
So we went through the following steps:

### Added Sprint Stamina

In first place we adjusted the character movement by adjusting the walk speed, so the character won't automatically
sprint.
Instead, the sprint mode can be toggled by holding Shift down, also now if the character sprints he will lose stamina
and regenerate if he is back walking or standing still.
The current stamina gets displayed in a progressbar in the bottom left.

### Improved Footsteps

Last week we already added footsteps, which didn't sound quite good, so we improved them by not only taking on sound,
instead we took 10 sounds which get automatically randomized due Unreal Engine Sound Cue Class.

### Crouch

Now we have already sprinting and walking, what's missing is crouching, for that we added a new animation, which let the
player crouch. We added both an idle and walk animation for the crouch, which can be entered by holding down CTRL.

We found both of the animations here:
https://www.mixamo.com/#/

#### Adding more animations

In the last step we wanted to make the head movement of each player visible for that we made the whole upper body
moveable so, also in the multiplayer all players can see which direction a player is currently looking at, making the
game feel better.

#### Multiplayer

We encountered through the steps some issue that the developed features were only visible to the client not to the other
players.
So we had to use an UnrealEngine concept that replicates everything to all others players. That's because UnrealEngine
tries to reduce the packets that are send through the multiplayer.
So we had to use the following concept for features like the body movement, when the player moves the camera and making
the sprint animation visible to all.

Taking the sprint example it looks like this:

![multiplayer_sync_example.png](multiplayer_sync_example.png)

So instead of just doing it on the client we call an RunOnServer_Sprint Event, which **replicates on the Server** and *
*MultiCast it to every Player**.

![multiplayer_sync_example_run-on-server.png](multiplayer_sync_example_run-on-server.png)

That happens through the call of the event MultiCast_Sprint, which Replicate Mode is set to **Multicast**.

![multiplayer_sync_example_multicast.png](multiplayer_sync_example_multicast.png)

### Camera Effects

To make the game more realistic and to give the player a better horror feeling of the game, we changed the following
camera effects:

- Added a vignette effect to the camera, which darkens the edges of the screen and makes the center of the screen
  brighter,
- Added a chromatic aberration effect to the camera, which makes the colors of the screen look a bit distorted,
- Added a bloom effect to the camera, which makes the light sources in the game look a bit brighter and more realistic,
- Added a depth of field effect to the camera, which makes the objects in the background look a bit blurry and the
  objects in the foreground look a bit sharper,

and many more smaller changes to the camera effect settings.

### Enemy AI

We have added a new small enemy AI to the game, which is in the current state a simple enemy that follows the player if
it is in a certain range.
The enemy AI is based on the Unreal Engine AI Controller and uses the Unreal Engine AI Perception System to detect the
player.

<video src="enemy-ai.mp4"/>

## Time spent

![Timesheet-W3.png](Timesheet-W3.png)
