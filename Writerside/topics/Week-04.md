# Week 04

## Game Analytics

### Introduction

Game analytics is an essential tool for analyzing and improving player experiences.
This concept outlines the collection and utilization of game data in a horror game developed with Unreal Engine 5,
focusing on player interactions, emotions, and game progress.

### Objectives of Game Analysis

- Analysis of player behaviour (movement patterns, interactions, game dropouts)
- Examination of stress and fear reactions
- Identification of balancing issues and difficulty levels
- Evaluation of cooperative elements in multiplayer gameplay

### Data Collection

The collection of game data is carried out through various mechanisms within Unreal Engine 5:

#### In-Game Telemetry

- Movement Data (Player position, movement paths, time spent in specific areas)
- Interaction Data (Use of objects, trigger activations)
- Latency Times (Reaction times to jump scares or threats)
- Task Completion (Time taken to complete tasks, success/failure rates, cooperative vs solo task attempts)

### Biometric Data (Just Concept)

- Heart rate measurement (via external devices such as smartwatches or ECG sensors)
- Eye-tracking for analyzing gaze movements
- Facial Expression Analysis (Using webcam-based AI to detect expressions related to fear, surprise, or stress during
  intense gameplay moments)
- Voice Stress Analysis (Evaluating voice pitch and tremors during player communication to determine emotional states)
- Muscle Tension Detection (Capturing involuntary muscle reactions, particularly in the face and hands, to detect
  subconscious fear responses)

### Questionaries and Player Feedback

- Subjective assessments through questionnaires after a game session
- Direct feedback on specific game events

### Technical Implementation in Unreal Engine 5 (Ideas)

### Data Logging

- Use of the Unreal Insights analytics platform for real-time monitoring
- Multiplayer event tracking to analyze cooperation and competition dynamics

### Visualization and Analysis

- Heatmaps to represent player movements
- Statistical Analyses to identify trends and patterns
- Player Interaction Metrics to assess teamwork and individual decision-making
- Biometric Data Correlation to map physiological responses to in-game events for improved horror mechanics design

## Data Protection and Ethical Considerations

- Anonymization of data to protect privacy
- Player consent for data collection in accordance with GDPR
- Transparency by providing access rights to players

### Final Implementation

So above we made a big concept of what is possible what would be an optimal solution for our game.
Still we needed to first implement a basic version of the game analytics, before we go into detail.
For that we looked out for solutions and there were a lot, especially if you are willing to pay.
But we preferred a free solution, that isn't the default Unreal Engine 5 Insights, which are good, but lack some
functionalities.
So we decided for GameAnalytics.com, is free for small teams and was quite easy to integrate.
Right of the box, it offers a lot of functionalities, like it shows the current users playing, sending errors to it and
so on.
That all is visible in a web-panel, that looks like this:

![GameAnalyticsWebPanel.png](GameAnalyticsWebPanel.png)

In that example we only have an example of some stats, in specific, the Realtime Stats of our game.
Next up we decided to log some events, getting information about how the player interacts while playing the game.
Therefore, we created a new function to send the events to the GameAnalytics API.

![GAnalyticsFunction.png](AnalyticsFunction.png)

In specific, we send an Event I'd paired for some optional information, at the moment only for example for a player
picking up or dropping items, starting the game.
There is definitely more to follow, but we wanted to get a basic version up and running to test it.
Now to see the events in the web-panel, we need to start the game and play it for a bit. After that we can open the
section Live Events in the panel, which looks like that.

![LiveEvents.png](LiveEvents.png)

You can see an overview over every event happened that was logged in the game.
To look at one specific event, we took and Item Drop event

![Event.png](Event.png)

There is a lot of information, from the OS the player is playing on till the language and actual event. Looking at the
end of the first line you can see there the event_id which says Item:Drop.
All other events were also successfully logged and can be seen in the web-panel.

## Progress this week

This week we have been mostly working on the main map like classrooms and hallways as well as on implementing voiceChat
for multiplayer.

### Improved Main Map with new Assets

Firstly, there are now many new custom-made assets in the game, which are used to decorate the map. We have added many
new props like tables, chairs, whiteboards and other props to make the map look more like the DHBW.

![assets.png](assets.png)

To improve the map building, walls, floors and ceilings were created in a modular way. This means that the walls, floors
and ceilings are made up of several parts, which can be combined with each other. This allows us to create a more
realistic map and also to create new rooms faster.
Almost all the assets come in 1 meter, 2 meter, 5 meter and 10 meter sizes, so that we can create a room of any size.

![modular_assets.png](modular_assets.png)

Also created were different windows and doors to complete the hallways and rooms.

![modular_assets_2.png](modular_assets_2.png)

These modular assets where used to build parts of the hallway and rooms.

![modular_hallways.png](modular_hallways.png)

![room.png](room.png)

But to create the map even faster, everything was built with `Procedural Content Generation`.
Specific points are created along a spline, which are then replaced with all the assets.
This allows us to make the hallway as long as we want and create everything fast.

![pcg_hallway.png](pcg_hallway.png)

![pcg_room.png](pcg_room.png)

### Starter Room

We also implemented the final version of our starter room, which took up enough time by now. We took inspiration from
some images we took while we were at the DHBW.

In this first image, you can see the area near the elevators, with some posters that resemble the actual area at the
DHBW.

![](Starter-Room-Hallway-Ingame.png)

![](Starter-Room-Hallway.jpg)

While most of the DHBW is modelled as closely as possible, we haven't added a staircase yet, which is why the door
visible in the screenshot below is barely visible.

![](Elevator-Staircase-Ingame.png)

![](Elevator-Staircase.jpg)

### End Room

We also added the door to the balcony and the escape staircase that is present in our reference footage. As we do not
have a Skybox yet, the outside also isn't modelled yet.

![](End-Room-Ingame.png)

![](End-Room-Balcony.jpg)

![](End-Room-Escape-Staircase.jpg)

## Collectable Items

Exam results are now collectable items in the game. They are the main task in the game - Collect all exam results.

![examResults](examResults.png)

All the exam results need to be collected to progress further. Also for every next level, more exam results need to be
collected.

To spawn the exam results, actors are generated from the `PCG`-system. This allows us to spawn the exam results in a
specific area with random rotation and offset while also set the amount of exam results that need to be collected.

## Timer

The timer was implemented to show the time left for the players to finish the game. The timer is displayed at the top of
the screen and counts down from 10 minutes.

![timer](timer.png)

### VoiceChat

To further improve upon the multiplayer aspect, voice chat was introduced. This is currently in its early stages and has
some issues with the audio quality as well as selecting the right audio device.
We use Steam's inbuilt `VOIP`-feature for Unreal Engine, though this has its limitations as mentioned.
## AI Enemy

To make the game more interactive, we have decided to integrate an AI Enemy that follows the player as soon as it sees
him. As long as the player is not in sight, the enemy randomly patrols the game world.
For this behavior, a playable character was first created, which was assigned different movement speeds (e.g. walking
and running). On this basis, an AI opponent was designed that monitors its surroundings using a pawn sensing system. If
the opponent detects the player using this system (e.g. by sight), a reaction chain is triggered.

![AI-Enemy-Event-Graph.png](AI-Enemy-Event-Graph.png)

The underlying logic was implemented entirely using blueprints. Two main behaviors are used:

1. At the beginning, a user-defined “MoveToRandomLocation” event is called in the “BeginPlay” event. This retrieves a
   random location around the opponent via “Get Random Location in Navigable Radius” and transfers it to the “AI MoveTo”
   node, causing the opponent to move to the new position. Once the target is reached, the patrol event is called again,
   creating an infinite loop.
2. When the player is recognized via “On See Pawn”, a sequence is started:
    - First the opponent plays a certain animation (e.g. change to fighting or running stance).
    - Then the movement speed is set to a higher value (e.g. 500) with “Set Max Walk Speed” to initiate the race.
    - This is followed by the “AI MoveTo” command, with which the opponent actively pursues the player.
3. After a delay (e.g. 2 seconds), a reset logic is executed:
    - A new animation is played (e.g. back to idle or normal running).
    - The movement speed is reduced again (e.g. to 250).
    - The opponent is then reset to patrol mode.
      This behavior ensures a dynamic AI that reacts to the player's presence and adapts accordingly. The animations (
      e.g. “Run”, “Idle”, ‘Walk’) are set manually in the blueprint using the “Play Animation” node, depending on the
      situation.
      This combination of random movement, visual recognition and targeted behavior makes the AI appear credible and
      interactive, which noticeably enhances the gameplay.

![AI-Enemy-Model.png](AI-Enemy-Model.png)

## Main Menu

The main menu was till now only there for pure functionality, which is also the main reason for it in any game.
Still we decided to give it a new fresh UI, to make it feel more integrated into the game.
A screenshot of it is shown below.

![mainMenu.png](mainMenu.png)

As you may recognize we took a screenshot of the DHBW App Students use to see their current grades and calendar.
On top of it we reworked the sidebar and added buttons which are used to navigate through the main menu and start a game
should it be singleplayer or multiplayer.
The image above only shows the Main Menu, but every other menu we have ingame was also reworked. It's not necessary to
go through each in detail, but for completeness we will show the other menus below.

We also changed the server list, the create server page to have the same style:

![serverList.png](serverList.png)

![createServer.png](createServer.png)

We also added a menu that shows up when you pause the game:

![ingamePauseMenu.png](ingamePauseMenu.png)

## Time spent

![Timesheet-W4.png](Timesheet-W4.png)