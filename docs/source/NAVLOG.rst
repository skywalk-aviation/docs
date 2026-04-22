NAVLOG Routing
=======================

The Leg Information system provides pilots with a structured, editable overview of each LEG in a SkyWalk route.
It combines pre‑flight planning data with real‑time GPS‑based updates, safety validation, and automatic recalculation of performance metrics.


.. |figF4| image:: ../figs/navlog_gui.png
    :scale: 60%

.. table:: Information pér LEG.
    :align: center

    +----------+
    |  |figF4| |
    +----------+


Timer System
==============

SkyWalk uses a unified play/pause button and a leg‑based timer to track progress and support safety checks.
The checkbox "GPS Compass" shows the GPS location from you mobile device.
The checkbox "Haptic Feedback" makes vibrations in the last 3 seconds of the LEG and when the LEG is finished.

Play/Pause Toggle Button
------------------------

A single button controls the timer:

- **▶ Start** (green) when paused
- **⏸ Pause** (amber) when running

The button updates automatically when:

- Starting the timer
- Pausing the timer
- Resetting
- Auto‑starting on “Next Leg”

Leg Start Time Tracking
-----------------------

A timestamp is stored when the pilot taps **Start**. It is used for:

- Elapsed‑time calculations
- Time‑vs‑distance safety validation

The timestamp is cleared on reset or when switching legs.


Vibration Alerts
================

SkyWalk uses the device’s vibration motor (where supported) to provide tactile
countdown cues.

Countdown Alerts
----------------

During the final three seconds of a leg:

- **3 seconds remaining** → one buzz
- **2 seconds remaining** → two buzzes
- **1 second remaining** → three buzzes

Leg Completion Alert
--------------------

At 0 seconds:

- **short – short – long**
    - 80 ms
    - 80 ms
    - 300 ms

Unsupported devices (e.g., iOS Safari) silently ignore vibration requests.




Safety Checks
==============

The *NAVLOG GUI* provides a structured overview of each navigation LEG in a SkyWalk route.
Each leg contains both editable and computed fields.



GPS Update
-------------------

When the pilot taps **Update**, the GPS of the mobile phone will be used to refresh heading, track, wind correction, and time‑remaining based on real‑time device position and speed.
The following steps are performed to get accurate information:

1. **GPS Fix Acquisition**
   - One‑shot get current position
   - High‑accuracy mode, 10 s timeout

2. **Speed Comparison**
   - If GPS speed differs from planned ground speed by more than **15 kt**,
     a confirmation dialog displays both values and allows the pilot to choose.

3. **Distance & Bearing Recalculation**
   - Computes distance to destination and new bearing from current position.

4. **METAR Integration**
   - Retrieves nearest METAR station
   - Extracts wind direction and speed
   - Computes:
     - Headwind
     - Crosswind
     - Wind Correction Angle (WCA)
   - Recomputes corrected magnetic heading.

5. **Live UI Refresh**
   - Heading and track
   - Remaining distance
   - Time remaining
   - Progress bar values
   - Countdown timer

All updates occur without leaving the current leg.


Safety Validation System
==========================

There are various safety checks before applying any GPS‑based update.
SkyWalk runs a comprehensive validation routine that should prevents incorrect LEG updates and warns the pilot when conditions appear inconsistent.

Hard Blocks
-----------

These conditions immediately cancel the update:

1. **Along‑Track Position**
    - Aircraft is < −10% or > 115% of leg length.

2. **Heading Reversal**
    - New track differs > 120° from planned.

3. **Distance Mismatch**
    - Remaining distance > 140% of original leg distance.

4. **GPS Accuracy (Poor)**
    - Accuracy > 500 m.

Soft Warnings
-------------

These conditions show a confirmation dialog; the pilot may override:

1. **Overshoot**
    - < 0.3 km remaining.

2. **Cross‑Track Error**
    - > 15% of leg length (minimum 2 km).

3. **GPS Accuracy (Medium)**
    - 200–500 m accuracy.

4. **Time vs Distance Consistency**
    - After 30 s and 0.5 km:
    - Implied GS < 40% or > 200% of planned.
    - Negative progress after 60 s.

These checks help ensure the pilot is updating the correct leg and that the GPS
data is reliable enough to compute a new heading.




.. include:: add_bottom.add
