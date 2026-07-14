# Expansion module interface

**Version:** concept 0.1; not a qualified connector specification

The proposed interface provides USB 2.0 host, 5 V and ground, optional current-limited 3.3 V auxiliary power, optional UART and I²C, module detect, switched/current-limited power, wake or interrupt, keyed rails, blind-mate connection, ESD protection, and an optional identification EEPROM.

EEPROM data is an untrusted hint, never authority. Modules own their RF path and antenna. Version 0.1 does **not** claim hot swap.

## Interface boundaries

USB is the primary data plane. UART and I²C are optional, electrically bounded maintenance or low-rate control buses; their presence does not grant trust, boot authority, or unrestricted access to the host. The specification must define voltage levels, pull-ups, addressing, bus isolation, cable length, arbitration, timeout/recovery behavior, and behavior for stuck or hostile devices before either bus can be qualified.

Five-volt module power and optional 3.3 V auxiliary power are independently switched, current limited, monitored, and default off for unknown modules. Module detect is debounced and cannot energize a module by itself. Wake/interrupt is bounded against repeated wakeups. Identification is matched to owner policy and observed electrical behavior, not trusted as an authorization credential.

## Safe-removal state machine

1. **Absent:** rails off; buses isolated.
2. **Detected:** identity hint and electrical presence observed with functional rails still off.
3. **Authorized:** owner policy selects a permitted profile and power budget.
4. **Powered:** rails ramp within inrush and fault limits; the host enumerates the module.
5. **Active:** bounded data and wake interfaces are enabled.
6. **Quiescing:** new work stops; transfers, storage, and radio activity drain or are aborted by policy.
7. **Safe to remove:** buses isolate and rails discharge below the specified threshold; the user receives confirmation.
8. **Fault:** power is removed and remains latched off until the defined recovery action.

Unexpected removal from Powered or Active is a tested fault, not supported hot swap. It must not corrupt host state, expose unsafe voltage, or automatically re-energize damaged hardware.

## Mechanical and verification gaps

Keying must prevent reversed or wrong-class insertion; rails must carry insertion loads without using electrical contacts as guides. Blind mating requires controlled alignment, first-mate/last-break analysis, touch-safe contacts, retention, strain relief, debris tolerance, and insertion-cycle evidence. The connector, pinout, rail sequence, current limits, discharge time, electrostatic-discharge protection, creepage/clearance, thermal limits, fault energy, electromagnetic compatibility, and regulatory profiles remain undecided.

Qualification tests include wrong and partial insertion, shorted and overloaded rails, inrush, back-powering, stuck buses, false detect, wake storms, corrupt identification, enumeration failure, removal in every state, repeated insertion, vibration, contamination, electrostatic discharge, thermal rise, and host recovery. No module or connector is qualified by this concept document.
