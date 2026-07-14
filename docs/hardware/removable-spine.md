# Removable electronics spine

**State:** Proposed reference design; not prototyped or qualified.

The Zack reference separates electronics from the enclosure so flat-build acceptance, repair, and variant testing occur before shell integration. A spine should constrain connector strain, antenna separation, thermal paths, battery isolation, service access, and repeatable assembly.

Removal is powered-down service, not hot swap. Qualification requires assembly tolerances, drop/vibration evidence, connector-cycle tests, thermal measurements, and fault-safe battery handling.

The spine is the serviceable carrier for the reference device's core electronics. It is not the expansion module interface: removing it may expose the battery, host, display, controls, and internal RF interconnects, while an expansion module is a bounded optional peripheral. Their connectors, state machines, service procedures, and qualification records remain separate.

The service procedure requires normal shutdown, external-power removal, battery isolation where provided, discharge verification, electrostatic-discharge controls, keyed extraction, visual inspection, and a post-install acceptance test. Open questions include retention force, fasteners, flex and coax routing, antenna clearance, thermal interface repeatability, insertion life, tolerance stack, and repair tooling.
