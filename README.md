
- - - - -

[http://spaceappschallenge.org/project/ffxii-gambits-for-robotic-automation/](http://spaceappschallenge.org/project/ffxii-gambits-for-robotic-automation/)

- - - - -

Abstract:
=========

Explore the potential use of the Gambit system [1] introduced in Final Fantasy XII [2] as a user interface for rule-based systems for automation of robotic platforms.


Goals:
======

Adapt the Gambit System in Final Fantasy XII (FFXII) as a user interface (UI) for use in autonomous control of robotic platforms.

The ideal situation would be for the UI to be available on any platform (e.g. an HTML5 based app) such that it generates program code to be run directly on the robotics hardware.  Baring that the ruleset can be processed client side sending specific commands to the robotics hardware.


Adaptation:
-----------

The core concept of FFXII's gambit system would remain intact.  There would be an ordered list of rules, each of which could be toggled on or off.  The order of rules can could be changed by dragging a rule into a new position in the list. [3]

The conditionals would be changed to compare sensor readouts to specific values.  The actions would be setting motor speeds or other actuators to specific values, or a more simplified turn left, move forward, etc.  (The latter could take specific units to determine how far to turn or move.)


Expectations:
-------------

Kids would be provided with a set of pre-existing rulesets specific to a robotics platform and tasks or goals to achieve.  Kids could simply run the ruleset on the robot and watch the behavior, or they could toggle certain rules on or off, or rearrange the order of rules and watch how the behavior of the robot changes under the new ruleset.  Time permitting they could create their own rulesets for a more creative learning experience with the robotics platform.


Examples:
--------

Assume a simple robotics platform with a magnetic compass sensor and the ability to turn left or right and move forward or reverse.  Generate a ruleset that checks the compass heading and turns the robot left or right until a desired heading is obtained (e.g. due south).  As long as the compass heading matches the desired heading, move forward.  Adjust the compass heading in the ruleset to a new heading to change the direction of the robot.  (This is a good place to simulate lag time for command updates to reach the robot - the old ruleset will run for some time before the new ruleset is active.)

Assume a variation of the above replacing the magnetic compass sensor with an object detection sensor in the front of the robot.  Generate a ruleset that turns the robot to the right as long as the detection sensor is detecting something.  Otherwise move forward.  Add a rule that is turned off by default that would turn the robot left instead of right.  Kids can switch between the right and left turning rules to switch the robots behavior from a left wall hugging robot to a right wall hugging robot.  Just add some walls or a maze for the robot to explore.


Background:
-----------

Final Fantasy XII introduced the gambit system to allow for simple control over the behavior of party members not under direct control of the player.  The concept was to generate a list of conditions and actions that are checked in order until a condition is met, in which case the action was performed.  The ruleset then starts over checking the conditions.

Rules could be toggled on or off as needed.  Rules could be reordered to prioritize certain actions over others, e.g. heal party members before attacking enemies.

Each rule consisted of a condition, target, and action.  A rule could specify to cast a specific spell on any character (or a specific character) that did not currently have that spell effect on them.  Healing spells could be setup to target a player with a certain percentage of their overall health.  Damaging spells could be targeted at enemies with the most hit points, least hit points remaining, vulnerability to a specific spell effect, etc.  The system turned out to be flexible enough that someone was able to generate a ruleset that when used against a specific rare enemy would generate experience for the party indefinitely without actually killing the rare enemy. [4]


Future Work:
============

Explore the possibility of adapting the Artoo micro-frameworks for robots [5] to interface directly with NXT hardware.  Use that to send commands based on actions generated by the ruleset client-side.


Resources:
==========

1. http://finalfantasy.wikia.com/wiki/Gambits
2. http://en.wikipedia.org/wiki/Final_Fantasy_XII
3. http://finalfantasy.wikia.com/wiki/Gambits?file=FFXII_Gambits.png
4. http://www.gamefaqs.com/ps2/459841-final-fantasy-xii/faqs/45730
5. http://artoo.io/


\#spaceapps #legorovers #FFXII
