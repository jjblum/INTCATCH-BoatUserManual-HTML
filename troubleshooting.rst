.. _troubleshooting:

Troubleshooting
===============

.. toctree::
   :maxdepth: 3

:ref:`Back to the index <index>`

* :ref:`boat_will_not_turn_on`
* :ref:`escs_do_not_beep`
* tablet app crashes when you try to connect to boat
* tablet will not connect to the boat
* tablet connects to boat, but does not display battery voltage or other sensor data
* BlueBox will not turn on (maybe wires are loose?)
* :ref:`phone_still_warns_no_bluebox`
* Phone has stopped warning about missing bluebox, but data doesn't appear on tablet
* Arrow representing boat does not appear on the map (phone does not have GPS fix)
* Arrow representing boat does not point in the right direction
* Sensor data parameters disappear from the bottom of the tablet app
* Data is not appearing in WAIS/web app
* boat WiFi never appears
* Don't hear the pump running in the rear compartment
* don't remember password to boat WiFi
* Find water in the rear compartment
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
* Cooling pump makes gurgling noises (air in the system, coolant may have leaked)
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

Each ESC is controlled via a 3-wire cable that connects to the :ref:`e-board <eboard_and_arduino>`.

Make sure that these cables are correctly plugged into the e-board.
First, make sure that the ground, signal, and power wires align with the indicators printed on the e-board.

If you have an airboat, there will only be one 3-wire cable. You will need to plug it into the correct spot.

Once the phone app is running and the phone is plugged into the Arduino, the ESCs should beep low-high.

If the ESCs rapidly beep several beeps the same pitch, 
make sure that you do not have the BlueBox loopback cable (BB-LB) plugged into the RC loopback spot (RC-LB).
Each time the system starts successfully, the ESCs were sent an initial sequence of values to "arm" them.
That sequence of rapid beeping means that the first signal the ESCs received was *NOT* the proper arming sequence.

Tablet will not connect to phone
--------------------------------

* Make sure that the phone and tablet are on the same WiFi network.
* Make sure that you used the correct IP address displayed by the phone.


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

