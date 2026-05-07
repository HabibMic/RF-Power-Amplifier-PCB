
# RF Power Amplifier & Impedance Matching System

## Overview
This repository contains the design and 4-layer PCB layout for a high-frequency RF power amplifier. The system features an active gain stage and two separate impedance matching networks designed to interface a non-standard "test load" with a 50 Ohm system.

## Design Specifications

### 1. Active RF Gain Block
* **Amplifier**: Based on the Mini-Circuits GALI-S66 integrated circuit.
* **Biasing**: Utilizes a 9V DC supply with a 300 Ohm total bias resistance (implemented as two 150 Ohm resistors in series) to set stable operating current.
* **RF Isolation**: Employs a Ferrite Bead (FB1) as an RF choke to isolate the DC path from high-frequency signals.
* **Coupling & Decoupling**: Includes 100pF DC-blocking capacitors at the input and output ports, and a decoupling array (10nF and 100uF) to filter power supply ripple.

### 2. Impedance Matching Networks
* **Short-Circuit Shunt Stub**: Calculated via Smith Chart analysis for a physical distance of 86.3 and a stub length of 10.7 mm.
* **Quarter-Wave Transformer**: A lambda/4 transmission line section with a calculated characteristic impedance of 70.7 Ohms.

## PCB Manufacturing
* **Form Factor**: 48.26 mm x 48.26 mm, compliant with 5 cm x 5 cm laboratory constraints.
* **Stackup**: JLC04161H-7628 4-layer standard configuration.
* **Layer Strategy**: 
    * **Top Layer**: Signal routing and RF microstrip lines.
    * **Internal Layer 1**: Dedicated ground plane for impedance control.
    * **Internal Layer 2**: Power plane.
* **Thermal Management**: Via-stitching array implemented under the GALI-S66 thermal pad for heat transfer to internal planes.

## Lab Characterization
Testing was performed using a Keysight N9912A FieldFox Vector Network Analyzer.
* **Measurement**: S-parameter characterization (S11, S21) across a 50 to 150 MHz sweep.
* **Calibration**: Applied port extension techniques to null out phase delays from coaxial test cables.

---
**Author**: Micheal Habib 
