---
title: "Wind Tunnel Force Sensor"
date: 2022-03-15
summary: "2-axis force measurement assembly for high school physics class"
thumbnail: assets/img/projects/wind_tunnel/Screenshot 2026-11-13 084256.png
order: 6
math: true
---

I made this wind tunnel force measurement for my high school's wind tunnel that didn't have any sensors. It uses a compliant x-y decoupling mechanism to take simultaneous readings of both axes.

CAD of sensor assembly:

<img src="/assets/img/projects/wind_tunnel/Screenshot 2026-11-13 084256.png" width=600>

**MCU:** ESP32
**Display:** 16x2 LCD display w/ I2C controller
**Sensing:** 5N load cells, HX711 amplifiers (modified to run at 100Hz)

