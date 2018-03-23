.. _troubleshooting:

Troubleshooting
===============

.. toctree::
   :maxdepth: 3

:ref:`Back to the index <index>`

* :ref:`boat_will_not_turn_on`
* :ref:`escs_do_not_beep`
* :ref:`do_not_hear_pump`
* :ref:`pump_gurgling`
* :ref:`escs_run_hot`
* :ref:`find_water_in_rear`
* :ref:`boat_wifi_never_appears`
* don't remember password to boat WiFi
* :ref:`bluebox_will_not_turn_on`
* :ref:`tablet_will_not_connect_to_phone`
* tablet app crashes when you try to connect to boat
* tablet connects to boat, but does not display battery voltage or other sensor data
* :ref:`phone_still_warns_no_bluebox`
* Phone has stopped warning about missing bluebox, but data doesn't appear on tablet
* Arrow representing boat does not appear on the map (phone does not have GPS fix)
* Arrow representing boat does not point in the right direction
* Sensor data parameters disappear from the bottom of the tablet app
* RC does not work at all
* Airboat fan is extremely loud, yet produces little thrust (backwards)
* The propellers are turning in the wrong direction
* Sensor ___ is not working
* Propeller boat turns in circles (broken prop)
* Propeller boat banks to one side despite trying to drive straight (prop reverse pair not installed correctly)
* LiPo battery is puffy
* Oops, a wire came loose or I damaged ___
* Tablet has lost connection to phone, but RC still works (phone may have crashed, WiFi signal too weak)
* Tablet is connected but boat won't start any waypoints (RC override is probably on)
* The tablet app map and waypoints don't match where the boat actually is
* The tablet app map doesn't show any water (too small)
* The tablet app map doesn't load (forgot to cache it)
* Blueblox data does not appear in WAIS/web app (bluebox may not have GPS fix or SIM card connection)
* Data is not appearing in WAIS/web app
* attached a new type of sensor, don't see it on the tablet, but old types show up on tablet (probably need to update software to handle that type of sensor)


.. _boat_will_not_turn_on:

Boat will not turn on
---------------------

Make sure that the battery :ref:`is plugged in <pluginthebattery>` and :ref:`has been charged <charge_the_battery>`.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`


.. _escs_do_not_beep:

ESCs do not beep low-high when you plug in the phone
----------------------------------------------------

Each :ref:`ESC <escs>` is controlled via a 3-wire cable that connects to the :ref:`e-board <eboard_and_arduino>`.

Make sure that these cables are correctly plugged into the e-board.
First, make sure that the ground, signal, and power wires align with the indicators printed on the e-board.

If you have an airboat, there will only be one 3-wire cable. You will need to plug it into the correct spot.

Once the phone app is running and the phone is plugged into the Arduino, the ESCs should beep low-high.

If the ESCs rapidly beep several beeps the same pitch, 
make sure that you do not have the BlueBox loopback cable (BB-LB) plugged into the RC loopback spot (RC-LB).
Each time the system starts successfully, the ESCs were sent an initial sequence of values to "arm" them.
That sequence of rapid beeping means that the first signal the ESCs received was *NOT* the proper arming sequence.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _do_not_hear_pump:

Cannot hear the cooling pump running in rear compartment
--------------------------------------------------------

The :ref:`pump <cooling_loop>` should turn on as soon as you turn on the :ref:`e-board <eboard_and_arduino>`.

If you don't hear a hum coming from the rear compartment of the boat, the most
likely reason is the pump is not receiving power. 
Check that the pump is plugged in to its cable in the rear compartment, and check
that this cable is connected to the e-board.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _pump_gurgling:

Cooling pump makes gurgling noises
----------------------------------

The hum from the :ref:`pump <cooling_loop>` should be steady.
If you hear gurgling, there is too much air in the system.
You should :ref:`add coolant <filling_the_cooling_loop>`.
Check for coolant leaks.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _escs_run_hot:

ESCs and/or motors are very hot
-------------------------------

The :ref:`cooling loop <cooling_loop>` should maintain reasonable temperatures
for the :ref:`ESCs <escs>` and motors (if you have a prop boat).
If they feel significantly hotter than ambient temperature, make sure that
there is coolant in the loop, the pump is running normally, and that the coolant
is freely flowing through the loop.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _find_water_in_rear:

Water is sitting in the rear compartment
----------------------------------------

There should not be any water in the rear compartment.
If you see any, you should determine if it is :ref:`coolant <cooling_loop>` or a leak.

Ideally the coolant will be colored, so this will be easy to tell.
If not, look at the cooling loop's resevoir. It should be nearly full.
If if it is low, fill it back up and turn on the boat. Look for any coolant leaks.

If you can be sure that there is not a coolant leak, then the water is from a leaky hull.
The most likely location of a small leak is around the base of the aluminum cooling tube's penetrations.
Apply a layer of silicone (or similar) sealant there.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _boat_wifi_never_appears:

Boat's WiFi network does not appear
-----------------------------------

The boat's :ref:`wifi_router` should generate a WiFi network with a name
similar to "Platypus-B1". Once you turn on the :ref:`e-board <eboard_and_arduino>`, you may need to wait
for up to one minute to see the network.
If the network does not appear after one minute, check that the router
is plugged into the ethernet cable in the rear compartment, and check
that that cable is connected to the e-board.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`


.. _bluebox_will_not_turn_on:

BlueBox will not turn on
------------------------

First, make sure that a :ref:`LiPo battery <lipo_battery>` is properly :ref:`plugged in <pluginthebattery>` and :ref:`charged <charge_the_battery>`.

Then, if you flip the :ref:`bluebox_power_switch` on, the :ref:`BlueBox <bluebox>` should turn on.
If it does not, make sure that no wires have become loose.
If all the wires are still in their proper connections, and the BlueBox still does not turn on,
it may have been damaged.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _tablet_will_not_connect_to_phone:

Tablet app will not connect to phone
------------------------------------

Make sure that the phone and tablet are on the same WiFi network.

Make sure that you used the correct IP address displayed at the top of the phone app.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`


.. _tablet_crashes_when_connect_to_boat:

Tablet app crashes when connecting to phone
-------------------------------------------

The tablet application uses the MapBox API for the map.
This API requires that the tablet has an internet connection at least once
before any map tiles can appear.

Because the application cannot load any map tiles at all, it crashes.

The area where the map usually appears will be completely black until the tablet
connects to the internet at least once.

To fix this, simply connect the tablet to the internet and open the application.
The world map should appear, replacing the large black background.
From this point on, the app should work as normal. 
Then an internet connection is only required for :ref:`caching new map tiles <cache_map_tiles>`.

:ref:`Top of this page <troubleshooting>`

:ref:`Back to the index <index>`

.. _phone_still_warns_no_bluebox:

Phone never stops notifications about missing BlueBox data
-------------------------------------------------------------

There are a few reasons why this might happen.

#. The sensor type options in the phone app does not have BlueBox for sensor 2. :ref:`See here <phoneoptions>`
#. The "Set sensor types" button at the bottom of the app was not used after plugging in the phone. :ref:`See here <presssensorsbutton>`
#. One of the cables used in the serial connection between the BlueBox and the eboard arduino is not plugged in correctly.
#. The BlueBox did not recognize the eboard arduino and start sending data to it.

Try using the "Set sensor types" button again. You must press and hold it for about 1 second.
Occasionally, if the user presses the button during a small time window as the next notification is generated,
the command issued by the button is ignored. Try to use the button in between the notifications.

The BlueBox uses udev rules to automatically recognize the eboard's arduino.
Usually these udev rules are used when the BlueBox boots up.
Occasionally, they will not function correctly during boot, so you will need to trigger them again.
You do this by unplugging and replugging the grey USB cable attached to the BlueBox's USB hub.
The hub is on the right (starboard) side of the white housing.

.. raw:: html

   <video width="640" height="480" controls muted> 
     <source src="_static/videos/usb_hub.mp4" type="video/mp4"/>
     Your browser does not support the video tag.
   </video>

:ref:`Top of this page <troubleshooting>`

.. troubleshooting_

:ref:`Back to the index <index>`

