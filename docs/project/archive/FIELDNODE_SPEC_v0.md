# Fieldnode Specification v0.1 (DRAFT)

The Fieldnode was the first tier the pre-Harriet project targeted for a shippable design. It is deliberately the simplest device in the system.

## Purpose

A Fieldnode is a solar-powered, weatherproof Reticulum relay. It is dropped, strapped, or mounted in a location and left to operate indefinitely. It has one job: extend the Reticulum mesh network. It has no user interface, no screen, and no complex integration.

## Design Goals

1. **Buildable in one afternoon** by someone with basic soldering skills.
2. **Total cost under $100** per unit in small quantities.
3. **Reproducible** — identical Fieldnodes can be built from this spec by any contributor.
4. **Weatherproof** — operates outdoors in rain, heat, cold, and sun for at least one year without maintenance.
5. **Autonomous** — solar-powered, indefinite runtime in reasonable sun exposure.
6. **Self-announcing** — joins the Reticulum mesh on boot with a documented identity.

## Component List (v0.1 — subject to prototype validation)

### Primary Option: RAK WisBlock RAK4631
- **MCU:** Nordic nRF52840 with integrated BLE
- **LoRa:** Semtech SX1262
- **Current draw:** ~11μA deep sleep
- **Cost:** $25–37 (kit with base + core module)
- **Rationale:** Lowest power consumption in its class. Ideal for solar-powered indefinite operation. Nordic chipset has excellent power management.

### Alternative: LILYGO T-Beam v1.2
- **MCU:** ESP32-S3
- **LoRa:** SX1262
- **Extras:** u-blox GNSS built in, 18650 battery holder
- **Cost:** $50–70
- **Rationale:** Known-good platform with existing RNode firmware support. Higher power draw than RAK but simpler integration.

### Power System
- **Battery:** 3.7V 3000mAh LiPo flat pack (or single 18650 cell with holder for T-Beam)
- **Solar:** 6V 2W monocrystalline panel minimum, 6V 5W preferred for higher latitudes
- **Charge controller:** CN3791 MPPT solar charger module ($3–5) or integrated (WisBlock has one)
- **Cost:** $15–25 total

### Antenna
- **LoRa 915 MHz:** SMA connector quarter-wave whip, 17cm. Commercial options ~$5.
- For higher gain / fixed deployments: 3dBi or 6dBi omni colinear, 30cm. ~$15.

### Enclosure
- **3D printed from PETG or ASA.** UV-resistant, heat-tolerant.
- **Design requirement:** IP65-equivalent sealing. Gasket channel for EPDM foam strip. Internal cable glands for antenna and solar pass-through.
- **Mounting:** Integrated threaded inserts for zip-tie, strap, or mast-mount options.
- **Status:** CAD design to be produced. Community contributions welcome.

### Miscellaneous
- Silicone sealant for final sealing
- EPDM foam gasket strip
- M3 threaded inserts (8x)
- M3 stainless bolts
- Silica gel desiccant packet
- Printed and laminated serial card with unit's Reticulum identity hash

## Firmware

- **Flash RNode firmware** (Qvist maintained) via `rnodeconf --autoinstall`
- **Configuration:** TNC mode disabled, transport node mode enabled
- **Channel:** pre-Harriet channel 2 (relay) and channel 1 (mesh) participation per channel plan
- **Identity:** Generated at first boot, recorded on the laminated serial card

## Build Time Estimate (v0.1 — to be validated)

- Component sourcing and delivery: 1–2 weeks
- Physical assembly: 2–3 hours (experienced) / 4–6 hours (first-time)
- Firmware flash and test: 30 minutes
- Weatherproofing and sealing: 1 hour
- Total hands-on time: ~5 hours for a first-time builder

## Deployment

A Fieldnode should be placed:

- **High.** Every meter of elevation meaningfully extends LoRa range. Rooftops, trees, mast mounts, utility poles (where legal and not subject to removal).
- **Sunlit.** At least 4 hours of direct sun per day for reliable year-round operation.
- **Unattended.** Assume you will not touch it again for a year.
- **Legally.** Respect property, right-of-way, local regulations. Fieldnodes operate on unlicensed ISM band at legal power levels but physical placement still matters.

## What Success Looks Like

A v1.0 Fieldnode spec is achieved when:

- Three independent builders, working only from this document, have produced a working Fieldnode.
- At least one Fieldnode has operated unattended outdoors for 30 days without intervention.
- The unit has demonstrably relayed Reticulum traffic for other project or compatible nodes.
- The build guide, CAD files, and BOM are in the public repository under the correct licenses.

## Known Open Questions

- Final SKU decision: RAK WisBlock vs LILYGO T-Beam (requires prototype comparison)
- 3D printed enclosure design (not started)
- Optimal antenna gain for typical deployment (requires field testing)
- Winter performance in high-latitude, low-sun conditions (unknown)
- Whether to include an optional external temperature/humidity sensor for environmental telemetry (scope creep risk)

## Next Steps

1. Order one RAK WisBlock kit and one LILYGO T-Beam for side-by-side prototype
2. Flash RNode firmware to both, verify Reticulum connectivity
3. Measure real-world power consumption in relay mode
4. Decide primary SKU based on data
5. Design v0.1 enclosure
6. Build three identical units to the spec
7. Deploy for 30-day field test
8. Iterate to v1.0
