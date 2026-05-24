# RF Transceiver Module of a Low-Cost Ground Penetrating Radar for Landmine Detection

**B.Tech. Project — IIT Indore | Nov. 2025**  
Satya Sai Praneeth Karri · Mohibahemad Ansari  
Under the guidance of Prof. Rinkee Chopra, Dept. of Electrical Engineering

---

## Overview

Designed and implemented an RF transceiver module for a low-cost, homodyne FMCW (Frequency Modulated Continuous Wave) Ground Penetrating Radar (GPR) centered at 700 MHz, aimed at detecting both metallic and non-metallic landmines.

Current mine-detection methods such as hand-held metal detectors and mechanical probing fail on plastic or non-metallic mines and provide no depth information. This system addresses those limitations using FMCW radar principles.

---

## System Architecture

Homodyne FMCW GPR with the following RF chain:

**Transmitter Chain**
- Voltage Controlled Oscillator (VCO) — 700 MHz center frequency
- Triangular Wave Generator (TWG) — for frequency sweep modulation
- RF Power Amplifier — output ~18 dBm
- Wilkinson Power Divider — splits signal for TX and LO paths

**Receiver Chain**
- Low Noise Amplifier (LNA — MAAL-011207) — input −9.3 dBm, output 15 dBm
- Band-Pass Filter (BPF) — centered at 700 MHz
- I-Q Demodulator (ADL5380) — extracts in-phase and quadrature components

**Antenna**
- Log-Periodic Dipole Array (LPDA) — selected for wideband performance

**Data Acquisition**
- STM32 microcontroller — extracts I/Q data, computes magnitude and phase
- Python interface — displays data received from STM32 on PC

---

## Key Specifications

| Parameter | Value |
|---|---|
| Radar Type | Homodyne FMCW |
| Center Frequency | 700 MHz |
| Architecture | I-Q Demodulator based |
| TX Output Power | ~18 dBm |
| LNA Gain | ~24.3 dB |
| Beat Frequency (measured) | 12.7 kHz |
| Max Detection Depth (soil) | ~40 cm |
| Antenna | LPDA |

---

## Tools Used

- **AWR Microwave Office** — RF circuit simulation and S-parameter optimisation
- **VNA (Vector Network Analyser)** — S-parameter measurements of all PCB modules
- **Spectrum Analyser** — output verification of VCO, amplifier, power divider
- **KiCad / EasyEDA** — PCB design and layout
- **STM32** — data acquisition firmware
- **Python** — signal visualisation

---

## Results

- Successfully detected metallic and non-metallic targets in both air and soil
- Detection depth up to 40 cm in soil with reliable amplitude and phase response
- FFT of beat signal showed peak at 12.7 kHz, matching theoretical computation
- Demonstrated coupling reduction using RF absorbers between TX and RX antennas

---



## Report

Full project report available in `/report/`.

---

*Department of Electrical Engineering, IIT Indore — Nov. 2025*
