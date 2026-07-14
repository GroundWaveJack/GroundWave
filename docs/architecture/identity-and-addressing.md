# Identity and addressing

**State:** Architecture under design; not implemented.

Human, device, service, and group identities must not be collapsed. External profile addresses bind to a Groundwave identity only through explicit, verifiable statements with scope and expiration. Discovery does not itself establish trust.

The platform borrows cryptographic primitives and profile identifiers. It owns binding semantics, migration, provenance, and conformance. Privacy risks include stable correlation and reachability disclosure; pairwise identifiers and selective disclosure require evaluation.

Enrollment, key discovery, multi-device authority, rotation, recovery, delegation, expiration, revocation, compromise notification, conflicting updates, and stale offline state remain unresolved. A profile binding must state who asserted it, its scope and lifetime, verification state, and failure behavior. No key or address is assumed to prove a civil identity.
