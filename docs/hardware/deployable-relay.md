# Deployable relay

**State:** Proposed rescue reference class; no design is qualified.

A deployable relay extends a Harriet path into a cave, tunnel, mine, collapsed building, ship compartment, damaged structure, or other environment where ordinary communication stops. It is placed at an entrance, junction, obstruction, staging point, or link-margin boundary and contributes bounded relay, cache, and custody capabilities.

The entrance device bridges two different environments. Its outward side may use cellular, satellite, Wi-Fi, Ethernet, a vehicle Base, or another authorized backhaul. Its inward side may use a constrained radio, directional antenna, wired extension, or another profile chosen for obstruction, low bitrate, long listening windows, and store-and-forward operation.

## Relay chain

One entrance relay may improve link margin, but a chain of droppable relays creates a communication trail behind a rescue team, explorer, robot, or drone. Nodes can be placed before bends, level changes, reinforced barriers, rubble, or any point where measured margin becomes unsafe.

Each relay should expose:

- upstream and downstream neighbor state;
- link quality, freshness, and uncertainty;
- battery state and estimated operating window;
- queue, cache, and custody limits;
- active distress records and terminal cancellations;
- chain partition or weak-segment evidence;
- its physical placement or manually assigned waypoint.

The team should not configure routing tables during deployment. The profile should discover eligible neighbors, reject unsafe policy downgrades, and indicate whether the node has a usable upstream path.

## Deployment interaction

Activation should require one deliberate action such as pulling a tab or pressing a guarded control. Feedback must work in darkness, noise, gloves, and stress. A minimal indicator set can distinguish upstream confirmed, marginal path, no path, active distress carriage, low battery, and fault. Visible, tactile, and audible cues require separate operating profiles because silence may be essential.

A responder should be able to place a relay, confirm that it joined the chain, and continue. A robot may release a node automatically when measured backhaul margin falls below an approved threshold, but automatic placement requires its own safety and recovery tests.

## Directional and obstructed propagation

An entrance relay may use a directional inward antenna to concentrate energy and reduce wasted outward radiation. Directionality is not assumed to solve cave or structural propagation. Wet rock, bends, rubble, reinforced concrete, metal compartments, polarization, reflections, and local dead zones can dominate geometric distance.

Profiles should permit antenna diversity, external antennas, alternate bands or transports, wired extensions, and omnidirectional breadcrumb nodes. Placement decisions must use measured link evidence rather than a nominal range claim.

## Data handling

A deployable relay normally handles opaque protected payloads. It needs only the minimum profile metadata required for forwarding, duplicate suppression, expiry, bounded custody, priority, and authenticated cancellation. It does not inherit authority to inspect, translate, broaden, or permanently archive incident content.

During Red Distress, the relay retains the newest authenticated incident state, prioritizes the initial distress record over redundant heartbeats, suppresses stale copies, and carries responder instructions inward. Emergency treatment remains bounded by owner, power, storage, spectrum, congestion, and incident policy.

## Reference characteristics

Candidate embodiments may be rugged pucks, short canisters, magnetic or strapped nodes, cable-lowered relays, robot payloads, or longer-duration entrance stations. Useful characteristics include impact and ingress resistance, glove operation, high-visibility and low-visibility markings, replaceable or rechargeable power, external antenna options, simple local indicators, local protected storage, authenticated updates, and explicit decommissioning.

Exact radios, batteries, enclosures, ingress ratings, antenna gains, bands, and regional configurations remain qualification outputs rather than permanent requirements.

## Failure and recovery

Required failure cases include a removed or crushed relay, exhausted battery, malicious replacement, corrupted state, duplicate identity, stale neighbor data, lost cancellation, one-way reachability, chain loops, congestion, intermittent partitions, and a device recovered after the incident. The chain must fail visibly and must not invent continuous reachability.

## Demonstration gate

A first demonstration should place an entrance relay, extend a path with at least three drop relays, intentionally lose direct connectivity, carry a compact Red Distress record outward, return an authenticated responder message, remove one relay, demonstrate partition handling or delayed store-and-forward, cancel the incident, and prove that stale relays stop repeating it. The report must include topology, obstruction, radios and profiles, byte counts, airtime, latency, battery use, failures, and limitations.
