Navigation
=====================

.. warning::
    The NAVLOG is only for educational purposes. Do not use it during flight. Always check it against your own trusted source.


The ``ENROUTE`` section is to visually plan the route between departure and arrival.

The **FlightMap** tab contains information from various tabs and projects it onto the interactive flight map.
The map will show the departure, arrival, and alternate aerodromes with static, real-time, and user-defined information and images.

**A summary of information that can be seen on the map:**

    * The route between Departure-Arrival: a line for illustration that can be changed.
    * Nearby Aerodromes: Various colors are used to separate between Public, Military, and Private aerodromes, as well as between Grass and Asphalt runways.
    * METAR information: Real-time information from the closest weather stations is processed and projected.
    * Airspaces and other areas: Gliding, parachute zones, etc.


.. |figF2| image:: ../figs/enroute.png
   :scale: 60%

.. table:: Projection of information into the map for **EHRD** to **EHTX**.
    :align: center

    +----------+
    |  |figF2| |
    +----------+



METAR Information
=======================

The METAR weather information can be projected on the map by using the option ``METAR stations``.
More information about the METAR is described in the ``Departure/ Arrival`` section.



LEG Information
=======================

The Leg Information table provides a structured overview of LEG in your planned route, allowing precise control over navigation data while keeping computed values consistent and reliable.
Each leg is represented as a row containing editable fields—Category, Leg Name, and Altitude—alongside.
The performance metrics such as Distance, Ground Speed, and Estimated Time are pre-computed.
Categories define the operational phase of the flight (DEPARTURE, ENROUTE, ARRIVAL), while leg names help identify waypoints or pattern segments.
Altitude entries can be freely adjusted, and SkyWalk automatically recalculates downstream metrics to maintain an accurate navigation log.
This interface ensures pilots can refine their route, verify leg‑by‑leg performance, and maintain a clear, aviation‑standard structure throughout the entire flight plan.

Editable Fields
---------------

- **Category** (DEPARTURE, ENROUTE, ARRIVAL)
- **Leg Name** (waypoint or pattern segment)
- **Altitude** (planned altitude for the segment)

Computed Fields
---------------

- **Distance** (NM / KM)
- **Ground Speed** (kt)
- **Estimated Time** (min)

SkyWalk automatically recalculates all dependent values whenever the user edits
a field or when a GPS‑based update is applied.


.. |figF3| image:: ../figs/navlog_legtable.png
   :scale: 60%

.. table:: LEG information for **EHRD** to **EHTX**.
    :align: center

    +----------+
    |  |figF3| |
    +----------+

.. include:: add_bottom.add
