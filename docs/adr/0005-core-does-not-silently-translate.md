# ADR 0005: The core does not silently translate

**Status:** adopted, 2026-07-14

Ordinary relays forward opaque protected content. A gateway may translate only with explicit policy and trust, and must produce a receipt containing original and derived media types and digests, method, known loss, uncertainty, and original-retention state. Some paths will therefore be unusable when translation is forbidden.
