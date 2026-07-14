# Communication envelope

**State:** Architecture under design; not implemented.

The proposed envelope groups records without making them equally trusted or immutable. Its integrity-bound intent contract carries recipient binding, a payload-manifest digest, independent delivery policy, transformation authority, confidentiality, and required acknowledgment. Changing these fields creates a new contract or authorized derivative; a relay cannot rewrite them because a path is constrained.

The payload manifest identifies content objects, media types, digests, dependencies, protection bindings, and provenance. A digest establishes object identity within its scheme, not truth, authorship, or semantic equivalence.

Capabilities, reachability, route metrics, energy, queues, and candidate transformations are local planning context. Profile headers, hop consumption, attempt identifiers, and custody state are mutable forwarding state with profile-specific integrity rules. Evidence is append-only relative to the intent and names the contract, object or derivative, event class, issuer, time semantics, and verification material.

The logical contract and the constrained wire representation are separate artifacts. A canonical contract may be stored or exchanged once while later packets use compact profile codes, omitted defaults, short scoped references, relative lifetimes where safe, and message- or session-level authentication context. Full identity, policy, and signature material must not be repeated on every fragment merely because the logical envelope contains it.

Sensitive capability and reachability data should be minimized, scoped, and expired. Canonical encoding, compact representations, signature binding, disclosure tiers, byte ceilings, and size limits remain open. Schema and profile fixtures with measured useful payload and airtime are prerequisites for implementation claims.
