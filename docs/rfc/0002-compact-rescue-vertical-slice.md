# RFC 0002: Compact rescue vertical slice

- **Status:** Proposed
- **Owner:** Jack
- **Created:** 2026-07-14
- **Review trigger:** Encoding fixtures and independently reviewable mappings for at least two constrained profiles
- **Related decisions:** [RFC 0001](0001-adopt-harriet-name.md); no adopted architecture decision

## Summary

This RFC proposes the smallest falsifiable rescue slice for Harriet: a compact communication contract, Red Distress, an entrance-and-breadcrumb relay chain, and incident-scoped markers. It defines testable boundaries and evidence gates, not a complete platform, implementation, release, or life-safety product.

The slice must preserve authenticated intent and typed evidence while using constrained carriage efficiently. The logical communication envelope is not copied into every packet. A stable canonical contract is integrity-bound once and may be retried or cached under bounded policy; later state uses compact, incident-scoped references.

## Contract and representation model

The canonical contract binds:

- contract version, incident identifier, authenticated origin, and intended audience;
- Red Distress class, activation time semantics, activity or mission profile, and person, group, or asset reference;
- location value, method, age, uncertainty, and confidence when location is present;
- reply requirement and independently expressed lifetime, priority, replica, custody, acknowledgment, confidentiality, and minimum-representation policy;
- payload-manifest digest, transformation authority, expiry, cancellation authority, and authentication context.

These are logical fields, not a mandate to transmit a full header on every carriage unit. The slice defines four representations:

| Representation | Required behavior |
| --- | --- |
| Canonical contract | Deterministic, integrity-bound stable record sufficient to interpret the incident and policy. It is created once but may be retried, cached, or recovered under bounded policy. |
| Compact initial | Self-contained authenticated first-contact record using a profile code, non-default policy, compact incident reference, essential distress and location evidence, reply requirement, and authentication binding. It requires no cached Harriet state. |
| Cached contract reference | Scoped short reference, representation type, replay-resistant sequence or epoch, changed-field indication, changed values, and authentication tag. It must resolve uniquely or fail closed and request the canonical record. |
| Extreme-constrained | Independently authenticatable incident reference, distress state, urgency, and reply signal. Missing semantic context remains visibly unresolved; this form never claims equivalence to the canonical contract. |

Constrained representations use deterministic binary encoding, bounded profile and enumeration codes, compact unsigned integers, omission of versioned defaults, and short references scoped to origin, incident, profile, and cryptographic context. Relative lifetimes are permitted only with a declared basis and uncertainty that makes expiry unambiguous. Reference collision, cache eviction, or rebinding must cause explicit recovery or refusal, never association with a different contract.

For the extreme-constrained form, independently authenticatable means verification under a fixture-declared key or identity context, which may itself be cached; the fixture includes that prerequisite and its byte cost. A receiver without the declared verification context exposes the record as unresolved and must not treat it as authenticated.

JSON and verbose text are not candidate constrained-carriage encodings. This RFC does not select a universal binary encoding. That decision requires canonical fixtures, measured budgets, parser limits, and mappings for at least two profiles.

### Authentication amortization

The canonical digest may be authenticated once and referenced by later records. Message- or session-level authentication may amortize key and signature material, but every accepted update still binds the contract reference, incident, sender or authorized role, representation type, changed state, and replay context. Fixtures must measure setup, steady-state, rekey, restart, loss-recovery, and authentication costs. Amortization must not weaken cancellation authorization, cross-incident separation, or replay resistance.

## Red Distress state machine

One deliberate, guarded action creates the predefined authenticated state without waiting for a form. The device provides an unmistakable activation indication. The stable state contains the contract fields above; compact heartbeats normally carry only the incident reference, replay state, and material changes.

Retransmission is adaptive and persistent but bounded. Each profile declares initial-burst, heartbeat, retry, replica, storage, airtime, legal duty-cycle, energy-reserve, congestion-backoff, and expiry limits. Priority cannot override those limits. Relays retain the newest authenticated state, suppress duplicates and superseded updates, and retain authenticated terminal state long enough to quench stale propagation.

The following evidence classes remain distinct:

1. profile acceptance;
2. custody acceptance;
3. next-hop transfer;
4. endpoint receipt;
5. responder acceptance;
6. human acknowledgment;
7. sender cancellation;
8. expiry.

Profile acceptance, custody, transfer, endpoint receipt, and generic acknowledgment do not stop Red Distress. By default, transmission ends only on authenticated sender cancellation, policy-satisfying acceptance by an explicitly authorized responder, or expiry. Responder acceptance identifies the authorized role, incident, accepted task, scope, replay context, and policy condition satisfied. Authenticated responder questions or instructions may request compact information or change cadence without falsely asserting rescue acceptance.

## Deployable relay chain

The proposed field topology contains an entrance relay and at least three deployable breadcrumb relay roles. The entrance relay bridges an explicitly supported outward backhaul to inward constrained carriage. Breadcrumbs are candidates for bends, level changes, obstacles, weak-margin points, and staging areas.

Ordinary relay participation does not grant plaintext access. Relays forward opaque protected payloads and minimum profile metadata, preserve newest authenticated incident state, suppress duplicates, apply bounded custody, carry cancellation inward and outward, and report partition and link-uncertainty evidence. Freshness, duplicate, and cancellation handling uses only explicitly disclosed, integrity-protected ordering and record-type metadata, or is delegated to an authorized endpoint. Any plaintext-capable or translating role requires separate declared authority.

Directional inward transmission is a candidate deployment technique, not a guarantee for caves, rubble, reinforced concrete, wet rock, metal compartments, or non-line-of-sight propagation. Placement follows measured link margin and uncertainty. Removal, exhaustion, one-way reachability, or partition must become visible evidence or delayed-delivery state, never invented reachability.

## Incident-scoped markers

Markers represent incident-scoped people, groups, responders, assets, hazards, or waypoints. Person and asset policy remain distinct. Assignment, transfer, task acceptance, arrival, recovery, handoff, clearance, and device receipt are separately authenticated event types.

A search team may assign a marker to a located group and continue. A recovery team may then issue responder acceptance for that task and later record arrival, transfer, completion, or clearance. Packet receipt is not task acceptance, and task acceptance is not physical recovery.

Location may be current or stale GNSS, nearest-relay, chain-relative, ranged, manually assigned, or last-heard evidence. Every location record carries method, age or time semantics, uncertainty, and confidence. An unchanged marker heartbeat references prior location rather than restating it.

Visible activation, temporary mission identifiers, automatic expiry, bounded retention, authenticated assignment and clearance, and explicit person-versus-asset policy constrain tracking misuse. Public discovery exposes only the incident minimum. Covert permanent consumer tracking is outside scope.

## Measurement budget and gates

Every fixture registers numeric target ceilings before implementation measurement begins. A target may differ by profile, but a test run with `TBD` ceilings is invalid.

| Scenario | Target ceiling required before test | Required pass condition |
| --- | --- | --- |
| First contact | Bytes, maximum fragments, reassembly time, retries, airtime, energy, and minimum useful bytes and ratio | Compact initial authenticates without cached state; fragments remain bounded. |
| Established correspondent with cached identity and contract state | Bytes, one-unit payload limit, retries, airtime, energy, and minimum useful bytes and ratio | Reference resolves uniquely or fails closed; no full-contract repetition. |
| Extreme-constrained distress | Bytes, authentication cost, one-unit or fragment limit, retries, airtime, energy, and minimum useful bytes and ratio | Authenticates under the declared verification prerequisite and exposes all unresolved context. |
| Recurring Red Distress heartbeat | Bytes, one-unit payload limit, cadence, retries, airtime, duty cycle, energy, and minimum useful bytes and ratio | Changed state authenticates; duplicate and superseded state are suppressed. |
| Compact responder question and answer | Separate byte, airtime, retry, energy, and minimum useful-byte and ratio ceilings for question and answer | Each direction fits one selected profile payload unit and remains incident-scoped. |
| Marker heartbeat, unchanged location | Bytes, one-unit payload limit, cadence, retries, airtime, energy, and minimum useful bytes and ratio | Prior location is referenced with age; no false precision is introduced. |
| Cancellation or terminal record | Bytes, one-unit payload limit, retries, airtime, propagation window, energy, and minimum useful bytes and ratio | Authority and replay context verify; stale relays quench within the declared window. |
| Each fragment | Harriet and transport overhead, authentication allocation, useful bytes and ratio, airtime, retries, and energy | Total does not exceed measured MTU; useful payload meets the registered minimum. |

For every row, evidence publishes the fixture and profile versions, physical or profile MTU, underlying transport overhead, Harriet overhead per message and fragment, authentication cost, useful payload bytes and ratio, bitrate, calculated and measured airtime, retry ceiling and actual attempts, duty-cycle allocation, energy per attempt, and total scenario energy. Battery-life claims require measured capacity and load evidence.

Each measured result must be at or below every ceiling and at or above every useful-payload minimum registered for its row. A field may be marked not applicable only with a fixture-specific rationale. Attempts fail the gate when they exceed any declared byte, fragment, reassembly-time, retry, replica, storage, airtime, legal duty-cycle, cadence, propagation-window, expiry, or energy ceiling, or miss a required useful-byte or ratio minimum. First-contact and amortized cryptographic cost are reported separately. Restart or loss must never produce unauthenticated acceptance.

## First Reticulum-oriented demonstration

This is a proposed test, not evidence that Reticulum implements Harriet semantics. The adapter must disclose unsupported or adjacent mappings. A passing demonstration must retain reproducible fixtures and show all of the following:

1. An ordinary-user interaction or test harness deliberately activates Red Distress.
2. Harriet creates deterministic, integrity-bound contract bytes and a scoped compact reference.
3. The extreme-constrained authenticated distress form clears the selected constrained path while exposing unresolved context.
4. An entrance role and at least three breadcrumb relay roles form a path after direct connectivity is removed.
5. Duplicate heartbeats are suppressed and the newest authenticated state survives.
6. Multiple markers represent separate groups or assets without requiring GNSS.
7. Recovery-task responder acceptance is authenticated and distinguished from packet receipt.
8. An authenticated responder message changes cadence or requests compact information.
9. Removing a relay produces visible partition evidence or delayed delivery, not false success.
10. Authenticated cancellation propagates and stale relays stop repeating the incident within the fixture ceiling.
11. Encoded bytes, airtime, latency, attempts, retry behavior, energy, topology, failure evidence, and limitations are retained.

## Security and failure conditions

Tests cover replay, reference collision, cache loss, restart, stale cancellation, false responder authority, duplicate identity, malicious relay replacement, corrupted state, one-way links, loops, congestion, exhausted storage or energy, location staleness, unauthorized marker reassignment, and post-incident identifier expiry. Unknown codes, ambiguous lifetime, unresolved references, and invalid authority fail visibly.

Custody acceptance never proves final delivery. Upstream deletion continues to require authenticated custody evidence and the full delivery policy, including any required diversity. Ordinary relays gain no implicit content, translation, assignment, or archive authority.

## Non-goals

- certified life-safety operation or guaranteed rescue, location, propagation, or range;
- claimed integration with emergency services, marine, aviation, satellite, or public-safety systems;
- a universal routing protocol or full automatic semantic translation;
- a final encoding before fixtures and two profile mappings;
- final hardware SKU, band, antenna, ingress rating, battery, or range commitments;
- covert consumer tracking;
- repository, package, or protocol-identifier renaming;
- implementation, qualification, release, or conformance claims.

## Consequences, limitations, and open decisions

The proposal makes the first slice measurable and keeps receipt semantics, field uncertainty, and resource bounds explicit. It also adds state, cache-recovery, replay, authorization, and fixture obligations. It cannot establish useful radio propagation, responder availability, safety certification, or cross-profile interoperability.

Open decisions include the binary encoding; numeric ceilings; two initial profile mappings; responder-authorization policy; short-reference collision and recovery details; session restart and rekey behavior; path-relative uncertainty encoding; and which Reticulum semantics require adjacent metadata or extensions.

The RFC should be revised or rejected if two profile mappings cannot preserve the contract and stop semantics within predeclared budgets, if the extreme representation cannot remain authentically scoped without dangerous misinterpretation, or if field tests show the relay and marker model creates false reachability or unacceptable tracking risk.
