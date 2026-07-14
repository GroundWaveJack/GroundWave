# Conformance

Conformance applies to a named specification version and profile. A suite should verify envelope parsing and canonicalization, identity bindings, policy refusal, delivery dimensions, custody transitions, receipt provenance, adapter mappings, quotas, and downgrade behavior.

Levels are core semantic, profile interoperability, security behavior, and hardware embodiment. Self-tested and independently reproduced results are distinguished. No suite or conforming implementation exists today.

Each result identifies specification and suite revisions, implementation revision, level, environment, fixtures, expected and actual outcomes, exclusions, and artifact digests. “Conformant” without this scope is invalid. Failures remain visible; waivers name an owner, rationale, risk, and expiration.

Core semantic conformance cannot imply adapter interoperability, security assurance, hardware qualification, or release support. A profile must publish required, optional, and unsupported semantics plus refusal behavior before it can define a pass gate.
