.. _data:

Data Storage and Visualization
==============================

There are multiple storage locations for the data collected
by the boat during a deployment.

#. The local flash storage on the :ref:`BlueBox<bluebox>`
#. The boat's :ref:`phone<phone_and_tablet>` creates a log file of its location and sensor data it receives
#. BlueGate - The GoSys data gateway receives sensor data via the BlueBox's UMTS (3G) connection
#. WAIS - Water Information System, the INTCATCH project's data gateway, queries the sensor data from BlueGate


BlueGate
--------

This web app (https://bluegate.go-sys.de/) allows the user
to view live data being streamed from a BlueBox or view
a time history of data from various sensors.

There is not a way to manually access location (latitude/longitude)
data, but comma-delimited (csv) files of time-stamped sensor data 
can be exported directly.

WAIS
----

The WAIS database queries (requests) data from BlueGate, 
requiring the following information:

* Sensor Group: represents a BlueBox and the sensors attached to it. The sensor group's username and password are the BlueGate web interface username and password.
* Catchment: the body (or bodies) of water where data is collected
* Campaign: a window of time that defines which data will be requested from BlueGate

During the campaign time window, WAIS will automatically query for new data. 
If BlueGate supplies sensor data and corresponding location data in response to the queries,
the visualization web app (http://demoapp.intcatch.eu) will
automatically create an overlay, displaying data on top of a map
of the catchment. The visualization app can also show a time series of the data.


Phone log
---------

The phone's log is a legacy from the Platypus autonomy software.
Parsing this log is not straightforward, thus it should only be
considered if BlueGate and WAIS are unavailable.

