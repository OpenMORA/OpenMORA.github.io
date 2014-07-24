Demo missions
==========

To start one of the demo missions for a simulated robot, open a console and go to the missions/simulation_one_robot directory. Once there, invoke pAntler with the desired mission file as argument.

For example:
* `pAntler reac_nav_with_gui.moos` - A demo with a 2D simulated robot, MonteCarlo (Particle filter) localization, reactive navigation and a GUI to send navigation commands.
* `pAntler pf_localization_with_gui.moos` - A simpler demo, with a 2D simulated robot, MonteCarlo (Particle filter) localization and Joystick control of the robot.

NOTE: The first time a navigation command is sent to the reactive navigation module, a set of precomputed tables needs to be computed. This can take up to a few minutes for slow machines. During that time, the robot will not navigate, and it's likely that another command should be needed to be issued after the tables are finished (which can be seen from the module output to the console). This will only happen once for each mission file.


