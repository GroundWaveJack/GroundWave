# Translation and loss

Ordinary relays do not translate protected content. An explicitly trusted gateway receives narrowly scoped authority and emits a translation receipt containing original media type and digest, derived type and digest, method and version, known loss, uncertain content, and whether the original was retained.

Translation flows through local policy and profile negotiation. If an authorized derivative is required, the trusted translator produces the derivative and receipt, then returns both through policy evaluation and profile selection because size, media type, confidentiality, and minimum representation may have changed. Unsupported or forbidden translation produces an explicit refusal.

A receipt establishes provenance and declared loss; it does not prove semantic equivalence, generated-content correctness, recipient comprehension, or that all loss was detected. Conformance therefore tests authorization, provenance continuity, loss declaration, and refusal.

“Rosetta” is only a working metaphor: “Rosetta preserves what you mean while changing how it travels.” It is not an approved component or public name. Receipt verification and policy refusal are conformance requirements; universal plaintext access is forbidden.
