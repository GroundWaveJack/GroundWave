# Hardware qualification model

**State:** Adopted qualification vocabulary; the process has not yet produced qualified hardware.

All hardware is pre-qualification unless a published evidence record says otherwise. Maintain three separate artifacts:

- **Hardware Requirements Specification (HRS):** technology-neutral functions, interfaces, limits, hazards, and acceptance methods. It must not depend on a commercial stock-keeping unit where a component class is sufficient.
- **Reference Qualified BOM:** an immutable combination of part numbers, revisions, firmware, configuration, region, and assembly details that passed the HRS gates. Substitution creates a new candidate combination.
- **Procurement Manifest:** current suppliers, order codes, lead times, alternates, lifecycle risk, and purchasing notes. It may change without changing requirements or qualification.

| State | Meaning |
| --- | --- |
| Reference | Documented baseline, not necessarily tested |
| Qualified | Passed published acceptance criteria as a combination |
| Compatible | Meets interface requirements; qualification not implied |
| Community-tested | Results supplied by identified test conditions |
| Experimental | Evaluation only |
| Deprecated | Replacement planned; migration documented |
| Unsupported | No project support or conformance claim |

Qualification is configuration-specific and expires when material revisions invalidate evidence.

## Evidence record

Each qualification result records the HRS revision, complete configuration and serial or lot scope, firmware and test-software revisions, laboratory setup, calibrated instruments, ambient conditions, regulatory region, test procedure, raw results, deviations, failures, operator pseudonym, date, and durable artifact links. A summary without reproducible results is not qualification evidence.

## Gates

A candidate advances only after applicable gates have objective pass criteria:

1. design review and hazard analysis;
2. inspection, continuity, and protected first power;
3. functional and interface conformance;
4. power, charging, battery-fault, and thermal characterization;
5. radio-frequency (RF), coexistence, exposure, and regional review;
6. mechanical, connector-cycle, ingress, drop, and vibration testing appropriate to the embodiment;
7. software provisioning, recovery, update, and security tests;
8. sustained operation and fault-injection testing;
9. configuration freeze and independent evidence review.

A non-applicable gate needs a recorded rationale. Community results can inform qualification, but remain **Community-tested** until the project reviews them against the same evidence contract.
