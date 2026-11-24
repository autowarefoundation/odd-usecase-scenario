# Vision Pilot ODD - Natural Language Description

This document describes, in plain language, the Operational Design Domain (ODD) of the Vision Pilot product.

Attribute names and value ranges follow the taxonomy in [Domain_Concepts_Definition_ISO_34503.yaml](../Domain_Concepts_Definition_ISO_34503.yaml), which is based on ISO 34503.

## Overview

Vision Pilot is an SAE Level 2+ lane keeping function intended for highway driving, relying on camera-based perception.
The vehicle is inside the ODD only when **all** of the "In ODD" conditions below hold, and **none** of the "Out of ODD" conditions apply.
If any single Out-of-ODD condition occurs, the vehicle is considered to be outside the ODD.

## In ODD Conditions

### Road type

The function operates only on **motorways, highways, or interstates**.
Any other road type (for example urban streets, rural roads, parking lots) is outside the ODD.

### Road geometry

- **Curvature**: from 0.0 to 0.0125 1/m, i.e. straight roads and curves with a radius of **80 m or larger**.
  This limit is based on the steep curve track of the Horiba MIRA test track.
- **Bank angle (cross slope)**: from **-1 deg to 7 deg**, based on typical US interstate highways.
- **Inclination angle (longitudinal grade)**: from **-5 deg to +5 deg** (roughly +/-8.7 % grade), uphill or downhill, based on typical US interstate highways.

### Lane markings

Lane markings must be present and either **clear** or **blurred** (e.g. faded or partially worn, but still present).
Roads without lane markings are outside the ODD.
If specific types of lane markings (e.g. solid, dashed, Botts' dots) need to be distinguished in the future, the taxonomy will need to be extended.

## Out of ODD Conditions

The vehicle is outside the ODD as soon as **any one** of the following conditions applies.

### Temporary road structures

- **Construction site detours**
- **Road work zones**

### Special vehicles in traffic

The presence of any of the following special vehicles:

- **Ambulances**
- **Police vehicles**
- **Work vehicles**

### Poor camera sensing conditions

Conditions that degrade the camera's ability to perceive the environment:

- **Rain heavier than light rain**: rainfall rate above 2.5 mm/h (moderate, heavy, violent, or extreme rain).
  Light rain (up to 2.5 mm/h) remains inside the ODD.
- **Snowfall heavier than light snow**: snowfall that reduces visibility to **less than 1 km** (moderate or heavy snow).
  Light snow (visibility of 1 km or more) remains inside the ODD.
- **Low illumination**: ambient illuminance below **0.1 lux**, which roughly corresponds to a night lit only by a full moon.

### Poor vehicle control conditions

Road surface conditions that degrade the vehicle's ability to control its motion:

- **Icy** surface
- **Flooded** surface
- **Standing water** on the surface
- **Snow on the surface**
- **Wet** surface
- **Surface contamination** (e.g. oil, sand, gravel, or debris on the road)

In practice, this means the function is designed for **dry road surfaces** only.

## Summary

Vision Pilot keeps its lane on marked motorways with moderate curves and slopes, in dry road conditions, under light or no precipitation, and with at least moonlight-level illumination.
It is not designed to operate through construction zones, around emergency or work vehicles, in heavy rain or snow, in near-total darkness, or on wet, icy, snowy, flooded, or contaminated road surfaces.
