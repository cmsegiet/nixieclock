# Nixie Tube Clock
Classic Nixie Tube Clock with Bluetooth/WiFi capability

### Background

The nixie tube displays are fascinating to look at and were used in many Cold War era test equipment and various other devices. I was inspired by many nixie tube clock designs to design my own as well. On the surface, this project seemed very easy. However, the deeper I got into the design phase, I quickly realized I had to learn more about designing switching power supplies to get a high voltage rail for the nixie tubes from a much smaller wall adapter. As well as wanting to learn more about transmission lines and impedance matching for implementing a Printed Inverted F Antenna (PIFA) or in general terms, a microstrip antenna with a resonant frequency of 2.4GHz for WiFi capability. 

### Design Requirements

- WiFi-enabled for configuration and additional features such as a remotely accessible timer or scoreboard. 
- RTC module or integrated RTC to allow time-keeping during failures
- A low voltage power supply such as 5V to 12V wall adapter
- Rotary encoder w/ momentary push button for user control
- Direct drive for Nixie Tubes
- 160V to 180V power supply @ 10mA to drive 4 IN-12A Nixie Tubes (Each tube sinks about 2.5mA at 180VDC)

### Design Implementation Features

- Chose nRF52832 MCU from Nordic Semiconductor w/ integrated RTC and Quadrature Decoder for encoder
- Serial to Parallel Shift Register w/ open-drain latched outputs (also 50V Zener clamped common, discussed later) for tubes
- LM3478 Boost/flyback controller for generating 180VDC
- 3.3V boost regulator for MCU
- 5V boost regulator for shift registers and other IC's
- Barrel jack input for wall adapter allowing about 5V to 12V input (protected by TVS diode and Schottky diode, as well as fused)
- I2C Temperature sensor for monitoring overall system temperature
- Later decided to implement this as a multi-board project with a front panel PCB for Nixie's and a control board for MCU for modularity

## Progress

Just a picture of one of the nixie tubes while testing out the power supply section.

<img src="/Pictures/Initial_Testing01.jpg" width="50%" height="50%">

### 2019-10-12

Finshed most of the schematics, just refining and adding additional features

### 2019-11-05

Finished PCB layout of the control board and figured out how to create a Multi-Board project within Altium Designer. 
