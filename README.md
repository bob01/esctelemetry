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

### Connections
- connect the FC with a 3 pin servo cable to one of the FrSky Rx's s.port ports
  - most FrSky Rx's can be configured to accept s.port devices on any free port
  - this connection will power the FC
- connect the ESC's telemetry signal and optionally the -ve/gnd, omit the +ve *this will damage certain setups)

