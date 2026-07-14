# Codex prompt: compact rescue architecture and RFC 0002

Use the following prompt for the next repository update.

```text
You are updating the Harriet adaptive-communications project.

Repository: GroundWaveJack/GroundWave
Local checkout: C:\git\GroundWaveJack\GroundWave
Working branch: docs/platform-reframe
Draft pull request: #1 targeting main
Required Git identity: Jack <groundwavejack@users.noreply.github.com>

This is a bounded architecture, RFC, and test-design pass. Do not rename the GitHub account, repository, local directory, branch, remote, packages, domains, executables, modules, crates, protocol identifiers, or external resources. Do not merge the pull request, mark it ready, modify licenses, rewrite history, or edit docs/project/archive/**.

First verify:

- branch is docs/platform-reframe;
- worktree is clean;
- local HEAD matches origin/docs/platform-reframe;
- repository-local Git identity is exact;
- PR #1 is open, draft, and unmerged.

Stop without edits if any preflight condition is unexpected.

Read at minimum:

- AGENTS.md, README.md, PROJECT_STATE.md, VISION.md, DOCTRINE.md;
- ARCHITECTURE.md and THREAT_MODEL.md;
- docs/architecture/communication-envelope.md;
- docs/architecture/delivery-policy.md;
- docs/architecture/cache-and-custody.md;
- docs/architecture/distress-and-rescue.md;
- docs/hardware/deployable-relay.md;
- docs/hardware/marker.md;
- docs/integrations/reticulum.md;
- docs/development/testing-strategy.md and conformance.md;
- docs/project/open-questions.md and risks.md;
- docs/rfc/0001-adopt-harriet-name.md and the RFC template.
```

```text
Create docs/rfc/0002-compact-rescue-vertical-slice.md with status proposed. The RFC must define the minimum falsifiable vertical slice, not a complete platform or released product.

The RFC must integrate four requirements:

1. Compact communication contract and wire representation
   - The logical communication envelope is not copied in full into every packet.
   - Separate the canonical contract, compact initial representation, cached contract reference, and minimal extreme-constrained representation.
   - Use omission of defaults, profile codes, compact integers, relative lifetimes where safe, short scoped references, deterministic binary representation, and message- or session-level cryptographic amortization.
   - Do not select JSON or a verbose text format for constrained carriage.
   - Do not prematurely freeze a universal encoding before fixtures and at least two profile mappings exist.

2. Red Distress mode
   - One deliberate action sends a predefined authenticated distress state with location, location method and uncertainty, time, activity or mission profile, party or asset reference, and reply requirement.
   - The stable record is sent once or cached; compact heartbeats carry only changed state and a short incident reference.
   - Retransmission is adaptive, persistent but bounded, congestion-aware, battery-aware, and subject to airtime, replica, storage, legal, and expiry limits.
   - Transport receipt must not stop distress. Distinguish profile acceptance, custody, next-hop transfer, endpoint receipt, responder acceptance, human acknowledgment, sender cancellation, and expiry.
   - Default termination requires authenticated sender cancellation, policy-satisfying responder acceptance, or expiry.

3. Deployable rescue relay chain
   - Model an entrance relay bridging outward backhaul and inward constrained carriage.
   - Support droppable breadcrumb relays at bends, levels, obstacles, weak-margin points, and staging areas.
   - Preserve opaque payload handling, newest-state retention, duplicate suppression, bounded custody, cancellation propagation, partition evidence, and visible link uncertainty.
   - Directional inward transmission is a candidate deployment mode, not a guaranteed solution for caves, rubble, reinforced concrete, wet rock, metal compartments, or non-line-of-sight propagation.

4. Harriet markers
   - Model small incident-scoped markers for people, groups, responders, assets, hazards, and waypoints.
   - Support rescue handoff: a search team can mark a located group, continue searching, and allow a recovery team to accept and complete the task.
   - Location may be GNSS, stale GNSS, nearest relay, chain-relative, ranged, manually assigned, or last heard; method, age, uncertainty, and confidence must remain explicit.
   - Prevent covert permanent tracking through visible activation, temporary identifiers, expiry, bounded retention, authenticated assignment and clearance, and distinct person versus asset policy.
```

```text
The RFC must specify measurable byte and airtime budgets before implementation. Include a budget table for:

- first contact;
- established correspondent with cached identity and contract state;
- recurring Red Distress heartbeat;
- compact responder question and answer;
- marker heartbeat with unchanged location;
- cancellation or terminal record;
- fragmentation overhead and useful payload remaining.

Do not invent final byte counts without an encoding and profile fixture. Instead define target ceilings, measurement fields, and pass/fail gates. Require publication of physical or profile MTU, underlying transport overhead, Harriet overhead per message and fragment, authentication cost, useful payload, bitrate, airtime, retries, duty cycle, and energy use.

The first Reticulum-oriented demonstration must prove:

1. An ordinary-user or test harness activates Red Distress.
2. Harriet creates a deterministic integrity-bound contract and compact reference.
3. The smallest useful authenticated distress representation clears a constrained path.
4. At least three deployable relay roles form a path after direct connectivity is removed.
5. Duplicate heartbeats are suppressed and the newest authenticated state survives.
6. Multiple markers represent separate groups or assets without requiring GNSS.
7. A recovery task is accepted and distinguished from packet receipt.
8. An authenticated responder message changes cadence or requests compact information.
9. A relay removal creates visible partition or delayed-delivery behavior rather than false success.
10. Authenticated cancellation propagates and stale relays stop repeating the incident.
11. Byte, airtime, latency, retry, battery, and failure evidence is retained.

Explicit non-goals:

- no claim of certified life-safety operation;
- no claim of emergency-service, marine, aviation, satellite, or public-safety integration;
- no universal routing protocol;
- no full automatic semantic translation;
- no final hardware SKU, band, antenna, ingress rating, battery, or range commitment;
- no covert consumer tracking;
- no repository or package rename;
- no release or conformance claim.

Update only the current documents necessary for consistency: documentation index, roadmap, open questions, risks, glossary, architecture cross-links, hardware embodiments, testing strategy, and conformance plan. Preserve historical and repository-identifier uses of Groundwave.

Validation:

- markdownlint;
- typos;
- link checking;
- YAML validation where applicable;
- git diff --check;
- relative-link audit;
- archive object comparison;
- secret, identity, personal-path, private-address, and machine-name scans;
- search for unsupported implementation, qualification, emergency-service, range, and safety claims;
- classify every remaining non-archive Groundwave occurrence.

Review the focused diff carefully. Commit and push only after all checks pass, using:

docs: define compact rescue architecture

Keep PR #1 open, draft, and unmerged. Update its description with the new rescue-architecture scope and exact validation results. Return the commit SHA, changed-file summary, validation results, unresolved decisions, and PR state.
```
