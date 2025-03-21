# Welcome to ESC S.Port (escsport)
General purpose ESC telemetry adapter for connection to FrSky s.port receivers

**USE AT YOUR OWN RISK**


### About escsport
Why? To get heli quality ESC telemetry for fixed wing applications.<br>
We use bettery capacity/consumption telemetry info to maximize flighttime and voltage telemetry monitor battery performance/warnings.<br>
So much better than flying by a timer.
This project addresses this need and is now standard equipment in my new builds.

### Release notes
- 2025.03.01 - Great news! Scorpion Tribunus III v16 FW now natively supports s.port, exposing ESC voltage, current, consomption, temperature and RPM<br>
No word yet if this feature will come to older Tribunus II ESC so for I will continue to use this for my Trib II planes
- 2024.12.10 - revised to accept power from Rx on port labled RX2 w/ VBT bridged to Vx (thanks Ben)

### Requirements
- an ESC w/ telemetry supported by RotorFlight (YGE, Scorpion, HobbyWing, Kontronik ...)
- small RotorFlight flight controller (FC) - e.g. [Matek G474-HLITE](https://www.mateksys.com/?portfolio=g474-hlite), it's 30x23x13mm 9g
- RotorFlight 2.0 (release 4.3.0) firmware - install using the [configurator](https://github.com/rotorflight/rotorflight-configurator/releases/tag/release%2F2.0.0)

### Caution
- some powersafe receivers e.g. the FrSky TD SR18 don't like power from an external source to appear on the +ve of the servo bus
  - removing the +ve lead from the ESC telemetry lead to the FC avoids this
 
### ESC
Some ESCs need to be told which protocol to use, e.g.
- Scorpion - set the ESC to "UNSC (Unsolicited)" telemetry mode
- YGE - set the ESC to "OpenYGE" telemetry mode
- See [RotorFlight ESC Telemetry](https://www.rotorflight.org/docs/Tutorial-Setup/ESC-Telemetry) for more info if needed

### The connections
- connect the FC with a 3 pin servo cable to one of the FrSky Rx's s.port ports
  - most FrSky Rx's can be configured to accept s.port devices on any free port
  - this connection will power the FC
- connect the ESC's telemetry signal and optionally the -ve/gnd, omit the +ve *this WILL damage certain setups*

### Hardware
- solder pins to the FC
  - RX2: 3-pin w/ bridge between VBT and adjacent Vx
  - RX3: 2-pin signal+gnd, again: the +ve pin is removed to avoid possible damage
![image](https://github.com/user-attachments/assets/fa35a123-bfec-491e-9a25-8da37c666e18)
![image](https://github.com/user-attachments/assets/9d9a6420-f58a-4172-bae1-869f298a1f72)
![image](https://github.com/user-attachments/assets/35b6e4d3-de91-447d-965e-f52b1f13384c)
![image](https://github.com/user-attachments/assets/34a8832a-caa5-481d-a223-452b6e793b8b)
![image](https://github.com/user-attachments/assets/7ed86e01-4f01-4703-b073-eb7b1f4c31fc)
![image](https://github.com/user-attachments/assets/35888c19-0848-4bde-98de-00fdca65a4fc)

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
- connect the ESC telemetry cable to the 2-pin RX3 port
- connect the 3-pin RX2 port to a port on the FrSky Rx that's been configured to accept s.port
![image](https://github.com/user-attachments/assets/caad0cd7-78fc-4231-be68-71dd67d8ab18)
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



