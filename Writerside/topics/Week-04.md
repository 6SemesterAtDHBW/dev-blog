# Week 04

## Progress this week

[//]: # (TODO add progress info)

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
- Facial Expression Analysis (Using webcam-based AI to detect expressions related to fear, surprise, or stress during intense gameplay moments)
- Voice Stress Analysis (Evaluating voice pitch and tremors during player communication to determine emotional states)
- Muscle Tension Detection (Capturing involuntary muscle reactions, particularly in the face and hands, to detect subconscious fear responses)

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

##  Data Protection and Ethical Considerations
- Anonymization of data to protect privacy
- Player consent for data collection in accordance with GDPR
- Transparency by providing access rights to players


### Final Implementation

So above we made a big concept of what is possible what would be an optimal soluton for our game.
Still we needed to first implement a basic version of the game analytics, before we go into detail.
For that we looked out for solutions and there were a lot, especially if you are willing to pay. 
But we preffered a free solution, that isnt the default Unreal Engine 5 Insights, which are good, but lack some functionalities.
So we decided for GameAnalytics.com,  is free for small teams and was quite easy to integrate.
Right of the box, it offers a lot of functionalities, like it shows the current users playing, sending errors to it and so one.
That all is visible in a webpanel, that looks like this:

![GameAnalyticsWebPanel.png](GameAnalyticsWebPanel.png)

In that example we only have an example of some stats, in specific, the Realtime Stats of our game.
Next up we decided to log some events, getting information about how the player interacts while playing the game.
Therefore we created a new function to send the events to the GameAnalytics API.

![GAnalyticsFunction.png](AnalyticsFunction.png)

In specific we send an Event Id paired for some optional informations, at the moment only for example for an player picking up or dropping items, starting the game.
There is defintly more to follow but we wanted to get a basic version up and running to test it.

Now to see the events in the webpanel, we need to start the game and play it for a bit. After that we can open the section Live Events in the panel, which looks like that.

![LiveEvents.png](LiveEvents.png)

You can see an overview over every event happend that was logged in the game.
To look at one specific event, we took and Item Drop event

![Event.png](Event.png)
There are a lot of information, from the OS the player is playing on till the language and actuall event. Looking at the end of the first line you can see there the event_id which says Item:Drop.
All other events where also successfully logged and can be seen in the webpanel.


## Time spent

[//]: # (TODO insert timesheet) 