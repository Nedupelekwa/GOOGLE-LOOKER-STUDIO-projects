# Flight Planning & Operations Dashboard (Looker Studio)

## Project Overview
This Looker Studio project provides a dynamic interface for analyzing global flight telemetry. It integrates raw aircraft specifications with live flight data to visualize operator performance and spatial aircraft distribution.

## Key Features
* **Raw Aircraft Tracking:** Detailed logs of ICAO hex codes, registration IDs, and aircraft models (Airbus, Boeing, McDonnell Douglas).
* **Operator Analytics:** Comparative reporting on record counts per airline, identifying fleet utilization for carriers like British Airways and EasyJet.
* **Geospatial Mapping:** Interactive Google Maps integration showing flight paths and density relative to altitude (Alt) in specific regions.
* **Flight Operations View:** Dedicated tracking for individual aircraft IDs, monitoring Piper and other light aircraft movements.

## Technical Details
* **Platform:** Google Looker Studio
* **Data Sources:** - `Raw Flight Data`: Time-stamped altitude and hex records.
    - `Raw Aircraft Details`: Comprehensive database of operators and model types.
* **Visualizations:** Tabular record counts, altitude sliders, and geospatial bubble maps.

## How to Use
1. **Filter by Operator:** Use the 'operator' fields to isolate specific airlines like Etihad or EVA Air.
2. **Altitude Control:** Utilize the 'Altitude in feet' slider to visualize flight paths at specific atmospheric layers.
3. **Aircraft Drill-down:** Search by 'Hex' or 'regid' to view the history of a specific airframe.

## Analysis Summary
The dashboard highlights the dominance of short-haul Airbus models in European record counts and provides granular visibility into the flight path of regional operators near London and the surrounding National Landscapes.

This project features a comprehensive Flight Planning and Operations Dashboard developed in Looker Studio. It transforms raw aviation telemetry into a geospatial and tabular analysis of aircraft movements and operator efficiency.

Project Summary

The "Flight Planning" dashboard provides a multi-layered view of global and regional aviation activity. By synthesizing data from aircraft details and real-time flight logs, the project enables tracking of specific airframes, operator fleets, and altitude-based flight paths.

Key Metrics & Findings:

High-Volume Operators: British Airways was identified as a primary driver of activity, with specific Airbus A319 and A320 aircraft recording over 18,500 individual records.Fleet Diversity: The project tracks a wide array of models, from large-scale commercial jets like the Boeing 747-45E and Airbus A380-861 to light aircraft like the Piper PA-28-181.

Altitude Analysis:

Operational data indicates heavy traffic at cruising altitudes of 43,000 feet for long-haul carriers (e.g., Etihad, China Airlines), while regional flight operations were mapped at lower altitudes between 25 and 2,425 feet.

Geospatial Tracking:

The dashboard successfully mapped flight density across the United Kingdom, specifically concentrated around London and the North Wessex Downs region.
