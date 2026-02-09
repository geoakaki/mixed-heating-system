# Heating System Configuration (5+5 Circuits)

## Overview

Combined manifold/distribution system for mixed high-temperature (radiators) and low-temperature (floor heating) circuits from a single boiler. Updated configuration with 5 radiator circuits and 5 floor heating circuits.

---

## System Configuration

```
Boiler (75-80°C)
      │
      ▼
┌─────────────────────────────────────┐
│ R553ZY005                           │
│ Pre-assembled brass manifold        │
│ HIGH TEMP - 5 circuits (radiators)  │
│ Connection: 1" × Base 18            │
└──────────────┬──────────────────────┘
               │ 1" pipe
               ▼
┌─────────────────────────────────────┐
│ R559NY005                           │
│ Pre-assembled manifold group        │
│ LOW TEMP - 5 circuits (floor heat)  │
│ Includes: mixing valve + ErP pump   │
│ + cabinet (1000×605×110mm)          │
│ Reduces temp from 75-80°C → 40-45°C │
└─────────────────────────────────────┘
```

---

## 1. Heat Generator (Boiler)

| Specification | Value |
|---------------|-------|
| **Unit** | Ariston Clas One 30 |
| **Capacity** | 30kW |
| **Operational Mode** | High Temperature Output |
| **Set Temperature** | 75-80°C |

### Technical Notes

- The boiler must be set to high temperature to satisfy the radiators
- The boiler's internal pump provides primary pressure and flow to the main system
- Mixed return temperatures from both circuits are handled efficiently

---

## 2. Parts List

### Hydraulic — Floor Heating (Low-Temp)

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **R559NY005** | Pre-assembled manifold group, 5 circuits | 1 | Includes: brass manifold with flow meters (0.5-5 L/min), 3-way mixing valve (M30×1.5mm), ErP variable-speed pump, safety thermostat K373, air vents, drain cocks, thermometers, galvanized steel cabinet (1000×605×110mm) |
| **K281X012** | Mixing valve actuator, 24V, 0-10V | 1 | M30×1.5mm thread — mounts on 3-way valve. **NOT included with R559NY005** |
| **R179AM** | Pipe adapters, Base 18 (multilayer/plastic) | 10 pcs | 5 supply + 5 return. Choose size per pipe OD (e.g., R179MX024 for 16×2mm) |

### Hydraulic — Radiators (High-Temp)

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **R553ZY005** | Pre-assembled brass manifold, 5 outlets | 1 | 1"×Base 18, on R588Z reduced brackets |
| **R500Y222** | Flush-mount cabinet | 1 | 600×650-740×85-140mm, for radiator manifold |
| **R179AM** | Pipe adapters, Base 18 (multilayer/plastic) | 10 pcs | 5 supply + 5 return. Choose size per pipe OD |

### Actuators

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **R473X221** | Thermo-electric actuator, 230V NC | **10** | 5 for radiators (R553ZY005) + 5 for floor heating (R559NY005). Replaces manual handwheels on return manifold |

### Controls — Danfoss Icon2

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **Danfoss Icon2 Main Controller** (088U2100) | 230V, 15-channel controller | 1 | 10 of 15 outputs used, 5 spare |
| **Danfoss Wireless Thermostat** | Room temperature sensor | Per room | 1 per controlled zone |

### Mixing Valve Control (for R559NY005)

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **K281X012** | 24V, 0-10V actuator for mixing valve | 1 | Controls 3-way valve on R559NY005 |
| **KPM30 or KPM31** | Electronic regulation module | 1 | Controls K281 based on temperature setpoint |
| **K363P** | Delivery temperature probe | 1 | Typically included with KPM30/31 |

---

## 3. R559NY005 Specifications

| Spec | Value |
|------|-------|
| Temperature range | 5-110°C |
| Max working pressure | 10 bar (6 bar at pump) |
| Primary connection | 1" (G 1") |
| Secondary outlets | M18 fine thread (Base 18) |
| Outlet center distance | 50mm |
| Mixing valve connection | M30×1.5mm |
| Flow meter range | 0.5-5 L/min per circuit |
| Manifold material | Drawn brass MS63 |
| Cabinet dimensions | 1000×605×110mm |
| Cabinet material | Galvanized sheet steel, powder-coated white (~RAL 9010) |
| Pump | ErP 2009/125/EC compliant, self-modulating/variable-frequency |

### What's Included in R559NY005

**Supply Manifold (R553M type):**
- Brass manifold with front-mounted shut-off/balancing valves with mechanical memory
- Integrated flow meters (0.5-5 L/min scale) on each circuit
- Universal flow adjustment key (R558NY) included

**Return Manifold (R553V type):**
- Brass manifold with manual ball valve isolation on each circuit
- Pre-configured for actuator installation (handwheels removable for R473X221)

**Mixing/Intermediate Group:**
- 3-way mixing valve with M30×1.5mm connection
- Safety thermostat K373 (with immersion probe)
- Fill/drain valves with hose connections
- Manual air vent valves
- Drain cocks
- Supply and return thermometers

**Circulation Pump:**
- ErP compliant high-efficiency variable-speed pump (pre-installed)

**Enclosure:**
- Metal cabinet with mounting brackets and rubber vibration dampers
- Two collector end caps (R554B) with TG seals
- Circuit identification label set

### What's NOT Included (Must Order Separately)

| Accessory | Code | Required |
|-----------|------|----------|
| Mixing valve actuator | **K281X012** | Yes |
| Pipe adapters | **R179AM / R178 / R179** | Yes |
| Thermo-electric actuators | **R473X221** | Yes (for zone control) |
| Insulation | **R559W** | Optional |

---

## 4. R553ZY005 Manifold Specifications

| Spec | Value |
|------|-------|
| Max working pressure | 10 bar |
| Temperature range | 5-110°C |
| Main connection | 1" |
| Outlet connection | Base 18 (use R178, R179, R179AM adapters) |
| Outlet center distance | 50mm |
| Material | Brass body, EPDM gaskets, galvanized steel brackets |
| Supply manifold | Balancing lockshield valves with mechanical memory |
| Return manifold | Interception valves for thermo-electric actuators |

### Technical Notes

> **Why R553ZY005:** The return bar comes with thermostatic valves that properly mate with R473X221 actuators. Standard brass bars lack these valve bodies and cannot accept actuators directly.

---

## 5. Zone A: High-Temperature Circuit (Radiators)

### R553ZY005 Circuit Assignment

| Outlet | Room | Control Method | Actuator | Thermostat |
|--------|------|----------------|----------|------------|
| 1 | Bedroom 1 Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 2 | Bedroom 2 Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 3 | Office Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 4 | Bathroom 1 Towel Rail | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 5 | Bathroom 2 Towel Rail | Danfoss Icon2 | R473X221 | Danfoss Wireless |

### Technical Notes

- All 5 radiator circuits are now electronically controlled via Danfoss Icon2
- Bathroom towel rails upgraded from manual TRV to actuator control for full system integration
- **Hydraulic bypass consideration:** With all circuits on actuators, if all zones close simultaneously the system has no bypass. Consider adding a differential pressure bypass valve on the boiler loop or enabling the boiler's built-in bypass (if available)

---

## 6. Zone B: Low-Temperature Circuit (Floor Heating)

### R559NY005 Circuit Assignment

| Outlet | Zone | Control Method | Actuator | Thermostat |
|--------|------|----------------|----------|------------|
| 1 | Floor Zone 1 | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 2 | Floor Zone 2 | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 3 | Floor Zone 3 | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 4 | Floor Zone 4 | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 5 | Floor Zone 5 | Danfoss Icon2 | R473X221 | Danfoss Wireless |

### How the R559NY005 Reduces Temperature

The R559NY005 contains a **3-way mixing valve** that blends two water streams:

| Port | Source | Temperature |
|------|--------|-------------|
| **HOT inlet** | From R553ZY005 (via 1" pipe) | 75-80°C |
| **COLD inlet** | Return from floor loops | ~25-35°C |
| **MIXED outlet** | To floor manifold (via pump) | 40-45°C |

**Mixing Process:**
1. Hot water from high-temp manifold enters the mixing valve
2. Cool return water from floor loops is recirculated back
3. K281X012 actuator (controlled by KPM30/31) adjusts blend ratio based on K363P temperature probe
4. ErP variable-speed pump pushes the mixed water through to the floor manifold
5. Floor manifold distributes to 5 floor loops
6. Floor absorbs heat, water cools, returns to mixing valve

### Recommended Settings (R559NY005)

| Valve | Setting |
|-------|---------|
| Primary lockshield valve | 2 turns open |
| Secondary lockshield valve | Fully open |

---

## 7. R473X221 Actuator Specifications

| Spec | Value |
|------|-------|
| Type | Normally Closed (N.C.) |
| Voltage | 230 Vac 50Hz |
| Power | 2.5W per actuator |
| Max peak current | ≤ 0.25 A |
| Steady current (after 12 min) | ≤ 0.015 A |
| Wire | 2-conductor (Brown=L, Blue=N) |
| Wire length | 1 m |
| Opening/closing time | ~3 min at 25°C |
| Connection | Quick-fit with R453Y002 ring nut (included) |
| Dimensions | 71 × 68 × 51 mm |

### Danfoss Icon2 + R473X221 Compatibility

- Both operate at **230V** — direct connection possible
- R473X221 is **Normally Closed** — valve closes safely when no power
- Simple 2-wire connection to Icon2 output channels
- Total load: 10 × 2.5W = **25W** (well within Icon2 capacity of 15 × 2.5W = 37.5W)

---

## 8. Controls Ecosystem (Danfoss Icon2)

### Central Controller

| Specification | Value |
|---------------|-------|
| **Unit** | Danfoss Icon2 Main Controller (088U2100) |
| **Voltage** | 230V |
| **Total Channels** | 15 |
| **Channels Used** | 10 (5 spare) |
| **Boiler Relay** | Yes (voltage-free contact, max 2A / 230V) |
| **Pump Relay** | Yes (PWR1, up to 100W at 230V) |
| **Location** | Near the manifolds |

### Danfoss Icon2 Output Assignment

| Output | Actuator Location | Zone | Thermostat |
|--------|-------------------|------|------------|
| 1 | R553ZY005 Outlet 1 | Bedroom 1 Radiator | Bedroom 1 |
| 2 | R553ZY005 Outlet 2 | Bedroom 2 Radiator | Bedroom 2 |
| 3 | R553ZY005 Outlet 3 | Office Radiator | Office |
| 4 | R553ZY005 Outlet 4 | Bathroom 1 Towel Rail | Bathroom 1 |
| 5 | R553ZY005 Outlet 5 | Bathroom 2 Towel Rail | Bathroom 2 |
| 6 | R559NY005 Outlet 1 | Floor Zone 1 | Zone 1 |
| 7 | R559NY005 Outlet 2 | Floor Zone 2 | Zone 2 |
| 8 | R559NY005 Outlet 3 | Floor Zone 3 | Zone 3 |
| 9 | R559NY005 Outlet 4 | Floor Zone 4 | Zone 4 |
| 10 | R559NY005 Outlet 5 | Floor Zone 5 | Zone 5 |

### Input Signals (Wireless Thermostats)

| Room | Signal Flow |
|------|-------------|
| **Bedroom 1** | Thermostat → Controller → Opens R553ZY005 Outlet 1 Actuator → Fires Boiler |
| **Bedroom 2** | Thermostat → Controller → Opens R553ZY005 Outlet 2 Actuator → Fires Boiler |
| **Office** | Thermostat → Controller → Opens R553ZY005 Outlet 3 Actuator → Fires Boiler |
| **Bathroom 1** | Thermostat → Controller → Opens R553ZY005 Outlet 4 Actuator → Fires Boiler |
| **Bathroom 2** | Thermostat → Controller → Opens R553ZY005 Outlet 5 Actuator → Fires Boiler |
| **Floor Zone 1** | Thermostat → Controller → Opens R559NY005 Outlet 1 Actuator → Fires Boiler |
| **Floor Zone 2** | Thermostat → Controller → Opens R559NY005 Outlet 2 Actuator → Fires Boiler |
| **Floor Zone 3** | Thermostat → Controller → Opens R559NY005 Outlet 3 Actuator → Fires Boiler |
| **Floor Zone 4** | Thermostat → Controller → Opens R559NY005 Outlet 4 Actuator → Fires Boiler |
| **Floor Zone 5** | Thermostat → Controller → Opens R559NY005 Outlet 5 Actuator → Fires Boiler |

---

## 9. Flow Diagram

```
                    SUPPLY SIDE                 RETURN SIDE
                         │                           │
    ┌────────────────────┴───────────────────────────┴─────────────────┐
    │                         BOILER                                   │
    │                  Ariston Clas One 30                              │
    └────────────────────┬───────────────────────────┬─────────────────┘
                         │ HOT (75-80°C)             ▲
                         ▼                           │
    ┌────────────────────────────────────────────────┴─────────────────┐
    │  R553ZY005 - HIGH TEMP MANIFOLD (5 circuits)                     │
    │  Cabinet: R500Y222 (600×650×110mm)                               │
    │  ┌─────┬─────┬─────┬─────┬─────┐                                 │
    │  │  1  │  2  │  3  │  4  │  5  │                                 │
    │  └──┬──┴──┬──┴──┬──┴──┬──┴──┬──┘                                 │
    │     │     │     │     │     │                                    │
    │   Bed1  Bed2  Office Bath1 Bath2                                 │
    │  R473  R473  R473  R473  R473   ← All actuators on return bar   │
    └────────────────────┬────────────────────────────┬────────────────┘
                         │                            ▲
                         ▼                            │
    ┌─────────────────────────────────────────────────┴────────────────┐
    │  R559NY005 - PRE-ASSEMBLED FLOOR HEATING GROUP (5 circuits)      │
    │  Cabinet: Included (1000×605×110mm)                              │
    │  ┌─────────────────────────────────────────────────────────┐     │
    │  │ ┌─────────┐  ┌──────────────┐  ┌──────────────────┐    │     │
    │  │ │ 3-way   │──│ ErP Variable │──│ 5-circuit brass  │    │     │
    │  │ │ mixing  │  │ Speed Pump   │  │ manifold + flow  │    │     │
    │  │ │ valve   │  │              │  │ meters           │    │     │
    │  │ └─────────┘  └──────────────┘  └──────────────────┘    │     │
    │  │                                 ┌─────┬─────┬─────┬─────┬────┐│
    │  │                                 │  1  │  2  │  3  │  4  │  5 ││
    │  │                                 └──┬──┴──┬──┴──┬──┴──┬──┴──┬─┘│
    │  │                                    │     │     │     │     │  │
    │  │                                  Zone1 Zone2 Zone3 Zone4 Zone5│
    │  │                                  R473  R473  R473  R473  R473│
    │  └─────────────────────────────────────────────────────────┘     │
    └─────────────────────────────────────────────────────────────────┘
```

---

## 10. Electrical Wiring Diagram

```
┌──────────────────────────────────────────────────────────────────────────────────┐
│                       DANFOSS ICON2 MAIN CONTROLLER (230V)                       │
│                              088U2100 - 15 Channels                              │
│  ┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐┌────────┐         │
│  │Output 1││Output 2││Output 3││Output 4││Output 5││Output 6││Output 7│  ...    │
│  │ (230V) ││ (230V) ││ (230V) ││ (230V) ││ (230V) ││ (230V) ││ (230V) │         │
│  └───┬────┘└───┬────┘└───┬────┘└───┬────┘└───┬────┘└───┬────┘└───┬────┘         │
└──────┼─────────┼─────────┼─────────┼─────────┼─────────┼─────────┼──────────────┘
       │         │         │         │         │         │         │
  ┌────┴───┐┌────┴───┐┌────┴───┐┌────┴───┐┌────┴───┐┌────┴───┐┌────┴───┐
  │R473X221││R473X221││R473X221││R473X221││R473X221││R473X221││R473X221│  ...
  │Bedroom1││Bedroom2││ Office ││ Bath 1 ││ Bath 2 ││Floor Z1││Floor Z2│
  └────┬───┘└────┬───┘└────┬───┘└────┬───┘└────┬───┘└────┬───┘└────┬───┘
       │         │         │         │         │         │         │
       ▼         ▼         ▼         ▼         ▼         ▼         ▼
  R553ZY005 R553ZY005 R553ZY005 R553ZY005 R553ZY005 R559NY005 R559NY005
  Outlet 1  Outlet 2  Outlet 3  Outlet 4  Outlet 5  Outlet 1  Outlet 2
  (Radiator)(Radiator)(Radiator)(Towel)  (Towel)   (Floor)   (Floor)

  Outputs 8-10: R559NY005 Outlets 3-5 (Floor Zones 3-5)
  Outputs 11-15: Spare

  ~~~~~~~~~~~~~~~~~~~~~~~~~ Wireless Communication ~~~~~~~~~~~~~~~~~~~~~~~~~

  ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐ ┌─────────┐
  │ Danfoss │ │ Danfoss │ │ Danfoss │ │ Danfoss │ │ Danfoss │  + up to 5
  │Wireless │ │Wireless │ │Wireless │ │Wireless │ │Wireless │  more for
  │Thermost.│ │Thermost.│ │Thermost.│ │Thermost.│ │Thermost.│  floor zones
  │Bedroom 1│ │Bedroom 2│ │ Office  │ │ Bath 1  │ │ Bath 2  │
  └─────────┘ └─────────┘ └─────────┘ └─────────┘ └─────────┘
```

### R473X221 Wiring (2-wire connection)

- **Brown wire** → Live (L) from Icon2 output
- **Blue wire** → Neutral (N) common

---

## 11. R559NY005 vs Old Configuration Comparison

| Aspect | Old (R553ZY002 + R559NY043) | New (R559NY005) |
|--------|----------------------------|-----------------|
| Floor circuits | 2 | **5** |
| Manifold | Separate R553ZY002 | **Integrated in R559NY005** |
| Mixing group | Separate R559NY043 | **Integrated in R559NY005** |
| Pump | Separate, 130mm | **Pre-installed ErP variable-speed** |
| Cabinet | Separate R500Y111 | **Included (1000×605mm)** |
| Flow meters | No | **Yes (0.5-5 L/min per circuit)** |
| Safety thermostat | No | **Yes (K373 included)** |
| Assembly | On-site assembly required | **Factory pre-assembled & tested** |

---

## 12. Installation Steps

### Hydraulic Installation

1. **Mount R553ZY005** (high-temp manifold) with R588Z brackets in R500Y222 cabinet
2. **Connect boiler supply/return** to R553ZY005 main 1" connections
3. **Mount R559NY005** (pre-assembled floor heating group) — unit comes with its own cabinet
4. **Connect R553ZY005 output** to R559NY005 input via 1" pipe
5. **Connect radiator circuits** to R553ZY005 outlets 1-5 using R179AM adapters
6. **Connect floor heating circuits** to R559NY005 outlets 1-5 using R179AM adapters
7. **Install K281X012 actuator** on R559NY005 mixing valve (M30×1.5mm)

### Actuator Installation (R473X221)

**On R553ZY005 (High-Temp Radiators):**

8. **Install R453Y002 ring nut** (included) on return manifold valve bodies for outlets 1-5
9. **Mount R473X221 actuators** — press onto ring nut, rotate 15° clockwise until click
10. **Press red lockout button** on each actuator after mounting

**On R559NY005 (Low-Temp Floor Heating):**

11. **Remove manual handwheels** from R559NY005 return manifold
12. **Mount R473X221 actuators** for floor zones 1-5
13. **Press red lockout button** on each actuator

### Electrical Installation

14. **Mount Danfoss Icon2 Main Controller** (088U2100) near manifold cabinets
15. **Wire R473X221 actuators** to Icon2 outputs:
    - Outputs 1-5 → R553ZY005 outlets 1-5 (radiators + towel rails)
    - Outputs 6-10 → R559NY005 outlets 1-5 (floor zones)
16. **Connect KPM30/31 module** with K281X012 and K363P probe for mixing control
17. **Pair Danfoss Wireless Thermostats** with Icon2 controller
18. **Place wireless thermostats** in each controlled zone

### Commissioning

19. **Balance floor circuits** using R559NY005 built-in flow meters and R558NY key
20. **Balance radiator circuits** using R558 spanner on R553ZY005 lockshield valves
21. **Set mixing temperature** via KPM30/31 (target 40-45°C for floor heating)
22. **Test each zone** via Icon2 controller manual override

---

## 13. Verification

### Hydraulic Tests

1. Pressure test all connections at 10 bar
2. Verify mixing valve operation — R559NY005 output should reach 40-45°C
3. Check ErP pump operation and flow through all 5 floor circuits
4. Balance individual circuits using R559NY005 flow meters (target 0.5-5 L/min per circuit)

### Actuator Tests (R473X221)

5. **Visual check**: Position indicator should be lowered when no power (valve closed)
6. **Power test**: Apply 230V — indicator should lift within ~3 minutes (valve open)
7. **Test all 10 actuators** individually via Danfoss Icon2 manual override

### Danfoss Icon2 System Tests

8. **Verify wireless thermostat pairing** — all thermostats respond to controller
9. **Zone test (radiators)**: Set room thermostat above current temp — corresponding actuator opens
10. **Zone test (floor heating)**: Set floor zone thermostat above current temp — corresponding actuator opens
11. **Verify zone isolation**: When one room calls for heat, only that zone's actuator(s) open
12. **Verify boiler relay**: Boiler fires when any zone calls for heat

### Safety Checks

13. **K373 safety thermostat test**: Verify it cuts mixing valve if floor supply exceeds safe temperature
14. **Bypass check**: Ensure system handles all-zones-closed condition safely (boiler bypass or Icon2 PWM)

---

## 14. Component Summary

| Zone | Component | Model | Purpose |
|------|-----------|-------|---------|
| Heat Source | Boiler | Ariston Clas One 30 | Primary heat generation (75-80°C) |
| High-Temp | Manifold | Giacomini R553ZY005 | 5-circuit radiator distribution |
| High-Temp | Cabinet | Giacomini R500Y222 | Flush-mount enclosure (600×650mm) |
| High-Temp | Actuators | Giacomini R473X221 × 5 | Radiator flow control |
| Low-Temp | Manifold Group | Giacomini R559NY005 | 5-circuit floor heating: manifold + mixing + pump + cabinet |
| Low-Temp | Actuators | Giacomini R473X221 × 5 | Floor zone control |
| Mixing | Valve Actuator | K281X012 | 24V, 0-10V mixing valve control |
| Mixing | Control Module | KPM30 or KPM31 | Electronic temperature regulation |
| Mixing | Temp Probe | K363P | Delivery temperature sensing |
| Control | Controller | Danfoss Icon2 (088U2100) | 15-channel central management (10 used) |
| Control | Thermostats | Danfoss Wireless × up to 10 | Room temperature sensing |

### Optional Accessories

| Component | Code | Purpose |
|-----------|------|---------|
| Manifold insulation | R559W | Thermal insulation for R559NY005 |
| Replacement cabinet (radiators) | R500Y222 | 600×650×85-140mm |

---

## 15. Pipe Adapter Reference (R179AM)

Select adapter based on your pipe outer diameter and wall thickness:

| Code | Size (Thread × Pipe OD × Wall) |
|------|-------------------------------|
| R179MX022 | 18 × 14 × 2 mm |
| R179MX024 | 18 × 16 × 2 mm |
| R179MX023 | 18 × 16 × 2.2 mm |
| R179MX025 | 18 × 18 × 2 mm |
| R179MX026 | 18 × 20 × 2 mm |

**Total adapters needed:** 20 pairs (10 for radiators + 10 for floor heating)

---

## 16. R559NY Series Reference

| Product Code | Circuits | Cabinet Size (W×H×D) |
|--------------|----------|----------------------|
| R559NY004 | 4 | 850×605×110mm |
| **R559NY005** | **5** | **1000×605×110mm** |
| R559NY006 | 6 | 1000×605×110mm |
| R559NY007 | 7 | 1000×605×110mm |
| R559NY008 | 8 | 1200×605×110mm |
| R559NY009 | 9 | 1200×605×110mm |
| R559NY010 | 10 | 1200×605×110mm |
| R559NY011 | 11 | 1200×605×110mm |
| R559NY012 | 12 | 1200×605×110mm |
