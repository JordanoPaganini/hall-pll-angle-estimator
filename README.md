# Hall PLL Angle Estimator

![C](https://img.shields.io/badge/C-Embedded-00599C?logo=c&logoColor=white)
![STM32](https://img.shields.io/badge/STM32-STM32F407VET6-03234B?logo=stmicroelectronics&logoColor=white)
![Python](https://img.shields.io/badge/Python-Tools%20%26%20Analysis-3776AB?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green.svg)

A bare-metal embedded project for reading three Hall sensor signals and estimating rotor position with a phase-locked loop (PLL).

## Overview

The project targets the STM32F407VET6 and is designed to interpret Hall states and transitions, determine rotation direction, estimate speed, and provide continuous mechanical and electrical rotor angles. Its output is intended for future integration with a field-oriented control (FOC) system.

## Technology

- C for the embedded firmware
- STM32F407VET6 target hardware
- Bare-metal execution without an RTOS
- Python for host-side tools, simulation, and analysis

## Status

Project setup and engineering definition are in progress. The final estimator will use a PLL.

## License

This project is licensed under the [MIT License](LICENSE).
