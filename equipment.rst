.. _equipment:

Equipment
=========

:ref:`Back to the index <index>`

* :ref:`boat`
* :ref:`rc_equipment`
* :ref:`phone_and_tablet`
* :ref:`bluebox_and_sensors`
* :ref:`platypus_sampler`

.. * :ref:`personal_genomics`

.. _boat:

Boat
----

* :ref:`hull`
* :ref:`white_housing`
* :ref:`sensor_mount`
* :ref:`lipo_battery`
* :ref:`eboard_and_arduino`
* :ref:`power_pods`
* :ref:`reverse_pair_props`
* :ref:`air_fan`
* :ref:`escs`
* :ref:`cooling_loop`
* :ref:`wifi_router`
* :ref:`cable_harness_and_breaker`

.. _hull:

Platypus Lutra Hull
^^^^^^^^^^^^^^^^^^^

The Platypus Lutra platform was designed with a focus on affordability,
while still providing autonomous capability.

The hull is:

* A unibody design with two compartments
* Formed from tough ABS plastic
* Approximately 1 m length x 0.5 m width
* Filled with flotation foam, minimizing the impact of a hull leak
* Light enough to carry under-arm

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _white_housing:

INTCATCH Expansion Housing
^^^^^^^^^^^^^^^^^^^^^^^^^^

The INTCATCH project adds a variety of sensors to the platform, 
and incorporates a cloud data gateway
in the form of GO Systemelektronik GmbH BlueBox system.

An extra housing was designed to accommodate the additional electronics 
required for this integration.
Nicknamed the "white housing", it is installed on top of front boat compartment,
replacing the acrylic plate used in the base Platypus product.

.. image:: _static/images/white_housing.jpg
   :alt: white housing
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _sensor_mount:

INTCATCH Sensor Mounting Frame
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

This two-piece frame allows the sensors to be mounted to the underside of the boat.
The bottom piece can be removed, allowing direct access to the sensor probes.

.. image:: _static/images/sensor_mount.jpg
   :alt: sensor mount
   :height: 480px
   :align: center   

.. image:: _static/images/sensor_mount_plate.jpg
   :alt: sensor mount plate
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _lipo_battery:

Lithium Polymer (LiPo) battery
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The boat can draw over 60 amps of current, so it can be very power hungry.
A LiPo battery provides the energy density and maximum current draw necessary to operate the boat.
The battery is held in the front compartment.

The boat can accept both 3S (3 cells) and 4S (4 cells), 
as long as it uses an XT-90 connector.

The most commonly used battery is the Turnigy Multistar 4S, 16 Ah, 10C battery.

.. image:: _static/images/battery.jpg
   :alt: battery
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _eboard_and_arduino:

E-board and Arduino
^^^^^^^^^^^^^^^^^^^

The "e-board" refers to the Platypus circuit board mounted to the center of the white housing lid.

This circuit board includes an Arduino Due board, 
and handles all of the control signals into and out of the autonomous boat.
It also supplies power to the boat's WiFi router, cooling loop pump, and the phone.
The :ref:`ESCs <escs>` are controlled with the 3-wire cables attached to the e-board.

.. image:: _static/images/eboard.jpg
   :alt: eboard
   :height: 480px
   :align: center   

It is important to note that there are two revisions of the e-board.
Platypus revised their e-board design during the course of INTCATCH, 
thus both types are used in the first 10 prototype boats.

The older design is larger, uses yellow XT60 connectors, and requires external cables to connect to the BlueBox and RC receiver.

The newer design is smaller, uses only red/black pairs of 45-amp Anderson Power Pole connectors, and uses internal cables to connect to the bluebox and RC receiver.

.. image:: _static/images/eboard_old_vs_new.jpg
   :alt: old and new e-boards
   :height: 480px
   :align: center   


:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _power_pods:

Power Pods
^^^^^^^^^^

This term refers to the Platypus modular drivetrain in the rear compartment of propeller boats.
There are two frames that mount a motor, simple gearing, drive-shaft, and stuffing tube.
They are in turn mounted to the floor of the rear compartment.

.. image:: _static/images/powerpods.jpg
   :alt: power pods
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _escs:

Electronic Speed Controllers (ESCs)
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

ESCs control the speed of the boat's motors.
They pull power from the battery according to the signals sent to them by the :ref:`e-board <eboard_and_arduino>`.
Each motor has its own ESC. The propeller boat has 2 ESCs, and the airboat has 1.
ESCs are found in the rear compartment of the boat.

.. image:: _static/images/escs.jpg
   :alt: ESCs
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _reverse_pair_props:

Left/Right Reverse Pair of Propellers
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

When the propeller turns, in converts motor torque into forward or backward thrust.
The direction of the pitch determines if the thrust is forward or backward for a clockwise rotation.

A side-effect of a submerged propeller spinning underwater is a reaction torque loading the entire boat hull.
This reaction causes the boat to try to bank to the side.

If the boat used two propellers that had the same pitch (instead of the reverse pair), 
the boat would bank sharply whenever you tried to thrust forward.
But if the boat has a reverse pair, the reaction torque from both propellers cancels each other out, and the boat will drive straight.

The most commonly used propeller is the Graupner 45 mm diameter prop.

The propeller with part number that ends in "L", e.g. 2317.45L is a reverse pitch propeller.
It is mounted to the left (port) side drive train.

.. image:: _static/images/reverse_prop_pair.jpg
   :alt: reverse propeller pair
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _air_fan:

Airfan Assembly
^^^^^^^^^^^^^^^

The Platypus airfan uses a 10-inch diameter propeller and a 
Great Planes Rimfire .15 motor.

The fan rotates on a lazy-susan bearing, with a small servo powering this rotation.
The extra cable that must be plugged into the :ref:`e-board<eboard_and_arduino>` controls this servo.

This rotating fan generates "vectored" thrust.
Depending on the angle of rotation, the thrust will be split between
forward/backward and port/starboard.

.. image:: _static/images/airfan_assembly.jpg
   :alt: airfan assembly
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _cooling_loop:

Cooling Loop
^^^^^^^^^^^^

There is a closed-loop cooling system in the boats, powered by a small pump.

The :ref:`ESCs <escs>` and :ref:`power pod<power_pods>` motors are cooled.

The heat exchanger is the small aluminum tube on the underside of the boat.

The small plastic bottle in the rear compartment is the cooling fluid resevoir.

.. image:: _static/images/pump.jpg
   :alt: cooling loop pump
   :height: 480px
   :align: center   

.. image:: _static/images/resevoir.jpg
   :alt: cooling loop reservoir
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _wifi_router:

WiFi Router
^^^^^^^^^^^

Each boat contains a WiFi router that generates a network that allows 
the phone and tablet to connect.

The most commonly used router is the Ubiquiti bullet.

.. image:: _static/images/router.jpg
   :alt: WiFi router
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _cable_harness_and_breaker:

Cable Harness and Breaker
^^^^^^^^^^^^^^^^^^^^^^^^^

The cable harness refers to the bundle of cables that run between 
the rear and front compartments in the boat.
The battery plugs into the large, yellow XT90 connector.

The 80 amp breaker is an important part of the harness.
This breaker will open if more than 80 amps is drawn through the harness.
The :ref:`ESCs <escs>` are not meant to draw more than 80 amps.

.. image:: _static/images/breaker.jpg
   :alt: circuit breaker
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _phone_and_tablet:

Phone and Tablet
----------------

The phone must be an Android phone, with Android 7.0 or newer. 
It must also have a gyroscope, accelerometer, compass, GPS, and modern WiFi connectivity.
The typical phone is a Nexus 5X. 
It has a USB-C port.

The tablet must be an Android tablet, with Android 6.0 or newer. 
A 10 inch screen is preferred. 
The ASUS ZenPad 10 is a good example.

.. _rc_equipment:

RC Equipment
------------

The radio control (RC) equipment provides an easier method for
manually steering the boat.
The large, tactile controls are easier to use than the tablet app's thumbstick.

A user can switch back and forth between autonomy and manual steering with a single switch.

It also provides a dead-stop switch that can be used to cut off
autonomous navigation. 

The RC is independent of the WiFi connection used between
the boat's phone and the tablet. It provides redundancy - if the
WiFi or phone fails, the user can still control the boat via the RC.

.. _rc_transmitter:

FrSky Taranis X9D Plus
^^^^^^^^^^^^^^^^^^^^^^

This transmitter has 16 channels, uses the SBUS protocol, and has model matching.

"Model matching" refers to being able bind specific receivers to a unique "model".

This allows you to switch between different receivers on the fly.
While you can still only control one boat at a time, you can easily switch
between them as long as you have bound the receivers to a unique model in the transmitter.

.. image:: _static/images/rc_transmitter.jpg
   :alt: RC transmitter
   :height: 480px
   :align: center   

.. _rc_receiver:

FrSky X8R
^^^^^^^^^

This receiver comes with its own integrated antennas.

.. image:: _static/images/rc_receiver.jpg
   :alt: RC receiver
   :height: 480px
   :align: center   

.. _sbus_inversion_cable:

SBUS Inversion Cable
^^^^^^^^^^^^^^^^^^^^

The SBUS protocol must pass through a circuit that translates it
into a form that the :ref:`e-board's arduino<eboard_and_arduino>` can use.

This circuit is integrated into the cable connecting the receiver to the arduino.

.. image:: _static/images/rc_sbus_inversion_cable.jpg
   :alt: SBUS inversion cable
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _bluebox_and_sensors:

BlueBox and Sensors
-------------------

.. _bluebox:

BlueBox
^^^^^^^

The BlueBox is a modular and scalable system to manage large
numbers of sensors and actuators. It handles data storage,
wired and wireless transmission of data, and sensor calibration.

More details on the BlueBox system and associated equipment can
be found at https://www.go-sys.de/en/bluebox/.

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _bluebox_power:

BlueBox power switch and voltage regulator
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The BlueBox requires a steady 24 V DC current. 
The voltage provided by the lithium polymer (LiPo) battery used 
by the boat varies from over 16 V down to below 14 V. 
To provide a steady 24V input, a voltage regulator is installed 
between the LiPo battery and the main BlueBox board’s power input.

A simple two-position DC switch is used to allow the BlueBox 
and the rest of the boat to be powered on separately. 

The battery’s ground serves as the common ground for the Platypus
e-board, the main BlueBox circuit board, and the DO/pH/relay circuit board. 
The DO and pH sensors’ raw readings are voltage measurements 
that could be biased by a “floating ground”, 
thus this common ground was critical for accurate measurements.

The DO/pH/relay and ISA circuit boards receive power via their CAN-bus 
interface with the BlueBox circuit board.

.. image:: _static/images/bluebox_switch_and_regulator.jpg
   :alt: BlueBox switch and regulator
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. _bluebox_sensors:

BlueBox sensors
^^^^^^^^^^^^^^^

The boat is typically equipped with a pH sensor, 
a dissolved oxygen sensor, and an electrical conducitivty sensor.

* pH: https://www.go-sys.de/en/products/sensors/ph-electrode-swimming_pool/
* DO: https://www.go-sys.de/en/products/sensors/oxygen-and-temperature-sensor-submersible/
* EC: https://www.go-sys.de/en/products/sensors/conductivity-temperature-immersion-sensor-small/

.. _bluebox_gps:

BlueBox GPS receiver
^^^^^^^^^^^^^^^^^^^^

The BlueBox utilizes its own GPS receiver. 
This receiver connects to the BlueBox's USB hub and is
typically mounted to the lid of the boat.

.. image:: _static/images/bluebox_gps.jpg
   :alt: BlueBox GPS receiver
   :height: 480px
   :align: center   

:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`



.. _platypus_sampler:

Platypus Sampler
----------------

This device allows the boat to collect jars of surface water.
It is mounted on top of the rear plate, thus it can only be used
with a special rear plate and a propeller boat.

* There are four jars.
* Each jar holds 500 mL (for a total of 2 L), and each jar is fitted with its own tubing.
* Each tube is installed on its own peristaltic pump.
* It takes approximately 4 minutes to fill a jar.

The jars can be individually :ref:`activated with the tablet<tablet_sampler>` 
or :ref:`triggered autonomously<autonomous_behaviors>`.

.. image:: _static/images/sampler.jpg
   :alt: sampler
   :height: 480px
   :align: center   


:ref:`Top of this page <equipment>`

:ref:`Back to the index <index>`

.. .. _personal_genomics:

.. Personal Genomics Water Filtration
.. ----------------------------------

.. * stepper motor
.. * pump head
.. * filters
.. * flow sensors

.. :ref:`Top of this page <equipment>`

.. :ref:`Back to the index <index>`