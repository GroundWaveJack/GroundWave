# Expansion module interface

**Version:** concept 0.1; not a qualified connector specification

The proposed interface provides USB 2.0 host, 5 V and ground, optional current-limited 3.3 V auxiliary power, optional UART and I²C, module detect, switched/current-limited power, wake or interrupt, keyed rails, blind-mate connection, ESD protection, and an optional identification EEPROM.

EEPROM data is an untrusted hint, never authority. Modules own their RF path and antenna. Version 0.1 does **not** claim hot swap: safe removal uses quiesce, explicit state handling, power cut, and user confirmation. Electrical limits, connector selection, insertion cycles, fault containment, and compliance tests remain open.
