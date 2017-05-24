# Hacking Cars with Python by Eric Evenchick
## Disclaimer
* You can brick a car via diagnostics
* You can modify safety critical systems
* Some mods are illegal - odometers, etc
## Cars are computers
* Safety - airbags (passenger weight, seatbelt, speed, can vary airbag deployment)
* Advanced features (autopilot)
* Emissions (main reason we have computers in cars)
## Cars are networks - up to 100 ECUs (electronic control units)
* Typically CAN (Controller Area Network) bus
## CAN bus
* Controller Area Network
* Low cost, integrated controllers
* Types
 * High speed (differential) [important stuff]
 * Low speed (single ended)
 * Fault tolerant
 * CAN FD (flexible data)
## CAN
* Controller: network node
* Bus: collection of controllers
* Frame: PDU containing
 * ID
 * Type
 * Data length code (up to 8)
 * Data (8 bytes)
## Comm Types
### Operational
* Used during normal ops
* Relays data between ECUs
* Periodic statically defined frames
* Proprietary encoding
* Let's us get vehicle state, log data, control automotive components
### Diagnostics
* Used at specific times, not normal ops
* Allows special interactions with ECUs
* Client/server protocol
* Used during manufacturing, service, end of life, forensics, requires specialized tools
## ISOTP
* How do we encode a 17 char VIN?
* Combines frames into longer data
* Up to 4095 bytes
* Flow control
* Also called CANTP
## Diag Standards
* ODB-II
 * Read params (PIDs)
 * Clear fault codes
 * Full list of PIDs on Wikipedia
* UDS
## ODB Session
* Request: [mode, pid]
* Response: [mode +0x40, pid, data...]
## UDS - used by OEM for their tools
 * Client/server protocol for diagnostics
 * Client = scan tool
 * Server = ECU
 * Can read/write data easily
## Tools
 * Scan tools
  * Cheap options: usually OBD only
 * USB to CAN adapters
  * Still need ISOTP and UDS, so instead..
## `pyvit`
 * Python vehicle interface toolkit
 * CAN, ISOTP, and UDS support
## Practical stuff
* Get an ODB-II device
* Right to repair
* OpenGarages, DEF CON car hacking village
## Future
* Ethernet based diagnostics: DoIP
* Vehicle APIs
 * Tesla
 * Ford OpenXC
