# MCU Data Logger — ATmega328P + RTC + External dual EEPROM

# Features

- ATmega328P-AU AVR Microcontroller
- Dual 24LC1025 External EEPROMs
- DS1337S RTC (Real Time Clock)
- I2C Communication Bus
- UART Header
- SPI Programming Header
- External Crystal Oscillator
- Battery Powered Design
- Compact 2-Layer PCB
- GPIO Breakout Header
- RTC Backup Support

# Hardware Overview

## 1. Microcontroller

### ATmega328P-AU
Main controller used for:
- Data processing
- lower power consumption
- EEPROM communication
- RTC communication
- GPIO handling
- UART communication

### MCU Clock
- 16 MHz Crystal Oscillator
- Two 22 pF load capacitors

### Reset Circuit
- 10k pull-up resistor on RESET pin to keep the reset pin high in normal mode

### Power Decoupling
- 0.1uF decoupling capacitor near VCC  for power stabliity 

# Memory Storage

## External EEPROM

Two external EEPROM ICs are used:

- 24LC1025
- 24LC1025

### Communication
- I2C Protocol

### EEPROM Features
- Non-volatile memory
- Long-term data retention
- Byte and page write support

### Address Configuration

#### EEPROM U2
- A0 = VCC
- A1 = VCC
- A2 = VCC

#### EEPROM U3
- A0 = GND
- A1 = VCC
- A2 = VCC

This allows both EEPROMs to operate on the same I2C bus with different addresses.

### I2C Pull-up Resistors
- SDA → 4.7kΩ pull-up
- SCL → 4.7kΩ pull-up

# RTC Section
## DS1337S Real-Time Clock

Used for:
- Timekeeping
- Timestamp generation
- Scheduled logging
- supports battery backup oscillator

### RTC Crystal
- 32.768 kHz crystal oscillator

### RTC Interrupt
INT/SQW output available for:
- Alarm interrupt
- Periodic wakeup
---
# Communication Interfaces

## I2C Header
Exposed pins:
- SDA
- SCL
- VCC
- GND
  
Used for:
- External sensor connection
- Additional peripherals
  
## UART Header
Exposed pins:
- RX
- TX
- VCC
- GND
Used for:
- Serial debugging
- PC communication
- Data extraction
  
## SPI Header
6-pin SPI programming interface:
- MOSI
- MISO
- SCK
- RESET
- VCC
- GND

Used for:
- Bootloader flashing
- Firmware upload
  
# GPIO Header

Digital GPIO breakout:
- D2
- D3
- D4
- D5
- D6
- D7
- D8
- VCC
- GND

Used for:
- Sensor interfacing
- Digital peripherals
- Expansion

# Power System

## Input Power
Battery-powered design.

### Power Indicator
LED with 330Ω current-limiting resistor.

### Decoupling Capacitors
Used near IC power pins for:
- Noise reduction
- Stable operation

---

# PCB Design

## PCB Specifications

- 2-Layer PCB
- Through-hole + SMD mixed design
- Compact embedded layout
- NPTH Mounting holes provided for pcb support
  
### Design Considerations

- Separate signal routing
- Short I2C traces
- Pull-up resistors near bus
- Ground return optimization
- Crystal traces kept short






