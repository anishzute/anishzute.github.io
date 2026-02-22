---
title: "Onboard Data Logger"
description: "Custom embedded data acquisition system for motorsport telemetry — CAN bus, GPS, IMU, and live dashboards."
tags: ["embedded", "python", "motorsport", "hardware"]
heroImage: "/images/hero_2.jpg"
order: 2
draft: false
---

A custom data logging platform built around a microcontroller reading CAN bus, GPS, and IMU sensors at high frequency. Data is stored to an SD card and visualized post-session via a Python dashboard. Designed to be lightweight, reliable, and easy to reconfigure between events.

<div style="display: flex; align-items: center; gap: 2rem; flex-wrap: wrap; margin-block: 2.5rem;">
  <div style="flex: 1 1 320px; min-width: 260px;">
    <h2 style="margin-top: 0; font-size: 1.3rem;">System Topology</h2>
    <p>
      The onboard logger integrates sensor inputs, CAN telemetry, and records to SD card for later analysis. Real-time data can also be visualized via a live dashboard. The design emphasizes simplicity, robustness, and adaptability for varied motorsport applications.
    </p>
    <ul>
      <li>CAN bus (vehicle data)</li>
      <li>GPS (speed, heading, position)</li>
      <li>IMU (lateral/longitudinal acceleration)</li>
      <li>Configurable sampling rate (100–1000 Hz)</li>
    </ul>
  </div>
  <img 
    src="/images/hero_2.jpg" 
    alt="Custom Data Logger PCB with components" 
    style="max-width: 400px; width: 100%; border-radius: .75rem; box-shadow: 0 2px 12px rgba(0,0,0,0.12);" 
    loading="lazy"
    decoding="async"
  />
<div style="display: flex; gap: 2rem; align-items: flex-start; margin: 2.5rem 0;">
  <div style="flex: 1;">
    <h2>How it Works</h2>
    <p>
      The logger reads high-frequency sensor data—including CAN bus messages, GPS, and IMU measurements—then efficiently writes logs to an SD card. After each session, data is easily transferred and visualized with a custom Python dashboard for analysis and performance tuning.
    </p>
    <ul>
      <li>Realtime CAN, GPS, and IMU acquisition</li>
      <li>Robust SD card logging with timestamping</li>
      <li>Configurable data capture rates and channels</li>
      <li>Visualization, sync with onboard video</li>
    </ul>
  </div>
  <div style="flex: 1; display: flex; justify-content: center;">
    <img src="/images/projects/DL_1.jpg" alt="Onboard Data Logger PCB" style="max-width: 100%; border-radius: 10px; box-shadow: 0 2px 16px rgba(0,0,0,0.10);" loading="lazy" />
  </div>
</div>
