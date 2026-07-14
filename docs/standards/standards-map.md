# Standards and projects map

**State:** evaluation posture, not an implementation list

| Area | Posture | Candidates | Groundwave responsibility |
| --- | --- | --- | --- |
| Intent, policy, provenance | OWN | Groundwave schemas and receipts | Specify minimally and test across profiles |
| Low-bandwidth messaging | PROFILE | Reticulum, LXMF, RNode, Sideband | Map semantics; contribute upstream |
| Disruption tolerance | PROFILE / INTEGRATE | BPv7, BPSec, DTN implementations | Evaluate security and custody mappings |
| Local routing and mesh | INTEGRATE | Babel, 802.11s, batman-adv | Use at their correct layer |
| Router edge | PARTNER / INTEGRATE | OpenWrt, LibreMesh, Gluon, AREDN | Package only after supported-profile tests |
| Adjacent LoRa ecosystems | PARTNER / WATCH | MeshCore, Meshtastic, Haven MANET | Seek interop; avoid forced semantic equivalence |
| Multipath | WATCH / BORROW | MPTCP concepts, ECMP | Borrow behavior, not protocol identity |
| Cache reconciliation | BORROW | content addressing, Bloom filters | Measure leakage and false positives |
| Long-haul adapters | INTEGRATE / WATCH | HF digital, satellite, optical | External-radio/convergence profiles only |
| Lab automation | ADOPT | labgrid, pytest | Reproducible hardware-in-loop evidence |

No row authorizes bundling, endorsement, or a fork. Project licenses, governance, security maintenance, and technical fit require review.
