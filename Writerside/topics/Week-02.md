# Week 02

## New Technology used this week

- [FL Studio](https://www.image-line.com/)
- Blender (Modification of some static meshes)

## Architecture
The main focus in week 2 was on creating an concept for our architecture.
Although the input we got was mainly focused on Unity, we still got some relevant stuff to present.
So the main different is clearly that in Unity the logic is gets written in C, while in UnrealEngine we can use such things as blueprints.
Although there is C++ code and classes available in most cases its not used. As all the functionalities are covered in Blueprints.

### Project Structure
To start with the basics our project structure looks like this.

![projectStructure.png](projectStructure.png)

Thats the vary basics but still relevant so we all know were to find certain models and blueprints.

### Perforce HelixCore Setup
As we use Perforce HelixCore as Version Control System we setup up some Streams in git known as branches, so we all can code at the same time without creating much conflicts.

![perforce_streams.png](perforce_streams.png)

Its a very basic concept of streams, a main stream and for each dev and own stream.

### Coding / Blueprints
As already mentioned in UnrealEngine there is no real coding and classes as their blueprints.
So widely know concepts in architecture cant be used directly. Still in Blueprints there also exists stuff like Inheritance, which is also one of the main part we will use.
So an example for that would be that at the moment we have an upper class BP_FirstPersonCharacter, which handles all the logic but has like an template character used for development.
To create multiple characters we could create parents of that class were we onl adjust the character and some animations details, but the logic is still handled, by the parent class.
While that is an theoretical example, we can also present one we will defintly implement.

So as we have items in the game that can be picked upped we will have a parent class to handle that.

![inheritance.png](inheritance.png)

The parent class will have a mesh and a collision sphere, to handle the pickup, for each item in the game like a flashlight a child could be added were only the mesh must be updated.
Additionally in the child there could be also an adjustment of parent settings or additions to functionalities as already known from the concept of inheritance.

## Progress this week

This week, we created new sounds, reworked the starter room and gave the elevator some animations. We also reworked a
main menu that shows up when the game is started and added support for multiplayer through Steam.

### Sounds

First, we downloaded some sounds and modified them using FL Studio. We added filters and other modifications, to create
a unique sound for the game.

Once we had modified the sounds, we integrated them into the game. Of course, the sounds are not yet perfect at this
stage of the project.
They will still be improved so that they feel natural when playing.

The following image is a Screenshot of the Mixing & Filter area in FL Studio:

![FL_Studio.png](FL_Studio.png)

### Elevator animations

We converted the elevator door into a blueprint and added a sliding animation to it. The elevator door now opens when
the player stands inside the elevator.

We also added a new spawn point inside the elevator, which means that the player now starts inside the elevator.

<video src="Elevator-Animation.mp4"/>

### Reworked Starter Room

As it was already possible to see in the video above, we added a mirror to the elevator. This was done to resemble the
real-life elevator in the building where the game is set as close as possible.

This came with the problem that the current starter room was invisible in the mirror. After a bit of debugging, we found
out, that the Unreal Engine Box Brushes are sort of deprecated and won't render in the lighting system, which is
possible to see in the Lumen overview mode. Due to this, we had to remake the whole room using static meshes inside the
Modelling Editor.

This wireframe shows the difference between the two rooms (top is old, bottom is new):

![Wireframe-Modelling.png](Wireframe-Modelling.png)

After doing this, the mirror works flawlessly (and exposes that we were too lazy to add a player model):

<video src="Elevator-Mirror.mp4"/>

The elevator is now fully functional and complete, we will however still change the layout of the room, as there is
supposed to be a second elevator, as well as two hallways on the side of them.

### Multiplayer and Main Menu

We have added the feature to play the game in multiplayer mode with your friends.
These sample images and videos show what our multiplayer currently looks like.

At the current state, the multiplayer can be shared with up to 4 people on one server.

To join a server, we added a Main Menu with basic functionalities like creating a server, viewing a list of active
servers, and joining a server.

![Main-Menu-W2.png](Main-Menu-W2.png)

![Server-List-W2.png](Server-List-W2.png)

![Create-Server-W2.png](Create-Server-W2.png)

We also played around a bit in the game and took some screenshots and videos of the multiplayer mode, since we wanted to
share how even just running around with friends can be fun:

![Multiplayer-Demo-1.jpg](Multiplayer-Demo-1.jpg)

<video src="Multiplayer-Demo-Video.mp4"/>

## Time spent

![Timesheet-W2.png](Timesheet-W2.png)
