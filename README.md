# AC Clutch Boost Circuit

acClutchBoost is a KiCad hardware project designed to improve AC clutch engagement on the **8th Generation Honda Civic Si**. The project addresses a common issue where the AC clutch fails to engage reliably due to increased air gap from clutch wear, particularly at high ambient temperatures.

The repository includes the **schematic**, **PCB layout**, and **BOM** required to build the circuit.

---

## Background

Over time, wear in the AC clutch friction material increases the air gap between the clutch plate and pulley. As the gap grows, the clutch solenoid may no longer generate sufficient magnetic force to pull in the clutch, especially under adverse conditions such as high temperatures.

At elevated temperatures, clutch engagement can degrade further, potentially due to reduced magnetic permeability of the ferrous components or increased coil resistance. The result is intermittent or complete AC failure despite correct ECU commands.

---

## Concept

When the vehicle ECU commands AC clutch engagement, **acClutchBoost** briefly increases the voltage supplied to the clutch coil above the nominal automotive range (approximately 12–14 V). This higher voltage is applied for a short, configurable duration to ensure reliable pull-in of the clutch. After this initial boost period, the circuit returns the clutch supply to normal voltage to avoid overheating or long-term stress.

This approach improves engagement reliability without permanent mechanical modification of the clutch assembly.

---

## Key Features

- Interfaces directly with the factory AC clutch control signal
- Momentary voltage boost during clutch engagement
- Adjustable boost voltage
- Adjustable boost duration
- Returns to nominal voltage after engagement
- Designed specifically for 8th Gen Civic Si electrical characteristics

---

## Design Overview

The circuit consists of:

- **Non-isolated DC-DC step-up (boost) converter**
  - Trimmable output voltage
  - Raises clutch supply voltage during engagement
- **Relay-based switching**
  - Selects between nominal supply and boosted supply
  - Ensures normal operation after engagement
- **Adjustable timing circuit**
  - Controls the duration of the voltage boost
  - Allows tuning for different wear conditions or temperatures

---

## Repository Contents

- **Schematic**  
  Complete circuit design showing power, control, and timing sections.

- **PCB Layout**  
  Board layout suitable for automotive installation considerations.

- **BOM (Bill of Materials)**  
  Component list with values and part references.

---

## Adjustability

- **Boost Voltage**  
  Set via trim potentiometer on the DC-DC converter.

- **Boost Duration**  
  Controlled by the adjustable timing circuit to apply voltage only during initial engagement. Set via trim potentiometer.

Both parameters can be tuned to balance reliable clutch pull-in with long-term component safety.

---

## Intended Use

This project is intended for:
- Experimental and educational use
- Automotive electronics enthusiasts
- Situations where AC clutch wear causes unreliable engagement

It is not a replacement for proper mechanical repair, but a practical electrical mitigation for a known failure mode.

---

## Tools

- KiCad (for viewing and modifying schematic and PCB)
- Standard PCB fabrication and assembly tools

---

## Disclaimer

This project interfaces with automotive electrical systems. Improper installation or tuning may result in damage to vehicle components or injury. Use at your own risk.

---

## License

CERN-OHL-W v2
