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

Validated minimum configuration:

| Component | Minimum specification |
|---|---|
| Processor | Intel Core i7-3770 at 3.40 GHz |
| Memory | 32 GB RAM |
| System storage | 250 GB SSD (233 GB usable on the reference computer) |
| Additional storage | 1 TB HDD (932 GB usable on the reference computer) |
| Graphics card | NVIDIA GeForce GTX 970, 4 GB |
| System architecture | 64-bit operating system, x64 processor |

> [!NOTE]
> The reference computer used to validate this configuration is named `BKL01`. Windows device and product IDs specific to that computer are not required to reproduce the installation.

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

## 8. Software installation and initial setup

Three software components must be installed:

1. the experience and server software on the Windows computer;
2. the experience APK on every headset;
3. the control APK on the Android tablet.

### 8.1 Server computer installation

1. Install the supplied PC version of **Lady Liberty**.
2. Create two shortcuts to the experience executable.
3. Add the following arguments to the **Target** field of each shortcut, after the executable path.

Temporary **NoName** server shortcut:

```text
-server -team=gm
```

**ROOM01** server shortcut:

```text
-server -team=gm -sessionname=ROOM01
```

> [!IMPORTANT]
> The shortcut without `-sessionname` opens the **NoName** server. It is used to detect and configure headsets before assigning them to the `ROOM01` room.

### 8.2 Initial server login

When launching the experience on the computer for the first time:

1. enter the supplied credentials, including the email address and password;
2. check that the credentials have been saved correctly;
3. close the application if required;
4. launch the **NoName** server;
5. then launch the **ROOM01** server.

> [!WARNING]
> Do not close the NoName server until all headsets have been assigned to the ROOM01 session.

### 8.3 Headset installation and configuration

1. Install the supplied APK on every headset.
2. Launch the application in the headset.
3. On its first launch, the headset automatically connects to the **NoName** server.
4. In the server interface, click the number of the detected headset.
5. Edit the required settings:
   - headset number;
   - player colour;
   - destination server / session, in this case `ROOM01`.
6. Close the settings window to apply the changes.

If the session was changed, the application closes in the headset. The next time it launches, it should automatically connect to the selected session.

Once all headsets have been assigned to `ROOM01` and their connections have been checked, the **NoName** server can be closed.

### 8.4 Headset kiosk mode

Configure every headset in **kiosk mode** and set Lady Liberty as the application that launches automatically.

> [!IMPORTANT]
> Kiosk mode allows the application to restart automatically whenever it closes. This occurs, for example, after changing a headset's session or language: the application closes and then relaunches with the new setting.

### 8.5 Android tablet installation and connection

1. Install the supplied control APK on the Android tablet.
2. Check that the tablet is connected to the same local network as the server.
3. Launch the application.
4. At the top of the screen, select the room to manage from the list of available rooms.
5. Select `ROOM01`.
6. Tap **Connect**.

The tablet can then access the control functions available for that room.

### 8.6 Final check

- [ ] Credentials are saved on the server
- [ ] NoName and ROOM01 shortcuts work
- [ ] The ROOM01 server is visible on the network
- [ ] The APK is installed on all headsets
- [ ] Every headset has the correct number and colour
- [ ] All headsets connect to ROOM01
- [ ] Kiosk mode correctly relaunches the application
- [ ] The control APK is installed on the tablet
- [ ] The tablet can see and connect to ROOM01
- [ ] The NoName server is closed after configuration

## 9. Operation

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

## 10. Safety instructions

Visitors must be informed that:

- walls and play boundaries generally correspond to real walls;
- they must never cross a boundary;
- the rest of the set is virtual;
- they must not sit or lean on virtual objects;
- they must walk and never run;
- they must immediately follow operator instructions.

Operators must supervise the room throughout the session and be able to interrupt the experience when necessary.

## 11. Maintenance

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

## 12. Logistics

> [!TODO]
> To be confirmed: number of flight cases, dimensions, weights, exact equipment package, storage conditions and handling requirements for one room.

## 13. Software parameters

Currently documented launch arguments:

```text
-server -team=gm
-server -team=gm -sessionname=ROOM01
```

> [!TODO]
> Complete with the exact executable name, full shutdown procedure and monitoring tools specific to the delivered build.

## 14. Installation checklist

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

## 15. Document version

**Configuration:** 1 room / 1 instance  
**Version:** 0.2  
**Last update:** September 2026
