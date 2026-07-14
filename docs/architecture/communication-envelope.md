# Communication envelope

The proposed envelope groups records without making them equally trusted or immutable. Its integrity-bound intent contract carries recipient binding, a payload-manifest digest, independent delivery policy, transformation authority, confidentiality, and required acknowledgment. Changing these fields creates a new contract or authorized derivative; a relay cannot rewrite them because a path is constrained.

The payload manifest identifies content objects, media types, digests, dependencies, protection bindings, and provenance. A digest establishes object identity within its scheme, not truth, authorship, or semantic equivalence.

Capabilities, reachability, route metrics, energy, queues, and candidate transformations are local planning context. Profile headers, hop consumption, attempt identifiers, and custody state are mutable forwarding state with profile-specific integrity rules. Evidence is append-only relative to the intent and names the contract, object or derivative, event class, issuer, time semantics, and verification material.

Sensitive capability and reachability data should be minimized, scoped, and expired. Canonical encoding, signature binding, disclosure tiers, and size limits remain open. Schema fixtures are a prerequisite for implementation claims.
