# Threat model

**State:** architecture under design. These are proposed invariants and release gates. No conforming implementation, independent assessment, or security certification exists.

## Scope and non-goals

This model covers the intended connective layer, endpoints, relays, caches, custody, trusted translators, profiles, updates, and reference hardware. External protocols retain their own threat models; profiles must declare differences.

Groundwave aims to protect content, intent, identity bindings, provenance, resources, and delivery evidence. It cannot guarantee a path, delivery, anonymity, traffic-analysis resistance, safe endpoints, universal legal operation, or faithful lossy transformation. A global observer, compromised endpoint, coerced gateway, or physical capture can defeat important goals.

## Assets and harm

Assets include content and derivatives; keys and bindings; intent and delivery policy; transformation provenance; acknowledgments and custody evidence; reachability observations; owner storage, energy, airtime, and bandwidth; update integrity; and recovery state.

Failure can expose relationships or location, impersonate a person, alter meaning, suppress urgent communication, falsely claim custody or delivery, exhaust resources, transmit unsafely, install hostile software, or turn a captured device into a source of sensitive history.

## Roles and adversaries

- **Endpoint owner:** sets local policy and protects keys; may make mistakes.
- **Ordinary relay:** forwards opaque payloads without plaintext or identity authority.
- **Cache or custodian:** accepts bounded retention responsibility; custody is not delivery.
- **Home relay:** has a declared relationship, not identity or location authority.
- **Trusted translator:** receives explicit, narrow authority for a named transformation.
- **Profile or adapter:** connects an external system and declares reduced guarantees.
- **Release maintainer:** can influence source, dependencies, builds, and updates.

Adversaries include observers, malicious peers, abusive authenticated senders, compromised or dishonest relays and custodians, Sybil populations, hostile networks, malicious modules, supply-chain attackers, stolen endpoints, and insiders with gateway or release access.

## Data flow and trust boundaries

An endpoint creates an intent contract and protected representations, then selects transports. Relays may observe link and timing metadata but should receive opaque content. Caches retain ciphertext under quotas. A custodian returns authenticated, scoped evidence before an upstream copy is eligible for deletion. Final delivery is separate.

Translation crosses the strongest routine boundary: an authorized gateway may receive plaintext, produce a derivative, and issue a receipt. Profiles cross semantic boundaries because addressing, acknowledgment, confidentiality, and delivery meanings differ. Expansion modules cross electrical, firmware, radio-frequency, and physical boundaries.

## Metadata and tracking

Reachability hints, last-contact observations, relay affinity, home-relay declarations, inventories, timing, size, radio fingerprints, and custody history can reveal relationships, movement, or location. Renaming them does not remove their tracking capability.

Proposed controls are minimization, purpose limitation, coarse fields, short expiry, local-first storage, selective disclosure, rotating identifiers where feasible, privileged-query audit, and deletion propagation where possible. Profiles must state what observers can correlate. The project must not create a general movement history or centralized social score.

## Identity lifecycle gaps

Enrollment, discovery, human-readable naming, multi-device membership, rotation, recovery, revocation, compromise notification, delegation, and cross-profile binding remain open. Documentation must not imply that a key proves a civil identity or that profile identifiers name the same person.

A future design must prevent silent substitution, expose verification state, scope delegation, support recovery without a required central service, and define conflicting-revocation and stale-offline behavior.

## Translation and semantic loss

Translation is opt-in, policy-bounded, and isolated. Proposed controls include least-privilege keys, per-operation authority, sandboxed parsers and codecs, input/output limits, no ambient message access, temporary-plaintext deletion, and receipts binding original and derived media types and digests, method, known loss, uncertainty, and retention.

A receipt proves what a gateway claims it did, not subjective fidelity or gateway honesty. Unsupported semantics and downgrade below the minimum representation fail explicitly. Translators cannot become universal trusted intermediaries.

## Cache and custody dishonesty

A cache can retain deleted data, discard early, lie about capacity, replay inventory, or bias admission. A custodian can acknowledge and drop content.

Proposed controls include acknowledgments bound to digest, custodian, policy, and expiry; separation of custody from delivery; bounded replication across failure domains; timeouts; privacy-preserving audits; and technical observations rather than centralized social scoring. Upstream deletion requires policy satisfaction, not a bare receipt. Secure remote deletion cannot be guaranteed.

## Sybil, abuse, and resource controls

Every path requires explicit byte, item, replica, hop, rate, airtime, energy, and lifetime bounds. Proposed mechanisms include admission control, owner reserves, fair queues, congestion feedback, local policy, duplicate suppression, backpressure, and costly-work isolation.

No universal Sybil defense exists. Identity cost, social trust, radio constraints, and resource proofs fail differently. Emergency priority must be authenticated or locally authorized, bounded, and auditable. Promotion grants work, never plaintext or governance authority.

## Malicious nodes and protocol handling

Nodes may forge routes, advertise false reachability, replay, suppress evidence, manipulate clocks or metrics, or exploit parsers. Proposed controls include integrity protection, intermittent-clock-aware replay defense, bounded parsers, canonical signed encodings, plausibility checks, diversity, fail-closed policy parsing, fuzzing, and fault injection. Multipath cannot exceed replica and airtime budgets silently.

## Supply chain and updates

Dependencies, build services, firmware, repositories, maintainers, and signing keys are attack surfaces. Proposed gates include pinned reviewed dependencies, inventories, artifact provenance, isolated signing, reproducible builds where practical, pre-install verification, rollback recovery, staged rollout, revocation, and a declared support window.

Bootstrap trust, offline update, compromised-signer recovery, and long-disconnection behavior remain unimplemented design work.

## Physical and expansion threats

Capture can expose sessions, plaintext, keys, debug ports, media, radio settings, and metadata. Proposed mitigations include minimal retention, protected storage and keys, lock and wipe policy, secure recovery, disabled production debug access, and tamper-evident—not tamper-proof—construction.

Expansion modules may overdraw power, inject buses, spoof identifiers, modify firmware, radiate unexpectedly, or damage a host. EEPROM data is a hint, never authority. The concept requires switched/current-limited power, safe-removal state, keyed mechanics, ESD protection, justified isolation, explicit driver authorization, and module-owned RF. Version 0.1 is not hot-swappable.

## Safety and regulatory defaults

Best effort does not authorize unrestricted transmission. Unknown radio profiles fail closed; configured regional and hardware limits bound airtime and media; emergency-service impersonation remains unavailable. Operators remain responsible for authorization, interference, export controls, and safety. The project claims no universal compliance.

## Proposed security invariants

1. Ordinary relays do not require plaintext.
2. Translation authority is narrow, revocable, and auditable.
3. Intent and minimum representation are integrity-protected end to end.
4. Custody evidence is authenticated and distinct from delivery.
5. Ambiguous or unauthenticated evidence never authorizes deletion.
6. Forwarding, replication, storage, energy, and airtime remain independently bounded.
7. Reachability metadata is minimized, scoped, expiring, and never identity authority.
8. Profiles declare confidentiality, addressing, acknowledgment, and semantic gaps.
9. Untrusted input is parsed within explicit limits.
10. Owner sovereignty and safe defaults override automatic contribution.

## Verification and release gates

| Area | Evidence required before a conforming release claim |
| --- | --- |
| Content and intent | Test vectors; tamper, replay, downgrade, and substitution tests |
| Translation | Authorization, fuzzing, isolation, receipt, loss, and refusal fixtures |
| Cache and custody | Quota, expiry, forged-evidence, black-hole, partition, and replica tests |
| Metadata | Field inventory, retention/deletion tests, and profile correlation review |
| Abuse | Exhaustion, Sybil, fairness, backpressure, and priority-abuse tests |
| Profiles | Semantic-gap review, malformed input, and interoperability evidence |
| Updates | Artifact, rollback, signer-recovery, dependency, and provenance review |
| Hardware | Power, removal, bus, debug, RF-policy, and capture tests |
| Release | Identity scan, proportionate independent review, and residual-risk record |

Passing tests is not certification. A release identifies the profile, version, relevant hardware, assumptions, unresolved findings, and assessor relationship.

## Residual risks and open decisions

Traffic analysis, radio direction finding, endpoint compromise, authorized-translator abuse, coerced operators, dishonest deletion, dependency compromise, denial of service, stale partition state, and misuse remain possible. Availability is bounded best effort.

Open decisions include identity and recovery, envelope cryptography, metadata disclosure, custody audit, deployment-specific Sybil controls, translator isolation, update roots and recovery, support lifetime, and profile-specific radio controls.

Report vulnerabilities through [SECURITY.md](SECURITY.md), not a public issue.
