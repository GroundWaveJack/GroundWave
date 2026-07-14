# Harriet marker

**State:** Proposed rescue and asset reference class; no design is qualified.

A Harriet marker is a small, screenless, incident-scoped device that can be handed to a person or group, clipped to a responder, attached to an animal or asset, or left at a hazard or waypoint. Unlike a consumer crowd-location tag, it is intended to report through available Harriet profiles and deployable relay chains without requiring one company's phone network.

## Rescue workflow

A search team may find a stranded or injured group that cannot yet be evacuated. A responder activates a marker, assigns it to the incident, records the minimum useful state, and continues searching while a recovery team follows behind.

The assignment may include:

- person or group count;
- triage or injury category;
- mobility and immediate needs;
- responder remaining or continuing;
- location method, uncertainty, and timestamp;
- assigned recovery task and acknowledgment requirement;
- disclosure, expiry, and retention policy.

The marker begins a bounded heartbeat and immediately reports material changes. Recovery acceptance, arrival, evacuation, transfer, and marker clearance remain separate authenticated events.

## Marker roles

The same hardware may support distinct, visibly assigned roles:

- **Person or group marker:** temporary rescue location, condition, and recovery state.
- **Responder marker:** team accountability, separation, motion, and distress activation.
- **Asset marker:** medical bag, breathing apparatus, rope cache, robot, vehicle, vessel, or other incident equipment.
- **Hazard or waypoint marker:** unstable structure, blocked route, cave junction, air cache, safe area, or extraction point.

Role changes require an authenticated assignment event. A person marker must not silently become a permanent asset tracker.

## Location without satellite visibility

A marker report must state both location and method. Valid sources include current GNSS coordinates, stale GNSS coordinates with age and accuracy, nearest relay, path position within a relay chain, measured range to one or more nodes, manually assigned room or passage, last-known surface point, movement since a known point, or simply the last relay that heard it.

For caves and damaged structures, a path-relative statement may be more useful than latitude and longitude: entrance, relay chain, branch, level change, distance beyond a known node, and confidence. Estimated positions must never be displayed as exact fixes.

## Compact reporting

The detailed assignment record is transmitted once when possible. A recurring marker report should normally contain only mission and marker references, state, people or asset class, location reference or change, sequence, age, battery, and compact authentication.

A stationary marker should not repeat identical precise location on every cycle. It may send a short authenticated heartbeat referencing the last accepted state. Movement, worsening condition, responder interaction, low battery, or reassignment triggers an immediate update.

## Handoff and provenance

A marker can carry an incident-scoped chain of responsibility without exposing message plaintext to ordinary relays. Events may include activation, assignment, recovery request, task acceptance, team arrival, evacuation start, transfer, return to inventory, and clearance. Each event states its issuer, scope, time semantics, and evidence type.

The event history supports operational accountability; it is not proof that a person received appropriate care or that an asset remained physically secure. Incident systems must distinguish device receipt, task acceptance, physical arrival, and human confirmation.

## Privacy and anti-tracking boundaries

Markers create obvious surveillance risk. Person use requires visible or tactile activation indication, temporary mission identifiers, automatic expiry, bounded location retention, encrypted precise location when practical, explicit assignment and transfer, and authenticated clearance. Covert consumer tracking is outside the intended role.

Emergency use for an unconscious or incapacitated person requires an explicit incident policy and strict expiry. It must not become a general exception for silent permanent tracking. Public discovery should expose only the minimum needed to relay or identify an unverified distress state.

## Reference characteristics

Candidate hardware may be a key-fob or small puck with clip, strap, adhesive, magnetic, or equipment mounts; glove-operable activation; protected Red Distress control; visible identification; configurable light, vibration, or buzzer; GNSS where useful; short-range ranging or discovery; constrained long-range carriage; local protected storage; and weeks of standby with a shorter active reporting mode.

Exact radios, ranging systems, batteries, enclosures, ingress ratings, and location claims require measurement and qualification.

## Demonstration gate

A first demonstration should assign multiple markers to separate groups and assets along a deployable relay chain, carry their compact state outward, assign a recovery team, acknowledge the task, update one marker without repeating unchanged records, operate without GNSS, clear one marker, and prove that expired or cleared identifiers no longer report. Tests must include unauthorized reassignment, replay, covert activation indicators disabled by fault, stale location, low battery, lost relay path, and post-incident decommissioning.
