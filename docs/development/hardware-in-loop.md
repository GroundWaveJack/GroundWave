# Hardware-in-loop

Hardware-in-loop testing should use pytest for assertions and fixtures and labgrid or equivalent open orchestration for power, serial, flashing, switching, and recovery. Test rigs record instrument calibration, wiring, firmware, BOM revisions, environment, and raw logs.

Flat-build acceptance precedes enclosure integration. Destructive battery, RF, environmental, and safety tests require appropriate facilities and authority; simulation is not qualification.

Gates progress from fixture self-test, power-off inspection, current-limited bring-up, flashing and recovery, interface tests, fault injection, endurance, then profile-specific RF and environmental work. A failed gate blocks later qualification claims but should not erase the evidence. Emergency stop, current limit, isolation, unattended-run limits, and artifact retention are defined per rig.

Hardware-in-loop results are **Tested** evidence. They become **Qualified** only when the named configuration, criteria, instruments, uncertainty, deviations, and independent review required by that qualification profile are complete.
