# Comp Player Death
Creates more comp-oriented death messages for better tracking in game.

### Summary
The purpose of CompPlayerDeath (CompPD) is to allow players to track player death information in a way that is clear and easy to reference, so  that this information can be used to make better decisions in a competitive environment. This comes with the following points:
1. The GUI for showing a player death's is clean, easy to read, and uses an appropriate font family, size, and color.
2. The purpose of the GUI is *not* to show who killed a given person. In a competitive environment, this information is not relevant.
3. Player death information is split between "friendly" and "enemy" HUDs. Offense and defense often need to reference friendly and enemy killsfor different purposes. Splitting this information allows players to refrence what they need more quickly.
4. CompPD provides a timer for when a player most recently died. This allows players to track where a given player might be in relation to when they last died. Both offense and defense can use this information for different purposes.
5. Finally, if death information is currently displayed for a given player within a given HUD, and then that person dies again, then e.1) the information associated with the original death will be removed, and e.2) information about the player's most recent death will be added to the bottom of the HUD. In general, a person would not care about the player's previous deaths. They only want to track the most recent death for competitve play.

CompPD is customizable. There are certain settings you can configure in the Scripts tab in the Browser. All other exposed settings can be configured in /prefs/CompPlayerDeathPrefs.cs file.

#### Adding Option to View "Killer"
Very late into script development, I decided to add the option to show the killer of a given player. While that's not the purpose of the script, I can see a person wanting to see this when casually playing. This decision resulting in my creating a Combined Death HUD. If the script is going to allow you to see the killer, then I might as well give you the ability to see both enemy and friendly deaths in the same HUD.

#### Final Notes: Script Structure
1. The functions in the script can definitely be abstracted more. However, assuming that this won't be updated, and assuming that new functionality doesn't need to be added, I found no reason to put time into abstracting functionality for no gain.
2. I still don't fully understand how to manage data within Torque. The data structures available seem to be incredibly limited, and I don't fully understand how script data might be managed between matches. In the end, I had to use individual arrays to track related data for each line. Ideally, I would have used  nested Objects, and I could have used a List to manage the lines. However, it's not clear to me that either are available in Torque. As a result, the number of arrays used to manage each line is truly awful.
3. I find GUI / UI management to also be incredibly confusing. I did my best with this, but I honestly have no idea how to appropriately setup the GUIs / UI.
