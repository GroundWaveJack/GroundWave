# Conformance

**State:** Process under design; no executable conformance suite exists.

Conformance applies to a named specification version and profile. A suite should verify envelope parsing and canonicalization, compact-reference resolution, byte ceilings, identity bindings, policy refusal, delivery dimensions, custody transitions, receipt provenance, adapter mappings, quotas, and downgrade behavior. Rescue conformance for [RFC 0002](../rfc/0002-compact-rescue-vertical-slice.md) additionally requires a named encoding and profile fixture; all four representation forms; target-ceiling pass/fail results; typed receipt, responder-acceptance, and stop transitions; an entrance and at least three breadcrumb relay roles; separate no-GNSS markers; visible partition behavior; stale-relay cancellation; and retained measurement evidence.

Levels are core semantic, profile interoperability, security behavior, and hardware embodiment. Self-tested and independently reproduced results are distinguished. No suite or conforming implementation exists today.

Each result identifies specification and suite revisions, implementation revision, level, environment, fixtures, expected and actual outcomes, exclusions, and artifact digests. “Conformant” without this scope is invalid. Failures remain visible; waivers name an owner, rationale, risk, and expiration.

Core semantic conformance cannot imply adapter interoperability, security assurance, hardware qualification, or release support. A profile must publish required, optional, and unsupported semantics plus refusal behavior before it can define a pass gate.
