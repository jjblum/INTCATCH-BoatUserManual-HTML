.. _equipment:

Equipment
=========

:ref:`Back to the index <index>`

Boat
----

* hull [ABS plastic, two compartments front and rear, sealed interior mostly filled with foam for buoyancy in case of leaking]
* white housing - pics of the various connectors locations with labels [expands the volume of the front compartment to accommodate GoSys equipment]
* sensor mount
* battery
* :ref:`eboard_and_arduino`
* propeller "power pods"  [a modular drive train]
* air fan [a "lazy susan" base that rotates the heading of the fan to create "vectored thrust"]
* :ref:`escs`
* :ref:`cooling_loop`
* router
* cable harness [bundle of wires that runs between rear and front compartment]
* Platypus sampler  [four parallel sets of tubing, peristaltic pumps, and jars. Controlled with the tablet app]
* GoSys circuitry [main BB board, DO/Relay board, ISA board]
* GoSys sensors [DO, pH, EC, ISA]

.. _hull:

Platypus Lutra Hull
^^^^^^^^^^^^^^^^^^^

Unibody, ABS plastic, filled with foam. Drain hole in front.

.. _white_housing:

INTCATCH White Housing
^^^^^^^^^^^^^^^^^^^^^^

Installed on top of front boat compartment, protects the BlueBox circuitry.

.. _lipo_battery:

Lithium Polymer (LiPo) battery
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

4S. xt90 connector.


.. _eboard_and_arduino:

E-board and arduino
^^^^^^^^^^^^^^^^^^^

The "e-board" refers to the Platypus circuit board mounted to the center of the white housing lid.
This circuit board includes an Arduino Due board, and handles all of the control signals into and out of the autonomous boat.
It supplies power to the boat's WiFi router, cooling loop pump, and the phone.
The :ref:`ESCs <escs>` are controlled with the 3-wire cables attached to the e-board.

It is important to note that there are two revisions of the e-board.
Platypus revised their e-board design during the course of INTCATCH, thus both types are used in the first 10 prototype boats.
The older design is larger, uses yellow xt60 connectors, and requires external cables to connect to the BlueBox and RC receiver.
The newer design is smaller, uses only red/black pairs of 45-amp Anderson Power Pole connectors, and uses internal cables to connect to the bluebox and RC receiver.


:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _powerpods:

Power Pods
^^^^^^^^^^

Platypus modular drivetrain

.. _escs:

Electronic Speed Controllers (ESCs)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ESCs control the speed of the boat's motors.
They pull power from the battery according to the signals sent to them by the :ref:`e-board <eboard_and_arduino>`.
Each motor has its own ESC. The propeller boat has 2 ESCs, and the airboat has 1.
ESCs are found in the rear compartment of the boat.

.. _reverse_pair_props:

Left/Right Reverse Pair of Propellers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The propeller with part number that ends in "L", e.g. 2317.51L is a reverse pitch propeller.
It is mounted to the left (port) side drive train.

When the propeller turns, in converts motor torque into forward or backward thrust.
The direction of the pitch determines if the thrust is forward or backward for a clockwise rotation.

A side-effect of a submerged propeller spinning underwater is a reaction torque loading the entire boat hull.
This reaction causes the boat to try to bank to the side.

If the boat used two propellers that had the same pitch (instead of the reverse pair), 
the boat would bank sharply whenever you tried to thrust forward.
But if the boat has a reverse pair, the reaction torque from both propellers cancels each other out, and the boat will drive straight.


.. _cooling_loop:

Cooling Loop
^^^^^^^^^^^^

There is a closed-loop cooling system in the boats, powered by a small pump.
The :ref:`ESCs <escs>` and power pod motors are cooled.
The heat exchanger is the small aluminum tube on the underside of the boat.


.. _wifi_router:

WiFi Router
^^^^^^^^^^^

Ubiquiti bullet.

.. _cable_harness_and_breaker:

Cable Harness and Breaker
^^^^^^^^^^^^^^^^^^^^^^^^^

80 amp breaker




Phone and Tablet
----------------

* phone
* USB between phone and arduino
* tablet

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _rc_equipment:

RC control
----------

.. _rc_transmitter:

FrSky Taranis X9D Plus
^^^^^^^^^^^^^^^^^^^^^^

.. _rc_receiver:

FrSky X8R
^^^^^^^^^

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`


BlueBox and Sensors
-------------------

* Bluebox main circuit board
* power on/off switch
* voltage regulator
* SIM card/modem location
* modem antenna cable
* modem antenna
* USB hub
* USB DB9 cable
* GPS unit
* DO/Relay board
* ISA board
* screen module
* EC sensor
* DO sensor
* ISA sensor
* pH sensor

.. _bluebox:

BlueBox
^^^^^^^

asdf

.. _bluebox_power_switch:

BlueBox power switch
^^^^^^^^^^^^^^^^^^^^

asdf

.. _bluebox_voltage_regulator:

BlueBox voltage regulator
^^^^^^^^^^^^^^^^^^^^^^^^^

asdf

.. 

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`



Platypus water sampler
----------------------

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`


Personal Genomics water filtration
----------------------------------

* stepper motor
* pump head
* filters
* flow sensors

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`