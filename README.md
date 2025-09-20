

# AI-Powered Smart Public Safety & Environmental Monitoring Node

## Overview

This project implements an **edge computing node** for public safety and environmental monitoring using the **open-source POWER CPU core Microwatt**. The node combines 
**video-based crowd density estimation** with **environmental sensor fusion** (temperature, air quality, noise, vibration) and runs lightweight AI models locally for **real-time alert generation**.

The design is **FPGA-prototyped** and can be implemented as an **ASIC using the Sky130 PDK** with available standard cells.

---

## Features

- **Crowd Density Monitoring:** Uses a camera module and lightweight CNN models to estimate crowd density in public spaces.
- **Environmental Sensor Fusion:** Aggregates temperature, air quality, noise, and vibration sensors to detect anomalies and hazards.
- **Local AI Inference:** TinyML models run on Microwatt (or optional FPGA co-processor) for low-latency decision-making.
- **Secure Alerts:** Edge node generates real-time alerts and transmits securely via Ethernet/Wi-Fi/LoRa.
- **Low-Power Design:** Suitable for remote deployment with battery or solar power.
- **Open-Source & Auditability:** Fully open-source hardware and software stack.

---

## System Architecture

       ## System Architecture

```text
     +-------------------+
     |   Microwatt CPU   |
     | OS/RTOS + AI Coord|
     +-------------------+
              |
              v
     +-------------------+      +-----------------------+
     |   Camera Module   |      |  Environmental Sensors|
     | - Crowd Density   |      | - Temperature         |
     | - Estimation CNN  |      | - Air Quality (CO₂, PM2.5)
     |                   |      | - Noise Level         |
     |                   |      | - Vibration Sensor    |
     +-------------------+      +-----------------------+
              |                          |
              +-----------+  +-----------+
                          v  v
                 +-------------------+
                 | Local AI Inference|
                 | - Tiny CNN/LSTM   |
                 +-------------------+
                          |
                          v
                 +---------------------------+
                 | Alert Generation & Logging|
                 | - Event Filtering         |
                 | - Secure Transmission     |
                 +---------------------------+
```

## Edge Node Features & Why Microwatt is Applicable

The following table highlights the main features of the edge node and explains why the Microwatt CPU core is particularly suitable for this application.”


| Feature                                    | Why Microwatt is Suitable                                                                 |
|-------------------------------------------|-------------------------------------------------------------------------------------------|
| **Low-latency decision-making**            | Microwatt’s simple, low-power design enables fast local AI inference at the edge.        |
| **Secure real-time alerts**                | Open-source core allows customized security protocols and full control over communication.|
| **Autonomous operation during outages**    | Lightweight CPU can run a minimal RTOS or embedded Linux, processing data locally even without network connectivity. |
| **Scalable deployment**                    | Small footprint and low power make it cost-effective to deploy multiple nodes across public spaces. |

## Implementation

### FPGA Prototype

- **Tools:** GHDL / Verilator for RTL simulation.
- **Target FPGA** 
- **Components:** Microwatt CPU core, sensor interface modules, optional AI accelerator.
- **Testing:** Validate sensor readouts, AI inference, and communication logic.

### ASIC Implementation

- **Technology:** Sky130 PDK
- **Flow:** OpenLane.
- **Components:** Microwatt CPU, sensor interfaces, memory, AI accelerator, secure communication module.
- **Constraints:** Standard cell libraries only; low-power edge deployment.

---

## Software Stack

- Minimal Linux or RTOS running on Microwatt.
- TinyML framework (MicroTVM or equivalent) for AI inference.
- Local processing for crowd density estimation and environmental anomaly detection.
- Alert generation module with secure communication.

---

## Usage

1. **FPGA Simulation / Testing:**  
   - Run RTL simulations using GHDL or Verilator.  
   - Load design onto FPGA and test sensor integration and AI inference.

2. **Deploy ASIC Version:**  
   - Synthesize design in Sky130 using OpenLane.  
   - Integrate sensors and communication modules for a fully functional edge node.

3. **Monitoring & Alerts:**  
   - View real-time sensor data and AI predictions via secure dashboard.  
   - Receive alerts for crowd density threshold breaches or environmental hazards.

---

## Dependencies

- **Hardware:** Camera module, temperature, air quality, noise, and vibration sensors.  
- **FPGA Tools:** GHDL, Verilator, Yosys, NextPNR.  
- **ASIC Tools:** OpenLane, Sky130 PDK, standard cell libraries.  
- **Software:** Linux/RTOS for Microwatt, TinyML frameworks for AI models.

---

## Contributors

- Karthika G S.

---

## References

1. [Microwatt OpenPOWER Core](https://git.openpower.foundation/cores/microwatt)  
2. [Sky130 PDK](https://skywater-pdk.readthedocs.io/)  
3. TinyML / MicroTVM frameworks for embedded AI  
4. Crowd density and environmental sensor fusion research papers

                 

