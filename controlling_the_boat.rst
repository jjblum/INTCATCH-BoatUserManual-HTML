.. _controllingtheboat:

Controlling the Boat
====================

There are three ways to control the boat. 

#. :ref:`manually pilot the boat with the RC control<rc_control>`
#. :ref:`use the tablet control application<using_the_tablet>` to take advantage of autonomous navigation
#. :ref:`define autonomous triggers to start behavior when specific conditions are fulfilled<autonomous_triggers>`

While the RC control may seem simple and intuitive, we recommend the use of autonomy whenever possible.
A human operator will still need to intervene from time to time, but the majority of the time
the boat autonomy will be able to perform its tasks better than a human pilot could achieve.

There are two examples that demonstrate this clearly.

First, when covering a large area of calm water, the autonomous navigation can follow a spiral path
that guarantees coverage of the area.
The tablet control application provides the user with progress feedback.
A human pilot would have difficulty tracking where they have already covered, leading to
missed spots and wasteful, redundant sampling in other spots.
If you returned the next day, the human pilot would have difficulty consistently repeating the task,
but the autonomous navigation will happily repeat the same sequence of waypoints over and over.

Second, the airboat design is challenging to manually pilot, even with the RC controller.
It requires predicting where the boat *will* be and counteracting overshoot, actions that
are not intuitive.
An inexperienced pilot will have difficulty achieving a straight line, but the autonomous navigation
will consistently achieve straight lines with an airboat.

.. Third, imagine that you are trying to collect several water samples, where each sample has a
.. different electrical conductivity (EC) value. This would provide information about the relationship
.. between EC and other parameters. To achieve this manually, a user would need to pilot the boat around
.. until they see the EC value they want and start the sampler.
.. Alternatively, the user could define a small number of autonomous triggers, and cover the area
.. with a spiral path. The boat would navigate along its assigned path, and when it encounters the
.. desired EC values it would begin sampling the water automatically.

If the boat can get a GPS fix, and you are not deploying in a narrow, 
swiftly-flowing body of water, let the robot do the work!

.. _using_the_tablet:

Using the Tablet Application
----------------------------

The tablet control application provides the user with
feedback about the state of the boat and provides a 
graphical user interface (GUI) that simplifies controlling
the boat's autonomous navigation.

For simplicity, the control app will be referred to as the "GUI" from here on.

A typical boat deployment will require the following steps:

#. :ref:`Connect the tablet to a boat's IP address<tablet_connect_to_boat>`
#. :ref:`tablet_manipulate_map`
#. :ref:`Add waypoints to the map<tablet_add_waypoints>`
#. :ref:`Generating a path from the waypoints<tablet_generate_paths>`
#. :ref:`Command a boat to begin navigating along the path<tablet_start_pause_stop_waypoints>`
#. :ref:`Observe the status of the boat and sensor data as it navigates<tablet_observing_status>`

The GUI has the following additional capabilities:

#. :ref:`Selecting which boat is currently under control<tablet_boat_selection>`
#. :ref:`Changing the speed of the boat<tablet_change_speed>`
#. :ref:`Manual teleoperation of the boat via a thumbstick<tablet_thumbstick>`
#. :ref:`If you have a sampler, control the sampler<tablet_sampler>`
#. :ref:`Changing "advanced options"<tablet_advanced_options>`

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_general_layout:

General Layout and Map Markers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
 
The largest feature of the GUI is the map. 
The map can be displayed as vector graphics or satellite imagery.

.. image:: _static/images/tablet/plain.jpg
   :alt: the tablet app

There are 4 types markers that are displayed on the map.

#. A colored arrow represents the boat's location and heading.
#. Red location markers represent waypoints
#. Color coded lines represent a path through a set of locations
#. A colored "home" marker represents the boat's home location


.. image:: _static/images/tablet/zoomed_in_markers.jpg
   :alt: map markers

A path that has not been assigned to any boat will be colored white.

A path segment that has been assigned to a boat, and the boat has not completed that segment,
will be share the same color as the boat.

A path segment that has been assigned to a boat, and the boat has finished that segment,
will turn a dark grey. 

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_connect_to_boat:

Connecting to a boat
^^^^^^^^^^^^^^^^^^^^

Connecting to a boat consists of:

#. :ref:`Press the "Connect to boat" button<tablet_connect_button>`
#. :ref:`Enter a boat's IP address into the popup dialog<tablet_enter_ip_address>`
#. :ref:`Observe the color of the connection status bar<tablet_connection_bar>`

.. _tablet_connect_button:

Press the "Connect to boat" button in the top-left corner of the GUI.
This will open a new dialog.

.. image:: _static/images/tablet/connect_to_boat.jpg
   :alt: connect to boat button

.. _tablet_enter_ip_address:

In the new dialog box, type in the boat's IP address.
You do not need to include any port number.
Make sure the "Real boat" option is selected.
Press the "Connect" button.

.. image:: _static/images/tablet/connect_to_boat_dialog.jpg
   :alt: connect to boat dialog

.. _tablet_connection_bar:

Right below the "Connect to boat" button is a colored bar.
The color of this bar represents the connection status.

If the color is red, there is not connection between the tablet and the boat.

If the color is green, the currently selected boat has a working connection to the tablet.

The IP address associated with the currently selected boat is also displayed in the connection bar.

.. image:: _static/images/tablet/ip_address_bar.jpg
   :alt: connection status bar

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_manipulate_map:

Manipulating the map
^^^^^^^^^^^^^^^^^^^^

The GUI's map can be manipulated in a few ways:

#. Change the zoom by a pinching touch
#. Change the location by a dragging touch
#. Change the view elevation with a two-finger vertical dragging touch
#. Centering the map over a boat's current location

Typically, you will have :ref:`cached<cache_map_tiles>` a limited set of map tiles.
The vast majority of map tiles will be blank, making manual navigation to your cached tiles a challenging task.

If the boat has a GPS fix and is connected to the tablet, you can press the "Center"
button to force the map to center on top of the currently selected boat.

.. image:: _static/images/tablet/center_view.jpg
   :alt: center view

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_add_waypoints:

Adding and manipulating waypoints
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Waypoints represent an ordered sequence of locations. 
They are used to generate paths.
The simplest path is just a chain of straight lines through the waypoints,
but they can also be used to generate spirals and zig-zag patterns.

There are three ways to add new waypoints to the map:

#. Long press (~1 second) on the map to add a single waypoint there
#. :ref:`Press the "drop a waypoint" button to add a single waypoint at the boat's current location<tablet_drop_a_waypoint>`
#. :ref:`Load a set of saved waypoints<tablet_saveload_waypoints>`

Once waypoints are present, they can be manipulated in a few ways:

#. :ref:`tablet_undo_waypoint`
#. :ref:`tablet_remove_all_waypoints`
#. :ref:`tablet_move_a_waypoint`
#. :ref:`tablet_flip_waypoints_order`
#. :ref:`Save a set of waypoints <tablet_saveload_waypoints>`

.. _tablet_drop_a_waypoint:

Dropping a waypoint on top of the boat
""""""""""""""""""""""""""""""""""""""

Pressing this button will create a new waypoint at the boat's current location.

This option becomes useful if it is too difficult to accurately place waypoint by hand.

.. image:: _static/images/tablet/drop_waypoint_at_boat.jpg
   :alt: drop waypoint at boat button

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_undo_waypoint:

Remove the last waypoint
""""""""""""""""""""""""

Pressing this button will remove the waypoint with the highest index number.
Unless you have flipped the waypoint order, this will be the most recently created waypoint.

You can continue to press this button, and it will continue to remove the waypoints one at a time.

.. image:: _static/images/tablet/undo_last_waypoint.jpg
   :alt: remove last waypoint button

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_remove_all_waypoints:

Remove all waypoints
""""""""""""""""""""

Pressing this button will remove all the waypoints from the map.

.. image:: _static/images/tablet/remove_all_waypoints.jpg
   :alt: remove all waypoints button

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_move_a_waypoint:

Move a waypoint
"""""""""""""""

To move a waypoint:

#. Tap the waypoint to bring up a the waypoint information box
#. Tap the "move waypoint" button in the dialog
#. Tap the new location on the map

The waypoint information box shows the index number of the waypoint, 
the latitude/longitude coordinates of the waypoint,
and has the "move waypoint" button.

.. image:: _static/images/tablet/waypoint_move.jpg
   :alt: move waypoint button

Pressing this button will let you move the waypoint by tapping on the map.
The waypoint will immediately move to that location.

If you want to move it to a location hidden by the information box,
you will need to first move it to a spot far away.
Then you will be able to move it again, with the desired location not hidden behind the box.

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_flip_waypoints_order:

Reverse waypoints order
"""""""""""""""""""""""

The waypoints are a sequence of locations, starting with location 0, then location 1, and so on.

Pressing this button will reverse the order of the waypoints. 
This will clear any paths that have been generated before reversing the order.

A typical use for this is to manually pilot a boat down a narrow corridor or canal of water,
periodically :ref:`dropping waypoints<tablet_drop_a_waypoint>`.
Then, you can use autonomous navigation on the return trip by reversing the waypoints order
and generating a straight path from the result.
The boat will then autonomously navigation back along the dropped waypoints.

.. image:: _static/images/tablet/flip_waypoint_order.jpg
   :alt: Reverse waypoints order button

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_saveload_waypoints:

Saving and loading sets of waypoints
""""""""""""""""""""""""""""""""""""

You can save sets of waypoints to recall them later. 
This is useful for repeating the same tasks.

Sets of waypoints can be organized by the name of the file they will be written to
and their individual name.

To save a set of waypoints, you must

#. press the "Advanced Options" button in the top-right corner of the GUI
#. press the "Save Waypoints" button
#. choose an existing file or create a new one
#. create a name for the set

To load a set of waypoints, you must

#. press the "Advanced Options" button in the top-right corner of the GUI
#. press the "Load Waypoints" button
#. choose a waypoints file
#. choose a set of waypoints

.. image:: _static/images/tablet/advanced_options.jpg
   :alt: Advanced Options button

.. image:: _static/images/tablet/save_and_load_waypoints.jpg
   :alt: Save and load waypoints buttons

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_generate_paths:

Generating paths from waypoints
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Once you have waypoints in place you have four options for generating paths.

#. A chain of straight lines through the waypoints
#. A spiral covering the area surrounded by the waypoints
#. A zig-zig covering the area surrounded by the waypoints
#. Changing the transect distance for spirals and zig-zag paths

After you generate the path, the estimated path length is displayed on the left side
of the GUI, below the path generation buttons.
This length is measured in meters.

.. image:: _static/images/tablet/generate_paths.jpg
   :alt: Three types of paths

.. image:: _static/images/tablet/path_length.jpg
   :alt: Estimated path length

.. image:: _static/images/tablet/path_types.jpg
   :alt: Types of paths

.. _tablet_straight_path:

Chain of straight lines
"""""""""""""""""""""""

This kind of path requires at least 1 waypoint.
The boat will travel in straight lines between each waypoint.

.. _tablet_spiral_path:

Spiral path
"""""""""""

Instead of traveling directly through the waypoints, we can use them to define a convex polygon.
This polygon represents an area that we want to completely cover with line segments.

This kind of path requires at least 3 waypoints.

A spiral should maximize the time spent traveling forward, efficiently covering the area.

.. _tablet_zigzag_path:

Zig-zag path
""""""""""""

A zig-zag is similar to a spiral, in that we use the waypoints to define an area we want to cover.

Perhaps we want to have parallel lines of data (also called "transects"). 
In that case, use a zig-zag path to travel in parallel East-West lines.

This kind of path requires at least 3 waypoints.

.. _tablet_transect_distance:

Changing transect distance
""""""""""""""""""""""""""

A user can tap on the currently displayed transect distance to change the value.
After typing in a new value, re-generate the path.

This value represents the distance *between* each transect.
If you want to tightly cover an area, use a smaller number.
If you want to loosely cover an area, use a larger number.

Be careful using a small value over a large area! You may overload the tablet's processor.

.. image:: _static/images/tablet/transect_distance.jpg
   :alt: Transect distance


:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_start_pause_stop_waypoints:

Starting, pausing, and stopping autonomous navigation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Once you have a path ready to be assigned to a boat, you can start the autonomous navigation
by pressing the start button. The path will change color to match the boat marker's color.

If you want to pause the autonomous navigation, press the pause button. 
To resume, press the button again.

To stop the autonomous navigation, press the stop button. 
This will also remove the path and waypoints.

.. image:: _static/images/tablet/start_pause_stop.jpg
   :alt: Start, pause, and stop autonomous navigation buttons

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _tablet_observing_status:

Monitoring the status of the boat and sensors
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The GUI displays the following status information:

#. :ref:`The boat's battery voltage<tablet_boat_battery_and_wp_status>`
#. :ref:`The boat's "waypoint status", indicating whether it is currently navigating along a path<tablet_boat_battery_and_wp_status>`
#. :ref:`The boat's progress along its assigned path<tablet_path_progress>`
#. :ref:`Any sensor data the boat is collecting<tablet_sensor_display>`

.. _tablet_boat_battery_and_wp_status:

Boat battery voltage and waypoint status
""""""""""""""""""""""""""""""""""""""""

The boat's battery voltage is displayed in the upper-left corner of the GUI.

The boat's waypoint status is right above the battery voltage.

* If the boat is currently traveling to a waypoint, this will display "GOING"
* If the boat's progress has been paused, this will display "PAUSED"
* If the boat has finished its path, this will display "DONE"
* If the user has stopped autonomous navigation, this will display "CANCELED"

.. image:: _static/images/tablet/boat_status.jpg
   :alt: Boat battery voltage and waypoint status

.. _tablet_path_progress:

Progress along a path
"""""""""""""""""""""

As each segment is completed, the lines change from the color of the boat to dark grey.
This change in color denotes the progress made by the boat along its assigned path.


.. _tablet_sensor_display:

Sensor data
"""""""""""

The sensor data is displayed at the bottom of the map area.

As each new datum is received, the display is updated.
New sources of data will cause the display to expand, accomodating new types of sensors.

Once a parameter has been received and displayed, 
if there is a long delay before the next datum arrives (in particular, more than 10 seconds),
the parameter will disappear from the display.
This prevents stale data from misleading a user.

.. image:: _static/images/tablet/sensor_data.jpg
   :alt: Sensor data


:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_boat_selection:

Selecting the current boat
^^^^^^^^^^^^^^^^^^^^^^^^^^

The GUI can maintain connections to multiple boats at the same time.
All the buttons and commands will be applied to the currently selected boat.

You can switch the currently selected boat by tapping the "Selected boat" pulldown menu and
tapping the boat number. The color shown here will match the boat marker's color.

Selecting a new boat will also update the following, as the tablet starts listening to a new source:

* battery voltage
* waypoint status
* ip address
* connection status
* sensor data

.. image:: _static/images/tablet/selected_boat.jpg
   :alt: Currently selected boat

.. image:: _static/images/tablet/boat_arrows_and_selection.jpg
   :alt: Matching colors

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_change_speed:

Changing the boat's speed
^^^^^^^^^^^^^^^^^^^^^^^^^

There are 4 settings for the speed of the boat:

#. Slow
#. Medium
#. Fast
#. Custom

The first three represent a preset of control parameters that have been tuned for each type of vehicle.
In almost all cases, a user should only use these three settings.
Manual PID tuning should only be done by expert user!

The "Custom" setting uses the manually selected values in the :ref:`Advanced Options -> Preferences menu<tablet_preferences_custom_pids>`.

You select these options by using the pulldown menu on the left of the GUI.

.. image:: _static/images/tablet/boat_speed.jpg
   :alt: Speed selection


:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_thumbstick:

Manually piloting with GUI thumbstick
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You can manually pilot a boat with the thumbstick in the lower right corner of the GUI.

This functions similarly to the :ref:`RC transmitter's right stick<rc_thrust_and_rudder>`,
although it is more difficult to use.

The recommended technique is to place the thumb in the center and *roll* the tip of the thumb.
If you slide your thumb, it is very easy to lose your place and be unable to steer without looking.
By rolling the thumb instead, you always maintain a "home" position for your thumb.

The signal envelope for the thrust and rudder directions can be set in :ref:`Advanced Options -> Preferences menu<tablet_preferences_joystick_range>`.
This is similar to the :ref:`RC transmitter's left stick<rc_throttle>`.

.. image:: _static/images/tablet/thumbstick.jpg
   :alt: GUI thumbstick

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_sampler:

Controlling the Platypus sampler
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The :ref:`sampler<platypus_sampler>` is controlled by the 6 buttons in the lower-left corner of the GUI.

Starting a jar
""""""""""""""

You can start individual jars, stop all jars, and reset the sampler's current jar index.

To start jar, press the corresponding numbered button. 
A timer will appear below the button and start to count down 4 minutes, the time required to fill a jar.

.. image:: _static/images/tablet/start_jars.jpg
   :alt: Start sampler jar buttons

Stopping all jars
"""""""""""""""""

Pressing and holding the stop button for ~ 1 second will cause all jars to stop and clear all currently
executing jar timers. You will need to reset the sampler after doing this.

.. image:: _static/images/tablet/stop_jars.jpg
   :alt: Stop sampler button

Resetting the sampler
"""""""""""""""""""""

The sampler keeps track of which jars have been started.
This prevents a user from accidentally pumping into the same jar twice.
To reset this, press and hold the reset button for ~ 1 second.

.. image:: _static/images/tablet/reset_jars.jpg
   :alt: Reset sampler button


:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_advanced_options:

Advanced Options
^^^^^^^^^^^^^^^^

Pressing the "Advanced Options" button in the upper-right corner of the GUI will
open a popup menu of the following options:

#. :ref:`tablet_vector_vs_satellite_map`
#. :ref:`tablet_set_go_home`
#. :ref:`tablet_send_pids`
#. :ref:`tablet_save_and_load_waypoints`
#. :ref:`tablet_snooze_battery_alarms`
#. :ref:`tablet_set_preferences`
#. :ref:`tablet_construct_and_send_autonomous_triggers`

.. image:: _static/images/tablet/advanced_options_menu.jpg
   :alt: Advanced options menu

.. _tablet_vector_vs_satellite_map:

Switch between vector and satellite maps
""""""""""""""""""""""""""""""""""""""""

These buttons switch the map between using vector graphics or satellite imagery.

.. image:: _static/images/tablet/satellite_vector_map.jpg
   :alt: Vector and Satellite map selection

.. _tablet_set_go_home:

Set boat home and go home
"""""""""""""""""""""""""

After pressing the "Set Home" button, tapping on the map will set the boat's home location to that location.

Pressing the "Go Home" button will cause the boat to backtrack along the locations it has been, 
returning to its home location.
The boat uses the A\* algorithm to plan its path through the locations it has previously visited.

There is a default home location, so a user does not always have to set the home manually.
When the boat receives its first autonomous navigation command, it sets its home to its current location.

.. image:: _static/images/tablet/set_and_go_home.jpg
   :alt: Set and go home buttons

.. _tablet_send_pids:

Manually send PID values
""""""""""""""""""""""""

Pressing this button will resend the PID values associated with the 
:ref:`currently selected boat speed option<tablet_change_speed>`.

.. image:: _static/images/tablet/send_pids.jpg
   :alt: Send PIDs button

.. _tablet_save_and_load_waypoints:

Save and load sets of waypoints
"""""""""""""""""""""""""""""""

See :ref:`here<tablet_saveload_waypoints>`.

.. _tablet_snooze_battery_alarms:

Snooze battery alarms
"""""""""""""""""""""

The GUI will trigger two levels of warnings depending on the current battery level and the alarm
preferences specified in the :ref:`preferences<tablet_preferences_battery_alarm_settings>`.

Pressing this button will snooze the alarms (prevent them from occurring) for a fixed duration of time.
You should only use this if you are keeping a close eye on the battery levels!

.. image:: _static/images/tablet/snooze_alarms.jpg
   :alt: Snooze alarms button

.. _tablet_set_preferences:

Set preferences
"""""""""""""""

Pressing this button will open up another screen with several optional settings

.. image:: _static/images/tablet/preferences.jpg
   :alt: Preferences button

Aside from the vehicle type setting, these options are usually left at their default values.
Only expert users should change preferences other than vehicle type!

The following options can be changed:

#. :ref:`Vehicle type<tablet_preferences_vehicle_type>`
#. :ref:`Joystick range<tablet_preferences_vehicle_type>`
#. :ref:`Custom PID values<tablet_preferences_custom_pids>`
#. :ref:`Battery alarm settings<tablet_preferences_battery_alarm_settings>`

.. _tablet_preferences_vehicle_type:

Preferences: vehicle type
"""""""""""""""""""""""""

This option lets the user select either propboat or airboat.
The only effect this will have is to change the PID values associated with the default
slow, medium, and fast speed settings.

.. image:: _static/images/tablet/preferences_vehicle_type.jpg
   :alt: Preferences: vehicle type

.. _tablet_preferences_joystick_range:

Preferences: joystick range
"""""""""""""""""""""""""""

A user can change the maximum and minimum values for the thrust and rudder directions of the thumbstick.

The default minimum values are -1.0 and 1.0 for both thrust and rudder.

If you change the thrust min and max values to -0.5 and 0.5 respectively,
pushing the thumbstick all the way forward will result in only half thrust.

Do *not* forget the negative sign in front of the minimum, or the boat will only be able to thrust forward.

.. image:: _static/images/tablet/preferences_joystick_range.jpg
   :alt: Preferences: joystick range

.. _tablet_preferences_custom_pids:

Preferences: custom PID values
""""""""""""""""""""""""""""""

An expert user can change the PID values associated with the "Custom" speed setting.

.. image:: _static/images/tablet/preferences_custom_pids.jpg
   :alt: Preferences: custom PID values

.. _tablet_preferences_battery_alarm_settings:

Preferences: battery alarm settings
"""""""""""""""""""""""""""""""""""

These options allow an expert user to select the voltage levels that trigger warnings and alarms in the GUI.

.. image:: _static/images/tablet/preferences_battery_warnings.jpg
   :alt: Preferences: battery alarm settings


.. _tablet_construct_and_send_autonomous_triggers:

Construct and send new autonomous triggers
""""""""""""""""""""""""""""""""""""""""""

Pressing this button will open up another screen. This screen is currently under construction.

Once completed, it will provide a user interface to construct and send 
new :ref:`autonomous triggers<autonomous_triggers>` to the boat.

Until this is completed, the user should press the back button to return to the main GUI.

.. image:: _static/images/tablet/autonomy.jpg
   :alt: Autonomy construction button

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`



.. _rc_control:

RC manual teleoperation
-----------------------

The radio control (RC) equipment provides an easier method for
manually steering the boat.
The large, tactile controls are easier to use than the tablet app's thumbstick.

.. _rc_override:

Override
^^^^^^^^

Flipping the override switch will cause the :ref:`arduino<eboard_and_arduino>` to
ignore commands coming from the autonomous navigation, and instead only respond to
further RC control signals.

The phone app will continue to send autonomous navigation signals to the arduino, but they are temporarily ignored. 
For example, lets say the boat is performing a large spiral path, but a fishing boat is in the way.
You can turn the override on, manually pilot the boat around the fishing boat, turn the
override off again, and the boat will autonomously return to its original path.

Currently, the only way to turn off the override is to flip the switch back to off.
Turning the RC transmitter off does *NOT* turn off the override! 
If you leave the override on and turn off the transmitter, the override will remain on.

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_override.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

.. _rc_throttle:

Power throttle
^^^^^^^^^^^^^^

The left stick of the RC transmitter acts as a power envelope - the value of the left stick
represents the maximum value that the right stick thrust can achieve.

This is useful if you want to cruise at a fixed speed that is less than maximum.
Instead of trying to hold the right stick somewhere in between zero and maximum,
simple set the left stick to the cruising speed and hold the right stick at maximum.

Currently, *only the thrust is affected*! The rudder signals are not throttled.

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_control_throttle.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

.. _rc_thrust_and_rudder:

Thrust and Rudder
^^^^^^^^^^^^^^^^^

The right stick controls both the thrust (forward and backward) and rudder (left and right).

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_control_thrust_and_rudder.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

.. _rc_tips:

Tips for RC control
^^^^^^^^^^^^^^^^^^^

Propboat tips
"""""""""""""

The throttle only reduces maximum forward thrust. 
The throttle does not change the power generated when turning.
Thus, you should be gentle with the left and right motion of the right stick.

Airboat tips
""""""""""""

The airboat is much harder to steer, as it tends to "drift" more than the propboat.

Imagine turning the airboat in place. 
As you let go of the thrust stick, the airfan stops producing thrust, but the boat continues spinning.
If you keep up the thrust for too long, the boat will drift past the direction you wanted.

To hit the direction you want, you actually need to angle the fan assembly the *opposite direction*
of your turn and give a burst of thrust, acting against the turn's momentum, as you near the desired direction.

To drive in a straight line, you must predict when small instabilities will result in the boat
drifting into a spin, and gently provide thrust in the opposite direction.
Consistently driving in straight lines with an airboat will require practice!





:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`

.. _autonomous_triggers:

Autonomous triggers
-------------------

Autonomous triggers allow the autonomous boat to perform actions once a set of conditions has been fulfilled.

This logic-action pair is referred to as a "behavior".
Each behavior is defined by five things:

#. A unique name
#. The action to be performed once the conditions are met
#. A boolean (True/False) condition requirement, called the "trigger"
#. The frequency that the trigger is checked for a True/False value
#. If the behavior is retained or abandoned after the action is performed

A behavior's definition is stored in a JSON format that the phone server application parses.

For example, here is the definition for a behavior named "inacitivty_return_home"::

	inactivity_return_home:
	{
		action: return_home,
		trigger: "^(is_autonomous) & time_since_operator > 60000",
		interval: 1000,
		ends: n
	}

In this example, we want the boat to automatically return home if it has not received any signals from a human
operator in 60 seconds and it is not autonomously navigating to any waypoints (i.e. it is sitting idle).

The string "return_home" is one of a limited set of strings that name *actions* that the boat can perform.

The strings "is_autonomous" and "time_since_operator" are two 
of a limited set of strings that name *states* that the boat can take on.

A table of all current actions, states, and their identifying strings will follow below.

The "interval" value is the number of milliseconds between each time the trigger boolean is evaluated as True or False.

The "ends" yes/no value specifies if we continue checking the trigger and possibly performing the action again (ends = no),
or if we abandon the behavior after the action is performed once (ends = yes).

Possible actions and their identifying strings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------------------+--------------------------------------------+
| String                       |   Action                                   |
+==============================+============================================+
| return_home                  | Navigate to home location                  |
+------------------------------+--------------------------------------------+
| start_sampler                | Begin filling lowest available jar         |
+------------------------------+--------------------------------------------+
| sampler_stop                 | Stop filling any jars                      |
+------------------------------+--------------------------------------------+
| sampler_reset                | Reset the status of the sampler jars       |
+------------------------------+--------------------------------------------+

This list can be expanded by updating the phone app to include new actions.

Possible states and their identifying strings
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

+------------------------------+----------------------------------------------------------+
| String                       |   State                                                  |
+==============================+==========================================================+
| EC                           | Electrical conductivity                                  |
+------------------------------+----------------------------------------------------------+
| DO                           | Dissolved Oxygen                                         |
+------------------------------+----------------------------------------------------------+
| T                            | Temperature                                              |
+------------------------------+----------------------------------------------------------+
| PH                           | pH                                                       |
+------------------------------+----------------------------------------------------------+
| GPS @ [X, Y]                 | Boat is within 3 meters of latitude,longitude = X, Y     |
+------------------------------+----------------------------------------------------------+
| elapsed_time                 | milliseconds since the phone app started                 |
+------------------------------+----------------------------------------------------------+
| time_since_operator          | milliseconds since the last operator heartbeat           |
+------------------------------+----------------------------------------------------------+
| battery_voltage              | boat battery voltage                                     |
+------------------------------+----------------------------------------------------------+
| is_connected                 | True if the boat is connected to the tablet              |
+------------------------------+----------------------------------------------------------+
| is_autonomous                | True if the boat is currently navigating autonomously    |
+------------------------------+----------------------------------------------------------+
| has_first_autonomy           | True if the boat has navigated autonomously at least once|
+------------------------------+----------------------------------------------------------+
| is_going_home                | True if the boat is currently going home                 |
+------------------------------+----------------------------------------------------------+
| is_taking_sample             | True if the sampler is currently gathering a sample      |
+------------------------------+----------------------------------------------------------+
| jars_available               | True if the sampler still has open jars                  |
+------------------------------+----------------------------------------------------------+

This list can be expanded by updating the phone app to include new states.

Boolean strings
^^^^^^^^^^^^^^^

The trigger definition format supports compound boolean sentences.

The following table lists the boolean symbols that can be used to construct boolean sentences.

+------------------------------+----------------------------------------------------------+
| String                       |   Boolean definition                                     |
+==============================+==========================================================+
| X < Y                        | True when X is less than Y                               |
+------------------------------+----------------------------------------------------------+
| X <= Y                       | True when X is less than or equal to Y                   |
+------------------------------+----------------------------------------------------------+
| X > Y                        | True when X is greater than Y                            |
+------------------------------+----------------------------------------------------------+
| X >= Y                       | True when X is greater than or equal to Y                |
+------------------------------+----------------------------------------------------------+
| X == Y                       | True when X is equal to Y                                |
+------------------------------+----------------------------------------------------------+
| X : [Y, Z]                   | True when X is within the closed interval [Y, Z].        |
|                              | Equivalent to (X <= Z & X >= Y)                          |
+------------------------------+----------------------------------------------------------+
| ^(X)                         | True when X is False. Boolean negation.                  |
+------------------------------+----------------------------------------------------------+
| X & Y                        | True when X and Y are both True                          |
+------------------------------+----------------------------------------------------------+
| X | Y                        | True when either X or Y is True                          |
+------------------------------+----------------------------------------------------------+

Example behavior definitions
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Lets say you want to fill a sampler jar at a specific location (45.403863, 10.999423), but only if the electrical
conducitivy value is within a certain interval (400, 600)::

	{
		action: start_sampler,
		trigger: "GPS @ [45.403863, 10.999423] & EC : [400, 600]",
		interval: 1000,
		ends: y
	}

With this definition, once per second the phone app will check the following conditions:

#. if the distance from its current location to (45.403863, 10.999423) is less than 3 meters
#. if the current EC value is >= 400
#. if the current EC value is <= 600

If *all 3* conditions are met, the boat will start pumping water into a sampler jar.

Default behavior file
^^^^^^^^^^^^^^^^^^^^^

When the phone app is started, it searches for a file "default_behaviors.txt" in the phone's
"platypus_behaviors" folder.

If this file exists, any JSON behavior definitions in it are parsed and begin to execute.

If you always want a behavior to exist, include a definition in the file.


Sending new behaviors
^^^^^^^^^^^^^^^^^^^^^

This capability is being developed. 
Currently, only the default behaviors file can be used.


.. _operating_the_pg_filtering:

Operating the Personal Genomics filtering system
------------------------------------------------

asdf




:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`