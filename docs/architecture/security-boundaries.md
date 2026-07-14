# Security boundaries

Endpoints authorize content, recipients, transformations, and acknowledgment. Ordinary relays see only necessary forwarding metadata and opaque payloads. Caches add resource and availability trust but not content authority. Translation gateways cross a plaintext or semantic boundary and require explicit authorization, isolation, receipts, and revocation.

Profile adapters are parsers exposed to hostile input. They require strict limits, canonicalization, fuzzing, downgrade resistance, and version negotiation. See the [threat model](../../THREAT_MODEL.md).
