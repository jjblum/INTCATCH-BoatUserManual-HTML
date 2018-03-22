.. _equipment:

Equipment
=========

:ref:`Back to the index <index>`

Boat
----

* hull [ABS plastic, two compartments front and rear, sealed interior mostly filled with foam for buoyancy in case of leaking]
* white housing - pics of the various connectors locations with labels [expands the volume of the front compartment to accommodate GoSys equipment]
* sensor mount
* :ref:`eboard_and_arduino`
* propeller "power pods"  [a modular drive train]
* air fan [a "lazy susan" base that rotates the heading of the fan to create "vectored thrust"]
* router
* cooling pump
* cable harness [bundle of wires that runs between rear and front compartment]
* Platypus sampler  [four parallel sets of tubing, peristaltic pumps, and jars. Controlled with the tablet app]
* GoSys circuitry [main BB board, DO/Relay board, ISA board]
* GoSys sensors [DO, pH, EC, ISA]

.. _eboard_and_arduino:

E-board and Arduino
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


.. _escs:

Electronic Speed Controllers (ESCs)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ESCs control the speed of the boat's motors.
They pull power from the battery according to the signals sent to them by the e-board.
Each motor has its own ESC. The propeller boat has 2 ESCs, and the airboat has 1.
ESCs are found in the rear compartment of the boat.


Phone and Tablet
----------------

* phone
* USB between phone and arduino
* tablet

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`


RC control
----------

* RC transmitter
* RC receiver

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