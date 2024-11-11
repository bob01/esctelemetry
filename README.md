# Welcome to ESC S.Port (escsport)
General purpose ESC telemetry adapter for connection to FrSky s.port receivers

**USE AT YOUR OWN RISK**


### About escsport
Why? To get heli quality ESC telemetry for fixed wing applications.<br>
We use bettery capacity/consumption telemetry info to maximize flighttime and voltage telemetry monitor battery performance/warnings.<br>
So much better than flying by a timer.
This project addresses this need and is now standard equipment in my new builds.

### Available telemetry sensors (Scorpion ESC used here)
TODO: Tele image

### Requirements
- an ESC w/ telemetry supported by RotorFlight (YGE, Scorpion, HobbyWing, Kontronik ...)
- small RotorFlight flight controller (FC) - e.g. [Matek G474-HLITE](https://www.mateksys.com/?portfolio=g474-hlite), it's 30x23x13mm 9g
- RotorFlight 2.0 (release 4.3.0) firmware - install using the [configurator](https://github.com/rotorflight/rotorflight-configurator/releases/tag/release%2F2.0.0)

### The connections
- connect the FC with a 3 pin servo cable to one of the FrSky Rx's s.port ports
  - most FrSky Rx's can be configured to accept s.port devices on any free port
  - this connection will power the FC
- connect the ESC's telemetry signal and optionally the -ve/gnd, omit the +ve *this WILL damage certain setups*

### The hardware
- solder pins to the FC
  - RX2: 2-pin signal+gnd
  - TX3: 3-pin
  ![image](https://github.com/user-attachments/assets/ce2c73af-364c-4798-8e5b-c6b16d7c5de1)
![image](https://github.com/user-attachments/assets/2e61563e-ef2a-433b-ad23-9bace3d8ba95)

### The firmware
- install RotorFlight 2.0, if already installed skip to configuration
![image](https://github.com/user-attachments/assets/52785324-c523-4f01-8e00-82688117d3f6)
![image](https://github.com/user-attachments/assets/f56faef1-715e-4f5f-82e1-51d351a15f62)
![image](https://github.com/user-attachments/assets/4db3944a-f51e-4338-b6b0-f5cdf7c9ba95)
![image](https://github.com/user-attachments/assets/06b79911-5122-4ee9-9dba-aa3ace0f14b3)

### Configuration
- download 
