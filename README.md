# Project Name

CAN Bus Vehicle Data Logger

## Project Owner

**Name:** Atul Luitel 
**Virginia Tech Email:** atull@vt.edu

## Project Overview

A standalone logger that plugs into a car's OBD-II port, requests standard parameters (RPM, speed, coolant temperature) over CAN, decodes them, shows them on an LCD, and saves timestamped CSV rows to a microSD card. It is built on an Arduino Uno with an MCP2515 CAN module, a DS3231 RTC, and a custom PCB shield, and is tested in the lab with a simulated ECU.

## What I Hope to Learn

CAN protocol: frames, IDs, bit timing, termination, OBD-II requests
Embedded C: SPI/I2C, interrupts, ring buffers on 2 KB of RAM
Decoding raw bytes into units and reliable SD logging
PCB design in KiCad, from schematic to assembled board
Measuring performance: frame loss, decode accuracy, log rate

## Design and Implementation

<img width="757" height="255" alt="image" src="https://github.com/user-attachments/assets/44c5bead-33a6-4b49-9496-47b2ddd8b038" />

Firmware loop: request PID (ID 0x7DF) → receive reply (0x7E8) → decode → timestamp → write CSV → update LCD.

Key decisions

Active PID requests (read-only), since many cars hide traffic behind a gateway.
Interrupt-driven receive with a ring buffer so SD writes don't drop frames.
Bench ECU simulator (second Arduino + MCP2515) for testing without a car.

## Bill of Materials

Document the major components and materials used for the project.

| Item | Quantity | Estimated Cost | Link |
|---|---:|---:|---|
| Component | 1 | $0.00 | Link |

**Estimated Total Cost:** $0.00

## Timeline and Milestones

Outline the major stages of the project and update them as work progresses.

| Milestone | Target Date | Status |
|---|---|---|
| Project planning | Date | Not Started |
| Initial design | Date | Not Started |
| Prototype | Date | Not Started |
| Testing | Date | Not Started |
| Project completion | Date | Not Started |

## Progress Log

2026-10-17

Scoped the project. Next: order parts and run the MCP2515 loopback test (check the module's crystal, 8 or 16 MHz).
### YYYY-MM-DD

## Project Files


## Useful Links


## Project Image

Replace the `hero.png` file in the root of this repository with an image representing your project.

**Keep the filename as `hero.png`.**

This image is used as the project cover image on the AMP Lab website.
