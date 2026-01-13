# Spectroscopy-Based PPFD Monitoring System

This repository contains the source code used in the study:

"A Low-Cost Spectroscopy-Based System for Monitoring Photosynthetic Light and
Daily Light Integral under Dynamic Lighting in Plant Factories"

## Overview
This project implements a low-cost monitoring system for measuring
photosynthetic light at canopy level in indoor farming and plant factory
environments. The system is based on a multi-channel spectral sensor and an
embedded microcontroller, enabling real-time estimation of photosynthetic
photon flux density (PPFD) and continuous data logging for daily light
integral (DLI) analysis.

The code is designed for research and reproducibility purposes and supports
both constant and dynamically varying lighting conditions.

## Hardware Components
- Microcontroller: ESP32
- Spectral sensor: AS7265x (18-channel spectral sensor)
- Real-time clock (RTC): DS3231
- Storage: MicroSD card module
- Network: Wi-Fi connection for data transmission

## Main Functions
- Acquisition of spectrally resolved irradiance data
- Real-time estimation of PPFD using calibrated spectral signals
- Time-stamping of measurements using RTC synchronized via NTP
- Local data logging to SD card in CSV format
- Optional data transmission to a remote server via HTTP

## Operating Schedule
Data acquisition and transmission are performed only during predefined
operational hours to match plant factory lighting schedules. Measurements
outside these periods are automatically suspended.

## Output Data
The system records:
- Timestamp
- Individual spectral channel values
- Integrated spectral intensity
- Estimated PPFD
- Aggregated spectral bands (blue–violet, green, yellow–orange, red, infrared)

Data are stored locally on the SD card and can also be transmitted to an
external server for visualization or further analysis.

## Usage
1. Upload the code to an ESP32 microcontroller using Arduino IDE.
2. Connect the AS7265x spectral sensor via I2C.
3. Insert a formatted microSD card.
4. Configure Wi-Fi credentials and server parameters if remote transmission
   is required.
5. Deploy the device at plant canopy level under LED lighting.

## Notes
- Calibration coefficients for PPFD estimation are system-specific and should
  be adjusted when using different lighting spectra or sensor configurations.
- This implementation functions as an open-loop monitoring system and does
  not actively control lighting output.

## License
This code is provided for academic and research use.
