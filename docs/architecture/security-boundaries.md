# Security boundaries

**State:** Architecture under design; not implemented.

Endpoints authorize content, recipients, transformations, and acknowledgment. The Groundwave ordinary-relay role does not require plaintext or content authority. A profile may carry sender-authorized plaintext, but it must disclose the resulting content and metadata visibility. A node allowed to inspect, transform, or otherwise use plaintext is operating under an explicitly declared trusted or profile-specific role for that operation; plaintext access is never silently inherited from relay participation. Caches add resource and availability trust but not content authority. Translation gateways cross a plaintext or semantic boundary and require explicit authorization, isolation, receipts, and revocation.

Profile adapters are parsers exposed to hostile input. They require strict limits, canonicalization, fuzzing, downgrade resistance, and version negotiation. See the [threat model](../../THREAT_MODEL.md).
