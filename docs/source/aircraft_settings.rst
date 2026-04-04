Aircraft Management
######################

The aircraft managment sections is to create, store, load, and manage aircraft profiles using their registration, enabling quick switching between aircraft configurations.
In Skywalk, these profiles are used throughout the app to automatically populate performance, weight, and fuel calculations for flight planning.
This section contains in total 9 expanders. All expanders are related to one specific aircraft.

.. |figT2A| image:: ../figs/aircraft_settings.png
   :scale: 50%

.. table::
   :align: center

   +----------+
   | |figT2A| |
   +----------+


Import Registered Aircraft
#############################
This section allows you to import predefined aircraft configurations and save them into your own list for reuse.
In Skywalk, this speeds up setup by avoiding manual entry and ensures consistency when working with commonly used aircraft.


Personal Specifications
#############################

This section defines standard passenger and baggage weights used during flight planning to reduce repetitive input and improve consistency.
In Skywalk, these values are automatically applied in the weight and balance calculations and can be adjusted per flight if needed.


.. |figT2B| image:: ../figs/personal_specifications.png
   :scale: 50%

.. table::
   :align: center

   +----------+
   | |figT2B| |
   +----------+

Aircraft Specifications
#############################
This section defines the aircraft’s loading configuration by specifying arms, weights, and computed moments for each station, allowing calculation of the center of gravity (CG).
In Skywalk, this is used in real-time to calculate total weight, total moment, and takeoff CG, ensuring the aircraft remains within safe operational limits.

.. |figT2C| image:: ../figs/aircraft_specifications.png
   :scale: 50%

.. table::
   :align: center

   +----------+
   | |figT2C| |
   +----------+


Weight and Balance Envelope
#############################
This section defines the allowable CG and weight limits as a polygon based on POH data, representing the safe operating envelope of the aircraft. In Skywalk, the calculated takeoff CG is plotted against this envelope to visually confirm whether the aircraft loading is within safe boundaries.

.. |figT2D| image:: ../figs/wb_specs.png
   :scale: 50%
.. |figT2E| image:: ../figs/wb_env.png
   :scale: 55%

.. table::
   :align: center

   +----------+
   | |figT2D| |
   +----------+
   | |figT2E| |
   +----------+


Takeoff/ Landing Performance (1)
##########################################################
This section defines correction factors from the POH for wind, runway surface, slope, and safety margins that influence takeoff and landing performance. In Skywalk, these factors are applied dynamically to adjust baseline performance distances based on real-world conditions during flight planning.


.. |figT2F| image:: ../figs/takeofflandingpoh.png
   :scale: 60%

.. table::
   :align: center

   +----------+
   | |figT2F| |
   +----------+

Takeoff/ Landing Performance (2)
##########################################################
This section allows you to input raw POH performance data (altitude, temperature, and distances) and fit a model to approximate performance under varying conditions. In Skywalk, this model is used to estimate takeoff and landing distances for specific environmental conditions encountered during a flight.


.. |figT2G| image:: ../figs/takeofflandingdist.png
   :scale: 80%

.. table::
   :align: center

   +----------+
   | |figT2G| |
   +----------+

.. include:: add_bottom.add
