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

### Hardware
- solder pins to the FC
  - RX2: 2-pin signal+gnd, again: the +ve pin is removed to avoid possible damage
  - TX3: 3-pin
  - unused / unwanted pins are easily pressed / pulled out of the header with pliers etc.
![image](https://github.com/user-attachments/assets/ce2c73af-364c-4798-8e5b-c6b16d7c5de1)
![image](https://github.com/user-attachments/assets/2e61563e-ef2a-433b-ad23-9bace3d8ba95)

### Firmware
- install RotorFlight 2.0 using the RotorFlight configurator, if already installed skip to configuration<br>
<img src="https://github.com/user-attachments/assets/52785324-c523-4f01-8e00-82688117d3f6" width=400></img><img src="https://github.com/user-attachments/assets/f56faef1-715e-4f5f-82e1-51d351a15f62" width=400></img><img src="https://github.com/user-attachments/assets/4db3944a-f51e-4338-b6b0-f5cdf7c9ba95" width=400></img><img src="https://github.com/user-attachments/assets/06b79911-5122-4ee9-9dba-aa3ace0f14b3" width=400></img>

### Configuration
- download [RTFL_cli_escsport.txt](https://github.com/bob01/esctelemetry/blob/main/RTFL_cli_escsport.txt)
- connect to the FC using the configurator, you will likely see this warning - ignore it<br>
<img src="https://github.com/user-attachments/assets/8ed00aaf-a841-45fe-a960-3a0ba4f6650f" width=400></img>
- click the [CLI] tab<br>
<img src="https://github.com/user-attachments/assets/f24eaec8-67eb-4e12-b7eb-f49c09e58f24" width=400></img><img src="https://github.com/user-attachments/assets/6f4170cc-3560-41e0-9513-d2f87fafeb1a" width=400></img>
- Load the RTFL_cli_escsport.txt you downloaded above<br>
<img src="https://github.com/user-attachments/assets/c32dde29-f6e3-45d3-b0b4-8a580169f2c9" width=400></img><img src="https://github.com/user-attachments/assets/d7a4f750-449e-431c-b7ea-9a7fc5187967" width=400></img>
- type 'save' to commit the loaded settings. The FC will reboot and reconnect<br>
<img src="https://github.com/user-attachments/assets/bc5beaaa-5489-423a-b992-d939f0abf095" width=400></img><img src="https://github.com/user-attachments/assets/6ec57b2e-ee97-490b-aafb-347f53d4305c" width=400></img>
- go to the [Power] tab
  - change the 'Capacity [mAh]' setting to match your battery
  - do not change anything else
  - save<br>
<img src="https://github.com/user-attachments/assets/627231c4-d446-452e-b5df-888ed86acd48" width=400></img>
- goto the [Motors] tab
  - change 'ESC Telemetry protocol' to match your ESC
  - change 'Main Motor pole count' to match your motor (for accurate RPM)
  - do not change anything else
  - save<br>
<img src="https://github.com/user-attachments/assets/f320bba6-31f7-4598-864d-a4d520bba792" width=400></img>

### Installation
- install securely anywhere
- connect the ESC telemetry cable to the 2-pin RX2 port
- connect the 3-pin TX3 port to a port on the FrSky Rx that's been configured to accept s.port
![image](https://github.com/user-attachments/assets/688ae2a3-0594-4aba-ac8c-c73a3ac49f37)
![image](https://github.com/user-attachments/assets/57e2d293-617f-4900-b589-c2054ae41361)

### On the transmitter
- power up Tx, Rx and ESC
- discover new sensors, the ESC supplied sensors like VFAS, Current, Fuel etc should appear
- there may be duplicates e.g. temp, RPM etc - delete what you don't need<br>Note: both main and tail rotor RPM are reported as 'RPM', power the motor briefly to see which one responds - delete the others
![image](https://github.com/user-attachments/assets/d0003743-2df4-4d11-988c-39cb26d118cb)
- the 'mAh' current consumption sensor may not have been auto discovered
  - create a DIY sensor
  - click 'AutoDetect' and select the sensor with ID 5250
  - set decimals, units and range as shown
![image](https://github.com/user-attachments/assets/21518c6c-47f7-4f74-8f31-06db4b5d4436)
![image](https://github.com/user-attachments/assets/5d9a7ae7-9c02-4d39-92e3-ef8fe7a62dbb)

### Done
These sensors can be displayed with widgets, used for alarms etc just like any other sensor.<br>
Enjoy.

![image](https://github.com/user-attachments/assets/6a26386b-b592-4cf9-a8bf-195bdf8196fd)
![image](https://github.com/user-attachments/assets/e8503767-69d2-400a-87ea-052b7ada6a7a)



