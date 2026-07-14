# Zack handheld

**State:** reference design under design; not prototyped or qualified

Zack is a retro brick-phone handheld concept centered in v1 on a Raspberry Pi Zero 2 W host, RAK19007 with RAK4631 US915 RNode profile, RAK12500 GNSS, portrait display, keypad, encoder, push-to-talk control, audio and haptics provision, battery/power path, Wi-Fi, Bluetooth, external antenna, and removable electronics spine.

These parts are reference selections, not permanent requirements. The electronics must pass documented flat-build power, thermal, input, display, audio, radio, and fault tests before shell integration. Regulatory, RF exposure, battery safety, acoustic safety, usability, and antenna performance remain unqualified.

## Acceptance sequence

The flat build isolates electrical faults from enclosure effects. Before shell integration it must demonstrate protected startup and shutdown, peak-load voltage stability, charge and cutoff behavior, sleep/wake recovery, display and every physical input, audio path and safe output limits, haptics, Global Navigation Satellite System acquisition, Wi-Fi and Bluetooth coexistence, radio receive/transmit under a permitted test setup, antenna-port protection, thermal steady state, and recovery from power and peripheral faults.

The integrated build repeats affected tests and adds enclosure temperature, acoustic performance, antenna detuning and user exposure review, control accessibility, cable and connector strain, battery containment, drop/vibration, service procedure, and sustained-use testing. Passing the flat build does not qualify the integrated device.

The named v1 components describe one reference candidate. No Zack assembly is currently represented here as prototype, tested, qualified, or released.
