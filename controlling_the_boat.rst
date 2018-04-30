.. _controllingtheboat:

Controlling the Boat
====================

There are three ways to control the boat. 

#. :ref:`manually pilot the boat with the RC control<rc_control>`
#. use the :ref:`tablet control application<using_the_tablet>` to take advantage of autonomous navigation
#. define autonomous triggers to start behavior when specific conditions are fulfilled

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

#. Selecting which boat is currently under control
#. If you have a sampler, control the sampler
#. Manual teleoperation of the boat via a thumbstick
#. Changing the speed of the boat
#. Changing "advanced options"

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
#. Observe the color of the connection status bar

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

Once you have waypoints in place you have three options for generating paths.

#. A chain of straight lines through the waypoints
#. A spiral covering the area surrounded by the waypoints
#. A zig-zig covering the area surrounded by the waypoints

After you generate the path, the estimated path length is displayed on the left side
of the GUI, below the path generation buttons.
This length is measured in meters.

.. _tablet_straight_path:

Chain of straight lines
"""""""""""""""""""""""

This kind of path requires at least 1 waypoint.
The boat will travel in straight lines between each waypoint.

.. _tablet_spiral_path:

Spiral path
"""""""""""

.. _tablet_zigzag_path:

Zig-zag path
""""""""""""

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _tablet_start_pause_stop_waypoints:

Starting, pausing, and stopping autonomous navigation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

asdf

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













.. _rc_control:

RC manual teleoperation
-----------------------

.. _rc_override:

Override
^^^^^^^^

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_override.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

.. _rc_throttle:

Power throttle
^^^^^^^^^^^^^^

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_control_throttle.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

.. _rc_thrust_and_rudder:

Thrust and Rudder
^^^^^^^^^^^^^^^^^

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/rc_control_thrust_and_rudder.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>


* right stick thrust and turn on one stick
* tips for airboat steering

:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`


.. _operating_the_pg_filtering:

Operating the Personal Genomics filtering system
------------------------------------------------

asdf

.. _autonomous_triggers:

Autonomous triggers
-------------------

* set home (default home)
* return home
* default behavior file
* sending new behavior triggers


:ref:`Top of this page <controllingtheboat>`

:ref:`Back to the index <index>`