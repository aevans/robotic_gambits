
System Architecture
===================

User Interface
--------------

The User Interface (UI) for working with rulesets should be isolated from specific robotics platforms and any command and control software used for communications.  This allows rulesets to be applied to a larger variety of platforms, including virtual simulations.  It also allows for easier modifications, collaborative edits, and sharing via exporting the ruleset to a common format.

Robotics Platforms
------------------

For any robotics platform that is capable of storing and processing a ruleset or other program code locally, the common ruleset format can be converted into a format specific to that platform.  Ruleset conversion and upload to the robotics platform will still need to be considered.

Communications and Controls
---------------------------

For any robotics platform that is remotely controlled by an additional piece of software running on another device, the common ruleset can be processed and converted into commands that can be transmitted to the platform through any available communications process.  It may be possible to integrate the UI with an existing client software, but ideally it would still support the common ruleset format.

Customizations
--------------

Different robotics platforms or simulations are likely to have different sets of inputs (sensors) and outputs (motor controls, lights and sounds).  Information that defines the set of useable inputs and outputs and appropriate data formats for different platforms can be extracted from the UI and platform and shared in another common format.  This allows for easy customization of available options by platform capabilities, or to limit available options to focus on specific educational tasks.

Time-lag
--------

Time-lag can be simulated at a variety of different points.  Sending a new ruleset to a far away robotics platform can take into account communication latency such that the new ruleset will not become active until it has had time to be sent to the platform.  Updating a specific rule may also take time before the platform can begin using it.  For remote platforms controlled by local devices, reading sensor data or updating motor controls can cause ruleset evaluation to run slower than if it were running directly on the platform.
