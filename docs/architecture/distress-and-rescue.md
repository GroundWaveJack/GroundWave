# Distress and rescue operation

**State:** Architecture under design; not implemented or approved for life-safety reliance.

The minimum falsifiable slice, compact representations, and measurement gates are proposed in [RFC 0002](../rfc/0002-compact-rescue-vertical-slice.md).

Harriet should support a predefined **Red Distress** intent for situations where a person may have seconds, one usable hand, poor visibility, or no usable screen. A deliberate physical or software action creates one authenticated logical emergency record and begins bounded retransmission across every permitted profile.

Red Distress is a Harriet intent class, not a claim of compatibility with regulated emergency beacons, marine distress systems, aviation systems, public-safety networks, or emergency services. Deployments must state which external systems are actually integrated and qualified.

## One-action activation

The ordinary interaction should be: activate Red Distress, confirm through a tactile or unmistakable indication, and let Harriet send the predefined emergency state. A hardware control should be glove-operable, protected against accidental activation, usable while the main display is off, and supported by a cancellation procedure that is difficult to trigger accidentally.

Before an activity, a person may prepare an incident profile such as hiking, hunting, boating, caving, climbing, skydiving, off-road travel, or rescue work. The profile may hold route, party, vessel, vehicle, medical, and emergency-contact information under explicit disclosure policy. Activation must not wait for the user to complete a form.

## Emergency state

The stable incident record can include:

- incident identifier and authenticated origin;
- Red Distress class and activation time;
- person, group, vessel, vehicle, or mission reference;
- activity profile and party count;
- last reliable location, method, age, and uncertainty;
- requested response and authorized audience;
- confidentiality, expiry, and cancellation policy;
- optional medical or trip details authorized before the emergency.

The recurring update must be much smaller than the stable record. It should normally carry only a short incident reference, sequence, age, status flags, material location change, battery state, requested acknowledgment, and compact authentication. The full contract is sent once, cached, or retrieved by reference rather than repeated on every fragment.

## Bounded persistence

Red Distress is persistent, not infinite. A profile defines an adaptive cycle with:

- an initial burst bounded by airtime and replica budgets;
- progressively longer heartbeat intervals;
- immediate updates for material state or location changes;
- congestion backoff and randomized timing;
- battery-reserve and legal duty-cycle floors;
- expiry and maximum retention periods;
- a sparse survival-beacon mode when power is critical.

Priority never authorizes unlimited flooding. Relays reserve only bounded emergency queue, storage, and airtime. They retain the newest authenticated state, suppress duplicates and superseded updates, and preserve terminal cancellation long enough to stop stale propagation.

## Stop and acknowledgment semantics

Transport or relay receipt does not end Red Distress. The sender policy distinguishes profile acceptance, custody acceptance, next-hop transfer, endpoint receipt, responder acceptance, human acknowledgment, sender cancellation, and expiry.

The default should continue until the origin cancels it, an explicitly authorized responder accepts responsibility under the requested policy, or the incident expires. A responder may instruct Harriet to continue, reduce cadence, provide selected information, switch to two-way exchange, or stop. Every instruction must be authenticated and scoped to the incident.

## Compact responder exchange

After contact, Harriet should prefer low-cost questions and coded answers when links are constrained. Questions such as ability to move, injury severity, party count, shelter, exact-location approval, and immediate hazards can be represented as compact enumerated fields or authenticated bits rather than verbose text.

## Location and representation

A report must identify how location was determined and never present an estimate as exact. Valid forms include current global navigation satellite system coordinates, stale coordinates with age and accuracy, a known trail or cave entrance, nearest relay, distance and direction from a relay, manually assigned room or passage, or last-heard position.

Location may be disclosed in tiers: exact encrypted coordinates, coarse area, named region, path-relative location, or no location. Harriet must not silently broaden the audience or precision because delivery is difficult.

The minimum useful representation should remain deliverable when richer content cannot pass. A compact authenticated statement that identifies the incident, distress class, approximate location, and need for reply is preferable to a large emergency form that never clears the link.

## Abuse and safety boundaries

Red Distress requires replay protection, duplicate suppression, authenticated cancellation, rate limits, and separate handling for known authenticated origins and unverified distress. Unverified distress may receive a constrained carriage class rather than automatic rejection, but it must remain visibly unverified.

No implementation may claim connection to emergency services, guaranteed rescue, guaranteed location, or certified life-safety operation without named external interfaces, qualification evidence, operating limits, and responsible authorities.

## Required evidence

A prototype must demonstrate activation, compact periodic updates, bounded relay behavior, duplicate suppression, authenticated responder acceptance, cadence change, cancellation, stale-copy suppression, partition recovery, and measured byte and airtime budgets. Tests must cover first contact, established correspondents, stale or unavailable location, low battery, malicious replay, lost cancellation, and a path that is intermittent rather than continuously connected.
