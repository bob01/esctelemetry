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
- install RotorFlight 2.0 using the RotorFlight configurator, if already installed skip to configuration
![image](https://github.com/user-attachments/assets/52785324-c523-4f01-8e00-82688117d3f6)
![image](https://github.com/user-attachments/assets/f56faef1-715e-4f5f-82e1-51d351a15f62)
![image](https://github.com/user-attachments/assets/4db3944a-f51e-4338-b6b0-f5cdf7c9ba95)
![image](https://github.com/user-attachments/assets/06b79911-5122-4ee9-9dba-aa3ace0f14b3)

### Configuration
- download [RTFL_cli_escsport.txt](https://github.com/bob01/esctelemetry/blob/main/RTFL_cli_escsport.txt)
- connect to the FC using the configurator, you will likely see this warning - ignore it
![image](https://github.com/user-attachments/assets/8ed00aaf-a841-45fe-a960-3a0ba4f6650f)
- click the [CLI] tab
![image](https://github.com/user-attachments/assets/f24eaec8-67eb-4e12-b7eb-f49c09e58f24)
![image](https://github.com/user-attachments/assets/6f4170cc-3560-41e0-9513-d2f87fafeb1a)
- Load the RTFL_cli_escsport.txt you downloaded above
![image](https://github.com/user-attachments/assets/c32dde29-f6e3-45d3-b0b4-8a580169f2c9)
![image](https://github.com/user-attachments/assets/d7a4f750-449e-431c-b7ea-9a7fc5187967)
- type 'save' to commit the loaded settings. The FC will reboot and reconnect
![image](https://github.com/user-attachments/assets/bc5beaaa-5489-423a-b992-d939f0abf095)
![image](https://github.com/user-attachments/assets/6ec57b2e-ee97-490b-aafb-347f53d4305c)
- go to the [Power] tab
  - change the 'Capacity [mAh]' setting to match your battery
  - do not change anything else
  - save
![image](https://github.com/user-attachments/assets/627231c4-d446-452e-b5df-888ed86acd48)
- goto the [Motors] tab
  - change 'ESC Telemetry protocol' to match your ESC
  - change 'Main Motor pole count' to match your motor (for accurate RPM)
  - do not change anything else
  - save
![image](https://github.com/user-attachments/assets/f320bba6-31f7-4598-864d-a4d520bba792)

### Installation
- install securely anywhere
- connect the ESC telemetry cable to the 2-pin RX2 port
- connect the 3-pin TX3 port to a port on the FrSky Rx that's been configured to accept s.port
![image](https://github.com/user-attachments/assets/57e2d293-617f-4900-b589-c2054ae41361)
