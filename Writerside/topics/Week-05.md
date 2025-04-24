# Week 05

## Progress this week

[//]: # (TODO add progress info)

This week we have been mostly working on the main map like classrooms and hallways as well as on implementing voiceChat for multiplayer.

### Improved Main Map with new Assets

Firstly, there are now many new custom-made assets in the game, which are used to decorate the map. We have added many new props like tables, chairs, whiteboards and other props to make the map look more like the DHBW.

![assets.png](assets.png)

To improve the map building, walls, floors and ceilings were created in a modular way. This means that the walls, floors and ceilings are made up of several parts, which can be combined with each other. This allows us to create a more realistic map and also to create new rooms faster.
Almost all the assets come in 1 meter, 2 meter, 5 meter and 10 meter sizes, so that we can create a room of any size.

![modular_assets.png](modular_assets.png)

Also created where different windows and doors to complete the hallways and rooms.

![modular_assets_2.png](modular_assets_2.png)

These modular assets where used to build parts of the hallway and rooms.

![modular_hallways.png](modular_hallways.png)
![room.png](room.png)

But to create the map even faster, everything was built with `Procedural Content Generation`. 
Specific points are created along a spline, which are then replaced with all the assets.
This allows us to make the hallway as long as we want and create everything fast.

![pcg_hallway.png](pcg_hallway.png)
![pcg_room.png](pcg_room.png)

## Collectable Items

Exam results are now collectable items in the game. They are the main task in the game - Collect all exam results.

![examResults](examResults.png)

All the exam results need to be collected to progress further. Also for every next level, more exam results need to be collected.

To spawn the exam results, actors are generated from the `PCG`-system. This allows us to spawn the exam results in a specific area with random rotation and offset while also set the amount of exam results that need to be collected.


## Timer

The timer was implemented to show the time left for the players to finish the game. The timer is displayed in the top of the screen and counts down from 10 minutes.

![timer](timer.png)

### VoiceChat

To further improve upon the multiplayer aspect, voice chat was introduces. This is currently in its early stages and has some issues with the audio quality as well as selecting the right audio device.
We use Steams inbuilt `VOIP`-feature for Unreal Engine, though this has its limitations as mentioned.

## Topic this week

[//]: # (TODO is there a topic? if yes, add it, if not, delete this section)

## Time spent

[//]: # (TODO insert timesheet) 