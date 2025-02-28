# Week 01

## The Game

Our idea was to depict the DHBW Karlsruhe in the exact same way us students see it when the exams are near.
The game is a horror game, with a Backrooms style, that takes place inside a place that looks similar to the DHBW
Karlsruhe.

## Technology used

- Unreal Engine 5
- [Perforce / Helix Core](https://www.perforce.com/products/helix-core) as Version Control
- [Writerside](https://www.jetbrains.com/writerside/) for this blog
- Jira for project management
- Discord for communication and regular meetings

## Team Members

We added an overview of our team members, you can find that in the [](Team-Members.md) section.

## Progress this week

After a bumpy start with our version control system, we managed to get everything up and running.
Initially, we decided to use Git(hub) for version control, but we quickly realized that it was not the right tool for
Game Development projects. To solve this issue, we switched to Perforce, which is a much better fit for our needs.

We also set up our project management tool Jira and started planning our project and created some tasks.

Once we were ready to work on the game, we started by creating a basic map layout with procedural generation of a simple
hallway, together with a starter room.

![Hallway.png](Hallway.png)

The hallway is procedurally generated and will be the main part of the game. The player will have to navigate through
these hallways, we are however unsure about the final goal and layout. \
The rooms are currently still missing, but we added some sound effects and flickering lights:

<video src="Flickering-Lamps.mp4"/>

The lamps in the hallway are flickering, which adds to the horror atmosphere of the game. They also have sound effects,
with a constant buzzing sound, and a different sound effect when they flicker. They are also less bright than the lamps
in the starter room, which makes some parts of the hallway quite dark.

![Starter-Room.png](Starter-Room.png)

The starter room contains some brighter lights that enlightens the room with the two elevator doors, the player will be
able to go into them in a future version.


