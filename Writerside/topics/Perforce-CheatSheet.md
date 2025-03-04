# Perforce HelixCore (Work in Progress)

**_At the moment only some notes and a basic structure is added._**

A short guide for all devs to work with Perforce HelixCore.
The guide is based on the official documentation on how to [Maage Files with Helix Core](https://help.perforce.com/helix-core/integrations-plugins/p4vs/current/Content/P4VS/chapter.managing.html).
Its required that you have a setup [server](https://help.perforce.com/helix-core/quickstart/current/Content/quickstart/admin-reference.html) and a [client](https://help.perforce.com/helix-core/quickstart/current/Content/quickstart/end-user-reference.html) to work with.


## Basics

### What are Streams?
Streams are the branches in Perforce.


## P4V Client
P4V is the Perforce Visual Client, which is a GUI for Perforce. It is the easiest way to work with Perforce.

One of the main things to know is that there is a toolbar at the top featuring the most common actions you will need to perform. And beneath the client is divided in an left and right side. 

On the left side you will see the file tree either of an depot or an selected workspace, called **Tree** pane.

While on the right side you can see stuff like the changelist or and Stream Graph. Next to the tab list there is an + icon where views can be added if you missing some.


Its important to know those three areas as they are mentioned in the following steps.

### Add files to Depot

1. In the **Tree** pane, click the Workspace tab.
2. Browse to the file you want to add.
3. Right-click the file and choose Mark for Add. _The file icon displays a red plus sign indicating that it is open for add._
4. To submit the changelist checkout the **Pending ** tab on the right side. Right-click the changelist and choose Submit.
5. Enter a description of the change and click Submit.

The new file is added to the depot.

### Edit files in Depot

Checking out files

### Merging Files

## Unreal Engine 5

How to work with Unreal Engine 5 and Perforce HelixCore.

<warning>
**Submitting and fetching should only be in Perforce and not in Unreal Engine!**
**There are some bugs when using Perforce inside Unreal Engine so if files need to be submitted then firstly save and close Unreal Engine and submit the files via Perforce.**
</warning>

### Setup

Install the newest Version of Unreal Engine from the [Epic games Launcher](https://store.epicgames.com/de/download).

#### New Project

Create a new project. 
After initialisation, click on the button on the lower right called "Revision Control" and then on "Connect to Revision Control". This will open a new window were Perforce needs to be chosen as the provider and then add server, name and workspace. Accept the settings and if correct then Perforce is setup correctly.  

#### Existing Project

If the project was fetched from Perforce then open the .uproject-file and then follow the steps from above.

### Work with files



