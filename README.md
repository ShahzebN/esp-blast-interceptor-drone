# ESP-BLAST: High-Speed Autonomous Interceptor UAV & Custom GCS

An ESP32-based 60–80 km/h interceptor rocket drone paired with a custom handheld Ground Control Station (GCS), decoupled dual-band RF architecture, and real-time YOLO target-tracking HUD.

> **Final Year Project** | Department of Electrical Engineering, FAST NUCES Islamabad  
> **Team:** Shahzeb Niaz, Anas Bilal, Auon

---

## System Architecture

* **Airframe & Propulsion:** Aerodynamic rocket-profile fuselage designed in Autodesk Fusion, engineered for low-drag high-speed interception (60–80 km/h).
* **Custom Flight Controller PCB:** Designed for SMD assembly via JLCPCB, integrating inertial sensing, PWM motor/servo control, and power distribution.
* **Decoupled RF & Video Pipeline:**
  * **Control & Telemetry:** Dedicated 2.4 GHz RF link for low-latency command and telemetry packets.
  * **FPV Video & OSD:** 5.8 GHz analog video downlink (AKK AIO-SA VTX + MinimOSD) captured via Skydroid OTG receiver.
* **AI-Assisted Ground Control Station:** Custom handheld GCS feeding live analog video into a real-time YOLO object-detection pipeline with custom HUD overlays.

## Repository Contents

* [`/hardware`](./hardware) — JLCPCB Gerber files, schematics, BOM, and Autodesk Fusion `.step`/`.stl` airframe files.
* [`/firmware`](./firmware) — C/C++ embedded firmware for the flight controller and GCS transceiver.
* [`/software`](./software) — Real-time YOLO target detection and telemetry HUD interface.
* [`/docs`](./docs) — System block diagrams, RF link analysis, and testing documentation.

## Hardware & Tech Stack

| Domain | Technologies & Components |
| :--- | :--- |
| **Microcontrollers** | ESP32-S3 (WROOM-1), STM32 / AVR Peripheral Interfaces |
| **PCB & CAD** | Autodesk Fusion, Custom SMD PCBs & Stencils (JLCPCB) |
| **RF & Video** | 2.4 GHz Telemetry Transceivers, 5.8 GHz AKK AIO-SA VTX, MinimOSD, Skydroid OTG |
| **Vision & Software** | Python, PyTorch, YOLO Object Detection, OpenCV, C/C++ |
