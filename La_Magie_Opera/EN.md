# La Magie Opéra — Technical Rider

## 1. Experience overview

**La Magie Opéra** is a multi-user free-roam VR experience designed for cultural venues and event operation.

## 2. Main specifications

| Item | Specification |
|---|---|
| Type | PCVR Free-Roam |
| Nombre de joueurs | Up to 12 simultaneous players |
| Durée en casque | Approx. 23 min 30 sec |
| Durée opérationnelle recommandée | 40 minutes per session including onboarding and offboarding |
| Âge recommandé | 10+ |
| Interaction | Hand tracking, no controllers |
| Déplacements | Free walking inside the play area |
| Accessibilité PMR | Possible depending on venue layout |

> [!IMPORTANT]
> Player count and session architecture must be validated for each deployment.

## 3. Space requirements

### Play area

- Recommended area : **8 × 8 m**
- Obstacle-free area
- Recommended ceiling height : **above 2,8 m**
- Flat and stable floor
- Diffuse and sufficiently even lighting
- High-contrast and varied visual references to improve tracking

### Operator / technical area

- Recommended technical room : **15 à 20 m²**
- Access to computers, network, power and maintenance equipment
- Restricted from public access

### Waiting area

- Recommended area : **15 à 20 m²**

## 4. Required equipment

### VR headsets

Recommended headsets :

- HTC VIVE Focus 3
- HTC VIVE Focus Vision

Pico 4 Ultra Enterprise may be used in selected configurations after technical validation.

> [!IMPORTANT]
> The experience uses hand tracking. No controllers are required.

### Computers

PCVR architecture with :

- 1 server computer
- 1 client computer per player depending on the selected deployment architecture
- GPU and CPU suitable for the delivered build

> [!TODO]
> Minimum and recommended computer specifications must be confirmed depending on the software build and hardware fleet.

### Network

- Dedicated local network
- Dedicated Wi-Fi 6E
- Computers connected through Ethernet
- All devices must be on the same subnet
- Wired Internet access required for license validation

## 5. Network infrastructure

- Gigabit Ethernet switch or better
- Dedicated Wi-Fi access points
- Static IP addressing or DHCP reservations recommended for critical devices
- Server and clients on the same subnet

## 6. Electrical requirements

Recommended total power capacity for a complete installation : **approximately 10 kW**

> [!IMPORTANT]
> Final electrical sizing must be validated with the venue technical team.

## 7. Installation

Indicative timing :

- hardware installation : **environ 5 h**
- calibration and testing : **environ 3 h**
- dismantling : **environ 5 h**

Each headset must be calibrated inside the real play space. Tracking must be tested across the entire play area.

### Suspended equipment and lighting

The following equipment is suspended above the play area, which is marked on the floor by a rectangle made of **8 linoleum strips, each 80 cm wide**.

> [!TODO]
> The final width and arrangement of the linoleum strips must be confirmed.

#### Wi-Fi routers

- **4 routers**, mounted on **2 separate trusses**, with 2 routers per truss
- spacing between the two routers on each truss: **3.5 m**
- distance between the two trusses: **2.5 to 3 m**
- rigging height: **approximately 5 m above floor level**

#### Lighting

- **4 × 1 kW horizon floodlights**, mounted on **2 trusses separate from the router trusses**, with 2 floodlights per truss
- spacing between the two floodlights on each truss: **3 m**
- distance between the two trusses: **2.5 to 3 m**
- rigging height: **approximately 5.5 to 6 m above floor level**
- intensity: **75%**
- used **without diffusers**

> [!IMPORTANT]
> The trusses, routers and lighting fixtures must be rigged or approved by qualified personnel, in accordance with venue safety regulations and load capacities.

## 8. Operation

Recommended configuration :

- **2 operators**

Minimum configuration :

- **1 operator**, only with a strict 40-minute session workflow.

## 9. Safety

The site must remain clear and compliant with venue safety requirements. Operators must supervise visitors throughout the session.

## 10. Maintenance

Daily checks should include :

- facial interface cleaning ;
- lens inspection ;
- tracking verification ;
- network check ;
- headset battery check ;
- server and client test before opening.

## 11. Logistics

Configuration provided for selected deployments :

- **2 flight cases**
- indicative dimensions : **60 × 160 × 80 cm**

> [!NOTE]
> Exact logistics depend on the hardware package included in the deployment.

## 12. Software parameters

Example launch arguments :

```bash
-server
-client
-team=GM
-team=Player
-team=Spectator
-team=TeleportPlayer
```

Player example :

```bash
-client -team=player -id=5 -color=orange
```

> [!WARNING]
> Available arguments may vary depending on the software build.

## 13. Installation checklist

- [ ] 8 × 8 m play area cleared
- [ ] Lighting validated
- [ ] 4 routers mounted on 2 trusses according to the rigging plan
- [ ] 4 × 1 kW horizon floodlights mounted on 2 dedicated trusses
- [ ] Heights, spacing, 75% intensity and absence of diffusers checked
- [ ] Rigging and suspended loads approved by the venue
- [ ] Computers installed
- [ ] Ethernet network operational
- [ ] Dedicated Wi-Fi configured
- [ ] Internet connection available
- [ ] Headsets charged
- [ ] Mapping / calibration completed
- [ ] Server launched
- [ ] Clients launched
- [ ] Full session tested
- [ ] Operator procedure validated

## 14. Document version

**Version:** 0.2  
**Last update:** September 2026
