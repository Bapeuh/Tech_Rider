# Lady Liberty — Technical Rider

> [!NOTE]
> This document describes a configuration with **one room and one instance of the experience**.

## 1. Experience overview

**Lady Liberty** is a free-roam immersive VR experience designed for cultural venues and event operation. Visitors physically walk within a real space whose boundaries match the virtual environment.

## 2. Main specifications

| Item | Specification |
|---|---|
| Type | Multi-user standalone free-roam VR |
| Covered configuration | 1 room / 1 instance |
| Number of visitors | Up to 10 simultaneous visitors |
| Play area | 8 × 6.5 m |
| Recommended height | Approx. 3 m |
| Interaction | Hand tracking, no controllers |
| Movement | Free walking |
| Reference headset | HTC VIVE Focus Vision |
| Architecture | 1 server computer and 1 Wi-Fi access point for the room |

> [!TODO]
> To be confirmed for the delivered version: exact experience duration, minimum age and final hardware configuration.

## 3. Space requirements

### Room and play area

- Usable area: **8 × 6.5 m**
- Recommended height: **approximately 3 m**
- Flat, stable and non-reflective floor
- Obstacle-free area
- No protruding objects at head or arm level
- Controlled access during the experience
- Diffuse, stable and sufficiently even lighting
- High-contrast and varied visual references to ensure headset tracking

> [!IMPORTANT]
> Virtual boundaries must precisely match the physical room boundaries. The area must remain completely clear during operation.

> [!WARNING]
> Highly reflective, transparent or uniform surfaces, as well as significant lighting changes, may degrade tracking.

### Operator / technical area

Provide an area immediately adjacent to the room for:

- the server computer;
- the switch and Wi-Fi access point;
- power supplies and chargers;
- cleaning and maintenance equipment;
- an operator monitoring display, depending on the delivered configuration.

Technical equipment must be protected and inaccessible to the public.

### Reception and equipment area

Provide a separate area for:

- the safety briefing;
- headset distribution and adjustment;
- headset storage and charging;
- cleaning between groups;
- visitor exit without crossing the next group, where permitted by the venue layout.

## 4. Required equipment

### VR headsets

Reference configuration:

- **10 HTC VIVE Focus Vision headsets** for visitors;
- additional spare headsets recommended;
- washable or replaceable facial interfaces;
- suitable power supplies and chargers.

> [!NOTE]
> Adaptation to Pico 4 Ultra Enterprise may be considered after technical validation of the build and setup.

> [!IMPORTANT]
> The experience uses hand tracking. No controllers are required.

### Server computer

- **1 server computer** for the room;
- wired Ethernet connection to the experience network;
- monitor, keyboard and mouse for operation and maintenance;
- Internet access for services requiring online validation.

> [!TODO]
> Minimum and recommended server specifications must be confirmed for the delivered build.

### Network

- **1 Wi-Fi access point dedicated to the room**
- local network dedicated to the experience
- Gigabit Ethernet switch or better
- server computer connected through Ethernet
- headsets and server on the same subnet
- wired Internet connection available for license validation and support
- static IP addressing or DHCP reservations recommended for critical devices

> [!IMPORTANT]
> The experience Wi-Fi must be dedicated. The access point must not provide public or office Wi-Fi.

> [!WARNING]
> The number of headsets effectively supported by one access point depends on its model, radio configuration and the site's environment. A full-load test with all 10 headsets is mandatory before opening.

## 5. Network infrastructure

Architecture for one room:

```text
Internet connection
        |
Router / firewall
        |
Gigabit switch
   |            |
Server       Wi-Fi access point
                  |
             10 VR headsets
```

Recommendations:

- reserve one SSID for the experience;
- disable client isolation;
- avoid mesh networks and Wi-Fi repeaters;
- keep all devices on the same VLAN / subnet;
- document IP addresses and administration credentials;
- check for radio interference before installation.

## 6. Electrical requirements

Provide sufficient circuits and sockets to power:

- the server computer and monitor;
- the switch and access point;
- headset chargers;
- monitoring and maintenance equipment.

> [!TODO]
> Total electrical load and circuit distribution must be confirmed after approval of the final hardware configuration.

> [!NOTE]
> A UPS is recommended for the server and network equipment to prevent abrupt shutdowns during short power interruptions.

## 7. Installation

Installation includes at least:

1. inspecting and clearing the play area;
2. installing the server computer and network;
3. configuring the dedicated access point;
4. installing and updating the headsets;
5. mapping / calibrating the room on every headset;
6. checking that physical and virtual boundaries match;
7. testing hand tracking;
8. testing the network with all headsets connected;
9. completing a full session test under operating conditions;
10. approving operator and safety procedures.

> [!TODO]
> Installation, calibration and dismantling times must be confirmed according to the venue and delivered equipment.

## 8. Operation

Before opening each day:

- start and check the server;
- verify the network and access point;
- test a complete launch;
- check the battery, lenses, audio and tracking of each headset;
- ensure that the room is empty and clear.

Between groups:

- stop or reset the session;
- collect and inspect the headsets;
- clean the facial interfaces;
- quickly check battery levels and tracking;
- prepare the headsets for the next group.

> [!TODO]
> Minimum staffing and exact session frequency must be confirmed according to the visitor journey and venue organisation.

## 9. Safety instructions

Visitors must be informed that:

- walls and play boundaries generally correspond to real walls;
- they must never cross a boundary;
- the rest of the set is virtual;
- they must not sit or lean on virtual objects;
- they must walk and never run;
- they must immediately follow operator instructions.

Operators must supervise the room throughout the session and be able to interrupt the experience when necessary.

## 10. Maintenance

Daily checks:

- clean and disinfect facial interfaces;
- inspect lenses and straps;
- check headset battery levels;
- verify tracking and hand tracking;
- check the network and Internet connection;
- test the server and software build;
- visually inspect the room and tracking references.

Provide at least:

- spare facial interfaces;
- spare cables and power supplies;
- spare batteries or headsets according to the operating frequency;
- headset-compatible cleaning equipment.

## 11. Logistics

> [!TODO]
> To be confirmed: number of flight cases, dimensions, weights, exact equipment package, storage conditions and handling requirements for one room.

## 12. Software parameters

> [!TODO]
> Complete with the executables, launch arguments, server settings, start-up procedure, shutdown procedure and monitoring tools specific to the delivered build.

## 13. Installation checklist

- [ ] 8 × 6.5 m room available and clear
- [ ] Height and access approved
- [ ] Lighting approved
- [ ] Tracking references installed if required
- [ ] Server installed and tested
- [ ] Ethernet switch operational
- [ ] Dedicated access point configured
- [ ] SSID and subnet approved
- [ ] Internet connection available
- [ ] 10 headsets prepared and charged
- [ ] Spare headsets available
- [ ] Mapping completed on every headset
- [ ] Physical and virtual boundaries checked
- [ ] Hand tracking tested
- [ ] Full-load network test completed
- [ ] Full session tested
- [ ] Operator procedure approved
- [ ] Emergency shutdown procedure approved
- [ ] Cleaning equipment available

## 14. Document version

**Configuration:** 1 room / 1 instance  
**Version:** 0.1  
**Last update:** September 2026
