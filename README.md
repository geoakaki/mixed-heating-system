# Heating System Configuration

## Overview

Combined manifold/distribution system for mixed high-temperature (radiators) and low-temperature (floor heating) circuits from a single boiler.

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
│ R559NY043                           │
│ Mixing Group + Circulator Pump      │
│ Reduces temp from 75-80°C → 40-45°C │
│ Pump center distance: 130-180mm     │
└──────────────┬──────────────────────┘
               │ 1" pipe (mixed water)
               ▼
┌─────────────────────────────────────┐
│ R553ZY002                           │
│ Pre-assembled brass manifold        │
│ LOW TEMP - 2 circuits (floor heat)  │
│ Connection: 1" × Base 18            │
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

### Hydraulic Components

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **R553ZY005** | Pre-assembled brass manifold, 5 outlets | 1 | High-temp radiator distribution |
| **R559NY043** | Mixing group with 3-way valve | 1 | Temperature control + pump mount |
| **R553ZY002** | Pre-assembled brass manifold, 2 outlets | 1 | Low-temp floor heating distribution |
| **Circulator pump** | 130mm center distance (recommended) | 1 | Fits R559NY043 spacer |

### Actuators & Control

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **R473X221** | Thermo-electric actuator, 230Vac, N.C. | 5 | 3 for radiators + 2 for floor heating |
| **Danfoss Icon2 Main Controller** | 230V main controller | 1 | Controls all 5 R473X221 actuators |
| **Danfoss Wireless Thermostat** | Room temperature sensor | 4 | Bedroom 1, Bedroom 2, Office, Living Room |
| **Manual TRV** | Thermostatic radiator valve | 2 | For Bathroom 1 & 2 towel rails |

### Mixing Valve Control (for R559NY043)

| Product Code | Description | Qty | Notes |
|--------------|-------------|-----|-------|
| **K281** | Actuator for mixing valve | 1 | Controls 3-way valve, M30×1.5mm thread |
| **KPM30 or KPM31** | Electronic regulation module | 1 | Controls K281 based on temp setpoint |
| **K363P** | Delivery temperature probe | 1 | Included with KPM30/KPM31 |

---

## 3. Zone A: High-Temperature Circuit (Radiators)

### R553ZY005 Circuit Assignment

| Outlet | Room | Control Method | Actuator | Thermostat |
|--------|------|----------------|----------|------------|
| 1 | Bedroom 1 Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 2 | Bedroom 2 Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 3 | Office Radiator | Danfoss Icon2 | R473X221 | Danfoss Wireless |
| 4 | Bathroom 1 Towel Rail | Manual | None (use handwheel) | Manual TRV on rail |
| 5 | Bathroom 2 Towel Rail | Manual | None (use handwheel) | Manual TRV on rail |

### R553ZY005 / R553ZY002 Manifold Specifications

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

## 4. Zone B: Low-Temperature Circuit (Floor Heating)

### R553ZY002 Circuit Assignment

| Outlet | Zone | Control Method | Actuator | Thermostat |
|--------|------|----------------|----------|------------|
| 1 | Living Room Zone A | Danfoss Icon2 | R473X221 | Danfoss Wireless (shared) |
| 2 | Living Room Zone B | Danfoss Icon2 | R473X221 | Danfoss Wireless (shared) |

**Note:** Both floor heating zones controlled by single Living Room thermostat (zones open/close together)

### R559NY043 Mixing Group Specifications

| Spec | Value |
|------|-------|
| Inlet/Outlet | 1" |
| Circulator connection | 1½" unions |
| Mixing valve actuator | M30×1.5mm thread |
| Pump center distance | 130-180mm |
| Max working pressure | 10 bar |
| Temperature range | 5-110°C |

**Includes:** 3-way mixing valve, primary/secondary lockshield valves, air vents, drain cocks, thermometer housings

### Recommended Settings (R559NY043)

| Valve | Setting |
|-------|---------|
| Primary lockshield valve | 2 turns open |
| Secondary lockshield valve | Fully open |

### How the R559NY043 Reduces Temperature

The R559NY043 contains a **3-way mixing valve** that blends two water streams:

| Port | Source | Temperature |
|------|--------|-------------|
| **HOT inlet** | From R553ZY005 (via 1" pipe) | 75-80°C |
| **COLD inlet** | Return from floor loops | ~25-35°C |
| **MIXED outlet** | To R553ZY002 (via pump) | 40-45°C |

**Mixing Process:**
1. Hot water from high-temp manifold enters the mixing valve
2. Cool return water from floor loops is recirculated back
3. K281 actuator (controlled by KPM30/31) adjusts blend ratio based on temperature probe
4. Pump pushes the mixed water through to R553ZY002
5. R553ZY002 distributes to floor loops
6. Floor absorbs heat, water cools, returns to mixing valve

---

## 5. R473X221 Actuator Specifications

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

- Both operate at **230V** - direct connection possible
- R473X221 is **Normally Closed** - valve closes safely when no power
- Simple 2-wire connection to Icon2 output channels
- Total load: 5 × 2.5W = **12.5W** (well within Icon2 capacity)

---

## 6. Controls Ecosystem (Danfoss Icon2)

### Central Controller

| Specification | Value |
|---------------|-------|
| **Unit** | Danfoss Icon2 Main Controller |
| **Voltage** | 230V |
| **Location** | Near the manifolds (ideally central utility box) |

### Danfoss Icon2 Output Assignment

| Output | Actuator Location | Zone | Thermostat |
|--------|-------------------|------|------------|
| 1 | R553ZY005 Outlet 1 | Bedroom 1 Radiator | Bedroom 1 |
| 2 | R553ZY005 Outlet 2 | Bedroom 2 Radiator | Bedroom 2 |
| 3 | R553ZY005 Outlet 3 | Office Radiator | Office |
| 4 | R553ZY002 Outlet 1 | Living Room Floor A | Living Room |
| 5 | R553ZY002 Outlet 2 | Living Room Floor B | Living Room |

**Note:** Outputs 4 & 5 both respond to Living Room thermostat (parallel control)

### Input Signals (Wireless Thermostats)

| Room | Signal Flow |
|------|-------------|
| **Bedroom 1** | Thermostat → Main Controller → Opens R553ZY005 Outlet 1 Actuator → Fires Boiler |
| **Bedroom 2** | Thermostat → Main Controller → Opens R553ZY005 Outlet 2 Actuator → Fires Boiler |
| **Office** | Thermostat → Main Controller → Opens R553ZY005 Outlet 3 Actuator → Fires Boiler |
| **Living Room** | Thermostat → Main Controller → Opens BOTH R553ZY002 Actuators → Fires Boiler |

---

## 7. Passive Zone (Bathrooms)

### Target Areas

- Bathroom 1
- Bathroom 2

### Components

| Component | Specification |
|-----------|---------------|
| **Emitters** | 2× Towel Rails (one per bathroom) |
| **Control** | Manual Thermostatic Heads (TRV) on towel rails |
| **Supply** | From R553ZY005 Outlets 4 & 5 (via handwheel) |
| **Return** | To R553ZY005 Return Bar |

### Technical Notes

- Towel rails are fed directly from R553ZY005 manifold (no actuators)
- Manual handwheel on manifold provides flow control
- TRV heads on towel rails provide local temperature control
- They serve as a hydraulic bypass if all other electronic valves close simultaneously

---

## 8. Cabinet Options

| Manifold | Outlets | Compatible Cabinets |
|----------|---------|---------------------|
| R553ZY005 | 5 | R500Y112 (600×460×110mm) or R500Y222 or R500Y215 |
| R553ZY002 | 2 | R500Y111 (400×460×110mm) or R500Y221 or R500Y215 |

---

## 9. Flow Diagram

```
                    SUPPLY SIDE                 RETURN SIDE
                         │                           │
    ┌────────────────────┴───────────────────────────┴─────────────────┐
    │                         BOILER                                   │
    └────────────────────┬───────────────────────────┬─────────────────┘
                         │ HOT (75-80°C)             ▲
                         ▼                           │
    ┌────────────────────────────────────────────────┴─────────────────┐
    │  R553ZY005 - HIGH TEMP MANIFOLD (5 circuits)                     │
    │  ┌─────┬─────┬─────┬─────┬─────┐                                 │
    │  │  1  │  2  │  3  │  4  │  5  │                                 │
    │  └──┬──┴──┬──┴──┬──┴──┬──┴──┬──┘                                 │
    │     │     │     │     │     │                                    │
    │   Bed1  Bed2  Office Bath1 Bath2                                 │
    │  R473  R473  R473  Manual Manual  ← Actuators on return manifold │
    └────────────────────┬────────────────────────────┬────────────────┘
                         │                            ▲
                         ▼                            │
    ┌────────────────────────────────────────────────┴─────────────────┐
    │  R559NY043 - MIXING GROUP + PUMP                                 │
    │  ┌─────────┐  ┌──────────┐  ┌─────────┐                          │
    │  │ 3-way   │──│  PUMP    │──│ Control │                          │
    │  │ valve   │  │ 130mm    │  │ valves  │                          │
    │  └─────────┘  └──────────┘  └─────────┘                          │
    └────────────────────┬────────────────────────────┬────────────────┘
                         │ MIXED (40-45°C)            ▲
                         ▼                            │
    ┌────────────────────────────────────────────────┴─────────────────┐
    │  R553ZY002 - LOW TEMP MANIFOLD (2 circuits)                      │
    │  ┌─────┬─────┐                                                   │
    │  │  1  │  2  │  ← Floor heating circuits                         │
    │  └─────┴─────┘                                                   │
    └─────────────────────────────────────────────────────────────────┘
```

---

## 10. Electrical Wiring Diagram

```
┌──────────────────────────────────────────────────────────────────────────────────┐
│                       DANFOSS ICON2 MAIN CONTROLLER (230V)                       │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐            │
│  │ Output 1 │  │ Output 2 │  │ Output 3 │  │ Output 4 │  │ Output 5 │            │
│  │  (230V)  │  │  (230V)  │  │  (230V)  │  │  (230V)  │  │  (230V)  │            │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘            │
└───────┼─────────────┼─────────────┼─────────────┼─────────────┼──────────────────┘
        │             │             │             │             │
   ┌────┴────┐   ┌────┴────┐   ┌────┴────┐   ┌────┴────┐   ┌────┴────┐
   │R473X221 │   │R473X221 │   │R473X221 │   │R473X221 │   │R473X221 │
   │Bedroom 1│   │Bedroom 2│   │ Office  │   │Living A │   │Living B │
   └────┬────┘   └────┬────┘   └────┬────┘   └────┬────┘   └────┬────┘
        │             │             │             │             │
        ▼             ▼             ▼             ▼             ▼
   R553ZY005     R553ZY005     R553ZY005     R553ZY002     R553ZY002
   Outlet 1      Outlet 2      Outlet 3      Outlet 1      Outlet 2
   (Radiator)    (Radiator)    (Radiator)    (Floor)       (Floor)

   ~~~~~~~~~~~~~~~~~~~~~~~~~ Wireless Communication ~~~~~~~~~~~~~~~~~~~~~~~~~
        ▲             ▲             ▲             ▲─────────────┘
   ┌────┴────┐   ┌────┴────┐   ┌────┴────┐   ┌────┴────┐
   │ Danfoss │   │ Danfoss │   │ Danfoss │   │ Danfoss │
   │Wireless │   │Wireless │   │Wireless │   │Wireless │
   │Thermost.│   │Thermost.│   │Thermost.│   │Thermost.│
   │Bedroom 1│   │Bedroom 2│   │ Office  │   │Living Rm│  ← Controls both zones
   └─────────┘   └─────────┘   └─────────┘   └─────────┘
```

### R473X221 Wiring (2-wire connection)

- **Brown wire** → Live (L) from Icon2 output
- **Blue wire** → Neutral (N) common

### Bathroom Towel Rails (Manual - No Wiring)

- Outlets 4 & 5 on R553ZY005 use **manual handwheel**
- Thermostatic control via **manual TRV** mounted directly on towel rail

---

## 11. Installation Steps

### Hydraulic Installation

1. **Mount R553ZY005** (high-temp manifold) with R588Z brackets in cabinet
2. **Connect boiler supply/return** to R553ZY005 main 1" connections
3. **Install R559NY043** mixing group downstream of R553ZY005
4. **Install circulator pump** in R559NY043 spacer (130mm recommended)
5. **Mount R553ZY002** (low-temp manifold) downstream of R559NY043
6. **Connect radiator circuits** to R553ZY005 outlets 1-5 using Base 18 adapters
7. **Connect floor heating circuits** to R553ZY002 using Base 18 adapters
8. **Install mixing valve actuator** (K281 or KPM30/31) on R559NY043

### Actuator Installation (R473X221)

**On R553ZY005 (High-Temp Radiators):**

9. **Install R453Y002 ring nut** (included) on return manifold valve bodies for outlets 1, 2, 3
10. **Mount R473X221 actuators** - press onto ring nut, rotate 15° clockwise until click
11. **Press red lockout button** on each actuator after mounting
12. **Leave outlets 4 & 5** with manual handwheels (bathroom towel rails)

**On R553ZY002 (Low-Temp Floor Heating):**

13. **Install R453Y002 ring nut** on return manifold valve bodies for outlets 1, 2
14. **Mount R473X221 actuators** for Living Room zones A & B
15. **Press red lockout button** on each actuator

### Electrical Installation

16. **Mount Danfoss Icon2 Main Controller** in suitable location (near manifold cabinet recommended)
17. **Wire R473X221 actuators** to Icon2 outputs:
    - Output 1 → Bedroom 1 radiator (R553ZY005 outlet 1)
    - Output 2 → Bedroom 2 radiator (R553ZY005 outlet 2)
    - Output 3 → Office radiator (R553ZY005 outlet 3)
    - Output 4 → Living Room Floor A (R553ZY002 outlet 1)
    - Output 5 → Living Room Floor B (R553ZY002 outlet 2)
18. **Pair Danfoss Wireless Thermostats** with Icon2 controller
19. **Configure outputs 4 & 5** to respond to Living Room thermostat (parallel zones)
20. **Place wireless thermostats** in Bedroom 1, Bedroom 2, Office, Living Room

### Commissioning

21. **Balance circuits** using R558 spanner on lockshield valves
22. **Test each zone** via Icon2 controller

---

## 12. Verification

### Hydraulic Tests

1. Pressure test all connections at 10 bar
2. Verify mixing valve operation - output should reach 40-45°C
3. Check pump operation and flow through R559NY043
4. Balance individual circuits using flow meters and lockshield valves

### Actuator Tests (R473X221)

5. **Visual check**: Position indicator (A) should be lowered when no power (valve closed)
6. **Power test**: Apply 230V - indicator should lift within ~3 minutes (valve open)
7. **Test each actuator** individually via Danfoss Icon2 manual override

### Danfoss Icon2 System Tests

8. **Verify wireless thermostat pairing** - all 4 thermostats respond to controller
9. **Zone test (radiators)**: Set Bedroom/Office thermostat above current temp - corresponding actuator opens
10. **Zone test (floor heating)**: Set Living Room thermostat above current temp - BOTH floor actuators open
11. **Verify zone isolation**: When one room calls for heat, only that zone's actuator(s) open

### Bathroom Towel Rails (Manual)

12. **Test manual handwheel operation** on R553ZY005 outlets 4 & 5
13. **Verify manual TRV function** on each towel rail

---

## Component Summary

| Zone | Component | Model | Purpose |
|------|-----------|-------|---------|
| Heat Source | Boiler | Ariston Clas One 30 | Primary heat generation (75-80°C) |
| High-Temp | Manifold | Giacomini R553ZY005 | 5-circuit radiator distribution |
| High-Temp | Actuators | Giacomini R473X221 × 3 | Radiator flow control (Bed1, Bed2, Office) |
| Mixing | Mixing Group | Giacomini R559NY043 | Temperature reduction (75-80°C → 40-45°C) |
| Mixing | Pump | 130mm center distance | Floor heating circulation |
| Mixing | Actuator | K281 + KPM30/31 | Mixing valve control |
| Low-Temp | Manifold | Giacomini R553ZY002 | 2-circuit floor heating distribution |
| Low-Temp | Actuators | Giacomini R473X221 × 2 | Floor zone control (Living A, Living B) |
| Control | Controller | Danfoss Icon2 (230V) | Central system management |
| Control | Thermostats | Danfoss Wireless × 4 | Room temperature sensing |
| Passive | Towel Rails × 2 | With Manual TRV Heads | Bathroom heating (hydraulic bypass) |

---

## System Diagram

See `heating-system.drawio` for a visual representation of the complete system layout.
