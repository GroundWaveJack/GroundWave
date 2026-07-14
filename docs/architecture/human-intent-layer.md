# Human-intent layer

**State:** Architecture under design; not implemented.

An intent names a recipient or audience, payload purpose, urgency, acceptable transformations, minimum representation, confidentiality, and required acknowledgment. Local policy validates it before transmission. Defaults must be conservative: no undisclosed lossy conversion, public forwarding, or expanded audience.

Intent is a constrained, reviewable contract, not a natural-language promise that software can fully understand. Free-form user text remains payload, not unbounded planner authority. The platform can preserve the declared contract, provenance, known loss, and explicit refusal; it cannot guarantee that human meaning, tone, or context survives transformation.

Local policy may narrow, confirm, or refuse an intent. It may not expand audience, relax confidentiality, authorize a trusted gateway, or lower required acknowledgment without an accountable authorization rule.

Conformance requires equivalent intents to retain meaning across profiles and requires unsupported semantics to fail explicitly. Open questions include group intent, delegation, revocation, and accessible user confirmation.
