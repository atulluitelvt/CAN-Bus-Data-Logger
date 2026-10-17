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

| Item | Quantity | Estimated Cost | Link |
|---|---:|---:|---|
| Arduino Uno R3 | 1 | $15.00 | Link |
| MCP2515 CAN bus module | 1 | $8.00 | Link |
| microSD card module | 1 | $6.00 | Link |
| 16x2 LCD with I2C backpack | 1 | $9.00 | Link |
| DS3231 RTC module | 1 | $7.00 | Link |
| Breadboard and jumper wire pack | 1 | $8.00 | Link |
| microSD card (8–32 GB) | 1 | $8.00 | Link |
| OBD-II cable with open leads | 1 | $12.00 | Link |
| 12 V to USB car power adapter | 1 | $8.00 | Link |
| Bench ECU simulator node (Nano, MCP2515, potentiometers) | 1 | $15.00 | Link |
| Custom PCB (5 boards from a fab house) | 1 | $10.00 | Link |
| PCB parts (sockets, headers, termination resistor, fuse) | 1 | $8.00 | Link |

**Estimated Total Cost:** $114.00

## Timeline and Milestones

| Milestone | Target Date | Status |
|---|---|---|
| Project planning | Oct 23, 2026 | In Progress |
| Initial design | Oct 30, 2026 | Not Started |
| Prototype | Nov 13, 2026 | Not Started |
| Testing | Nov 18, 2026 | Not Started |
| Project completion | Nov 20, 2026 | Not Started |

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
