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

The **Lady Liberty** delivery folder contains three subfolders corresponding to the three components to be installed:

```text
Lady_Liberty/
├── Tablette_Android/
├── Game_Windows/
└── Game_Android/
```

| Folder | Destination | Function |
|---|---|---|
| `Tablette_Android` | Android tablet | Session control interface |
| `Game_Windows` | Server computer | Server and operator interface |
| `Game_Android` | VR headsets | Lady Liberty visitor application |

> [!IMPORTANT]
> The server computer, tablet and all headsets must be connected to the same local network and placed on the same subnet.

### 8.1 Windows server installation

The `Game_Windows` folder contains the server application installer, including:

```text
Lady Liberty_1.0.0.5_Installer.exe
Lady Liberty_1.0.0.5_Installer-1.bin
```

Both files must remain in the same folder during installation.

#### Installation procedure

1. Open the `Game_Windows` folder.
2. Double-click `Lady Liberty_1.0.0.5_Installer.exe`.
3. Follow the steps in the installation wizard.
4. When prompted, enter the session name assigned to the room.

Example:

```text
Session01
```

> [!IMPORTANT]
> The session name must be exactly the same on the server and in the `setup.ini` file used to install the headsets. A simple name without spaces or special characters is recommended.

#### Initial login

Once installation is complete:

1. launch the Lady Liberty application;
2. enter the supplied email address and password;
3. check that the credentials have been saved correctly;
4. check that the server starts with the configured session name.

The named server shortcut uses the following arguments:

```text
-server -team=gm -sessionname=Session01
```

Replace `Session01` with the name selected during installation.

### 8.2 Android tablet installation

The `Tablette_Android` folder contains the control interface APK and the files required for its installation.

#### Installation procedure

1. install the supplied APK on the Android tablet;
2. connect the tablet to the same local network as the server and headsets;
3. launch the control application.

The first screen displays the sessions detected on the network and their current status.

To access a room:

1. select the required session from the list;
2. tap **Connect**;
3. wait for the session management interface to open.

The tablet interface displays the same main information as the operator interface on the server computer.

> [!WARNING]
> If no session appears, check that the tablet is connected to the correct network, that the server is running and that all devices are on the same subnet.

### 8.3 Installing the application on the headsets

The `Game_Android` folder contains, among other files:

```text
setup.ini
LadyLiberty-Android-Shipping-arm64.apk
Install_LadyLiberty_WithID.bat
Install_LadyLiberty.bat
```

It may also contain additional files or folders required for installation. They must remain in their original locations.

#### Configuring the session name

Before installing the application on the headsets:

1. open the `setup.ini` file;
2. enter the session name;
3. use exactly the same name as the one configured on the server;
4. save the file before running the installation script.

Example:

```text
Session01
```

> [!IMPORTANT]
> Any difference in the name, letter case or spelling will prevent the headset from automatically joining the correct session.

### 8.4 Installation with direct ID assignment

To install the application and directly assign a number to the headset, use:

```text
Install_LadyLiberty_WithID.bat
```

This script assigns an ID to the headset during installation. The ID will then appear in the operator interface on both the computer and tablet.

Recommended procedure:

1. connect only one headset to the computer;
2. check that the headset is correctly detected;
3. run `Install_LadyLiberty_WithID.bat`;
4. enter the requested ID;
5. wait for confirmation that installation is complete;
6. disconnect the headset;
7. repeat the operation with the next headset, using a different ID.

> [!IMPORTANT]
> Every headset in the same installation must have a unique ID.

### 8.5 Installation without direct ID assignment

To install the application without immediately assigning a number to the headset, use:

```text
Install_LadyLiberty.bat
```

The headset number can then be changed from the operator interface.

This method may be used when IDs will be assigned later or when the final configuration is performed from the server.

### 8.6 Installing headsets through an MDM

The APK may also be deployed directly to the headsets using an MDM platform.

With this method:

- all headsets initially receive ID `72`;
- all headsets are initially assigned to the `NoName` session;
- their IDs and sessions must then be configured manually from the operator interface.

> [!WARNING]
> Until they have been reconfigured, multiple headsets may appear with the same ID `72`. They must be handled individually and assigned unique IDs.

### 8.7 Creating a temporary NoName server

To detect and configure headsets installed through an MDM, run both of the following at the same time:

- the server assigned to the room, for example `Session01`;
- a temporary server without a session name, referred to as `NoName`.

#### Creating the NoName shortcut

1. locate the Lady Liberty shortcut on the server computer desktop;
2. copy the shortcut;
3. rename the copy, for example:

```text
Lady Liberty — NoName
```

4. right-click the new shortcut;
5. open **Properties**;
6. in the **Target** field, completely remove the following argument:

```text
-sessionname=Session01
```

The NoName server shortcut must retain only the following arguments:

```text
-server -team=gm
```

The room server shortcut must retain:

```text
-server -team=gm -sessionname=Session01
```

### 8.8 Assigning headsets to the correct session

1. launch the `NoName` server;
2. launch the named server, for example `Session01`;
3. launch the Lady Liberty application on the headset;
4. wait for the headset to appear in the NoName server interface;
5. click the headset ID;
6. in the configuration window, edit:
   - the headset ID;
   - the player colour, if required;
   - the destination session;
7. select the session assigned to the room, for example `Session01`;
8. close the configuration window to save the changes.

When the settings are changed, the Lady Liberty application closes automatically on the headset.

Relaunch the application to load the new settings. The headset should then automatically connect to the selected session.

Repeat this procedure for every headset.

Once all headsets:

- have a unique ID;
- are assigned to the correct session;
- appear correctly on the named server;

the `NoName` server can be closed.

> [!IMPORTANT]
> Do not close the NoName server until all headsets have been configured and checked.

### 8.9 Configuring kiosk mode

Kiosk mode is strongly recommended on every headset.

Lady Liberty must be configured as an allowed application and as the application that launches automatically.

Kiosk mode allows the application to restart automatically whenever it closes, including after:

- an ID change;
- a session change;
- a language change;
- an unexpected application shutdown.

When a setting is changed, the application closes and then automatically restarts with the new configuration.

> [!NOTE]
> Without kiosk mode, the operator must manually relaunch Lady Liberty on the headset after each change that requires the application to restart.

### 8.10 Final installation check

Before approving the installation, check the following:

- [ ] The Windows server is installed.
- [ ] The email address and password have been saved.
- [ ] The server starts with the correct session name.
- [ ] The tablet is connected to the same network as the server and headsets.
- [ ] The control application is installed on the tablet.
- [ ] The tablet detects the configured session.
- [ ] The Lady Liberty application is installed on every headset.
- [ ] The `setup.ini` file contains the correct session name.
- [ ] Every headset has a unique ID.
- [ ] Every headset is assigned to the correct session.
- [ ] All headsets appear in the operator interface.
- [ ] All headsets appear in the tablet application.
- [ ] Kiosk mode correctly relaunches Lady Liberty.
- [ ] The NoName server is closed after configuration.
- [ ] A complete session has been tested with all headsets.

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
-server -team=gm -sessionname=Session01
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
**Version:** 0.3  
**Last update:** September 2026
