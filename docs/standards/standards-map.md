# Standards and projects map

**State:** architecture under design; evaluation posture, not an implementation list

The posture vocabulary is normative for this map:

- **OWN:** specify only the connective semantics that remain Groundwave's responsibility.
- **PROFILE:** constrain and map an existing standard or project without claiming ownership of it.
- **INTEGRATE:** connect through a documented adapter or supported interface.
- **PARTNER:** coordinate only after mutual acknowledgement; until then, a project is a partnership candidate.
- **WATCH:** monitor suitability without committing an implementation.
- **DO NOT BUILD:** treat the capability as solved elsewhere unless an RFC demonstrates a gap.

Each compatibility claim needs an owned artifact (profile, adapter, fixture, or test report), a maturity state, and reproducible evidence. Candidate names alone are not evidence.

| Area | Posture | Candidates | Groundwave responsibility |
| --- | --- | --- | --- |
| Intent, policy, provenance | OWN | Groundwave schemas and receipts | Specify minimally and test across profiles |
| Low-bandwidth messaging | PROFILE | Reticulum, LXMF, RNode, Sideband | Adopted profile target under design; own mapping and fixtures |
| Disruption tolerance | PROFILE / INTEGRATE | BPv7, BPSec, DTN implementations | Evaluate security and custody mappings |
| Local routing and mesh | INTEGRATE | Babel, 802.11s, batman-adv | Use at their correct layer |
| Router edge | INTEGRATE; partnership candidates | OpenWrt, LibreMesh, Gluon, AREDN | Proposed profile only after supported-target tests |
| Adjacent LoRa ecosystems | WATCH; partnership candidates | MeshCore, Meshtastic, Haven MANET | Seek acknowledged interop; avoid forced equivalence |
| Multipath | WATCH / DO NOT BUILD | MPTCP concepts, ECMP | Borrow proven behavior; do not build a generic multipath transport |
| Cache reconciliation | PROFILE / DO NOT BUILD | content addressing, Bloom filters | Define bounded use; measure leakage and false positives |
| Long-haul adapters | INTEGRATE / WATCH | HF digital, satellite, optical | External-radio/convergence profiles only |
| Lab automation | INTEGRATE | labgrid, pytest | Produce reproducible hardware-in-loop evidence |

No row authorizes bundling, endorsement, formal partnership, or a fork. Before implementation, externally verify relevant specifications, project status, interfaces, governance, licensing compatibility, security maintenance, and technical fit. This map records no completed external verification.
