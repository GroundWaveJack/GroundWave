# PROJECT_STATE.md

**Last updated:** Initial draft, April 2026
**Purpose:** This is the canonical state document for the pre-Harriet project. It is the single source of truth for "where the project stands right now." It is read at the start of every working session and updated when anything material changes.

---

## 1. What the pre-Harriet project Is

The pre-Harriet project is an open-source, hardware-focused emergency communications and survival system built for scenarios in which conventional communications infrastructure is unavailable, compromised, or actively hostile. It is designed to function without subscriptions, without corporate dependencies, and without any single point of failure.

The pre-Harriet project is a **hardware contribution lane** within a larger open-source communications ecosystem. It explicitly does not reinvent software that already exists. It stands on the shoulders of projects like Reticulum, RNode, Sideband, LXMF, LXST, Haven MANET, Briar, OsmAnd, and JS8Call. The pre-Harriet project's contribution is the integrated hardware kit, the system architecture that unifies these tools, the deployment standard, and the documentation that makes this stack accessible to a non-expert builder.

## 2. The Three Scenarios

The pre-Harriet project is designed to operate across three threat environments:

1. **Collapse** — Grid down, infrastructure gone, purely peer-to-peer RF.
2. **Compromised Infrastructure** — Grid up, internet up, neither trusted. Surveillance, censorship, DPI, IMSI catchers.
3. **Hybrid** — Partial infrastructure. System automatically selects most resilient/covert path.

Reticulum's transport-agnostic architecture handles most of the switching between scenarios. The pre-Harriet project's hardware provides every transport Reticulum needs.

## 3. The Four-Tier Architecture

- **Tier 1 — The Brick.** Handheld communicator in a Zach Morris–style brick phone form factor. Orange Pi 5 (RK3588) or RK3566, 5" display, RNode + HackRF + RTL-SDR + GNSS, hardware kill switches, 3D-printed chassis.
- **Tier 2 — The Anchor.** Hardened base station. LiFePO4 battery bank, solar input, HF transceiver, APRS, multiple SDRs, Faraday case with filtered antenna feedthroughs, physical storage for spare parts and supplies.
- **Tier 3 — The Fieldnode.** Cheap, droppable, solar-powered Reticulum relay. One RNode, one battery, one job. Buildable in an afternoon for $60–100. Confirmed first deliverable.
- **Tier 0 — The Ghost.** Zero-electronics analog fallback. Laminated topo maps, mechanical compass, printed channel plan, signal mirror, OTP sheets, whistle.

## 4. The RF Protocol Stack

Every protocol in the stack functions without subscription or corporate infrastructure.

**Mesh / Data:** Reticulum (RNode 915MHz primary), Meshtastic (interop), APRS, WiFi MANET (802.11s + BATMAN-adv via Haven).

**Voice Direct:** FRS, GMRS, MURS, Ham 2m simplex, Ham HF (40m/80m/20m), FreeDV, JS8Call.

**Passive Monitoring:** FM/AM/shortwave broadcast, NOAA Weather Radio (162 MHz), NOAA APT satellite (137 MHz), ADS-B (1090 MHz), P25/DMR receive, IMSI catcher detection, WiFi/BT probe scanning.

**Navigation:** GNSS multi-constellation (GPS + GLONASS + Galileo + BeiDou via u-blox M10), WSPR for HF propagation mapping.

**Compromised-Infra Layer:** Tor + obfs4, I2P, WireGuard, Briar, Cwtch, MAC randomization, verified AOSP with no Google services, HackRF spectrum sweep for counter-surveillance.

Explicitly eliminated: Iridium, Starlink, cellular, Zigbee, Z-Wave, LORAN-C, GOES imagery, ACARS, numbers stations, STANAG monitoring, pager decoding — each for disqualifying reasons (subscription dependency, corporate dependency, or mission irrelevance).

## 5. Core Design Principles

1. **Zero subscriptions, zero infrastructure dependencies.** Hard constraint. Non-negotiable.
2. **Stand on existing open-source software.** Do not reinvent protocols, apps, or firmware. Contribute upstream where possible.
3. **Graceful degradation.** Every capability has a fallback. Reticulum handles transport switching automatically.
4. **Buildable by anyone.** Standardized components, public BOM, detailed documentation. A motivated non-expert can build a Fieldnode in an afternoon.
5. **Zero-trust identity.** Every node has a cryptographic identity (via Reticulum). Trust is never assumed, always proven. Individual, device, and group identities are all separately managed.
6. **Sovereignty over convenience.** If something is easier to use but creates a dependency, we choose the harder path.
7. **Honest about limits.** EMP protection is not mil-spec. HF TX is not possible from the Brick. Satellite is not part of the system. The project is credible because it does not overclaim.

## 6. The pre-Harriet project Channel Plan (v1.0 Draft)

LoRa / RNode (915 MHz US):
- CH 0 — OPEN BEACON (unencrypted position)
- CH 1 — HARRIET NET (encrypted mesh primary)
- CH 2 — RELAY ONLY (repeater traffic)
- CH 3 — DIRECT (encrypted point-to-point)
- CH 9 — EMERGENCY (unencrypted broadcast)

MANET WiFi: SSID "HARRIET", Reticulum encryption, auto-join.

Voice fallback:
- UHF 462.675 MHz (GMRS Ch 20, FRS interop)
- VHF 146.520 MHz (ham national calling)
- AM 2.182 MHz (maritime distress)

Analog brevity codes: 3 clicks = alive/moving, 5 clicks = need help, 7 clicks = compromised/abort.

## 7. Licensing

- **Hardware:** CERN Open Hardware License v2 (Strongly Reciprocal)
- **Software:** AGPL v3
- **Documentation:** Creative Commons BY-SA 4.0

The project is copyleft by intent. Derivative works must remain open.

## 8. Organizational Structure

**Current state:** Sole steward operating under pseudonym. Fiscal sponsorship being explored via Open Collective or similar.

**Target state (12–18 months):** Nonprofit foundation with a three-member board, distributed maintainership, community-funded operation.

**Governance principle:** The project must be structurally resistant to capture. Decisions, maintainer changes, and governance changes require documented process. No single person can close or take over the project, including the founder.

## 9. Current Status

- Architecture: drafted, iterating
- Hardware: no prototypes built
- Community: none yet
- Legal entity: not formed
- Repository: not created
- First users: not identified

**Immediate next milestone:** First Fieldnode prototype built and documented.

## 10. Decision Log

Architectural decisions that have been made and should not be relitigated without a strong reason:

- **Build on Reticulum, not a new protocol.** Confirmed.
- **Fieldnode ships first, not the Brick.** Confirmed. Rationale: simplest to build, immediate network value, lowest risk, validates supply chain.
- **RK3566 over RK3588 for the Brick.** Rationale: 2× energy efficiency for a battery-constrained handset. The Brick is battery-bound; the Anchor can use higher-power chips.
- **Zero subscription / zero infrastructure is a hard constraint.** Confirmed. This eliminated Iridium, Starlink, Helium, etc.
- **Pseudonymous public stewardship with real legal entity behind it.** Confirmed approach.
- **Fiscal sponsorship first, nonprofit foundation later.** Confirmed phasing.
- **The punch card key is an experiment, not a shipping v1 feature.** Confirmed scope.

## 11. Open Questions

- Specific pseudonym / callsign for the steward (pending)
- Fiscal sponsor selection (Open Collective vs others)
- First ten target users (not yet identified)
- Exact Fieldnode hardware SKU: RAK WisBlock RAK4631 vs LILYGO T-Beam (pending prototype)
- Whether to formally coordinate with Parallel's OpenMANET effort or stay independent

## 12. Watch List — Things That Could Change The Project

- Reticulum license situation and fork dynamics (RetiNet, Reticulum-rs)
- Beechat Network Systems / NATO DIANA Reticulum work — potential defense capture of the protocol
- Meshtastic / Reticulum interop progress
- RK3576 maturity as a middle-ground SoC option
- FuriLabs FLX1s trajectory (not a pre-Harriet project component but adjacent)
