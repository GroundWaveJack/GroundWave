# Architecture overview

**State:** Architecture under design; not implemented. Adopted constraints are recorded in [doctrine](../../DOCTRINE.md) and [ADRs](../adr/).

Harriet is a connective layer between human intent and independently evolving carriage systems. Endpoints create communication envelopes; planners choose policy-compliant paths and representations; adapters map to external transports; relays and caches contribute bounded resources; recipients return evidence appropriate to the requested acknowledgment.

The logical core is a set of contracts, not a required monolith: intent authoring, local policy evaluation, planning, representation, profile adaptation, carriage, bounded relay or custody, and evidence verification may be deployed separately.

The architecture separates four state classes: (1) the sender-authorized, integrity-bound intent contract and payload manifest; (2) sensitive local planning context such as capabilities, contacts, energy, queues, and reachability observations; (3) mutable forwarding state such as hop consumption, queue state, profile headers, and custody transitions; and (4) authenticated evidence of a precisely named event.

The design borrows cryptography, codecs, routing, storage, radio, and delay-tolerant protocols. It owns policy separation, provenance, declared loss, explicit refusal, profile contracts, delivery-overlay state, and cross-profile conformance. Semantic preservation is deliberately narrow: the platform cannot prove that arbitrary human meaning survived a lossy transformation.

The whole architecture is under design. Limits include absent schemas, untested planner behavior, metadata leakage, adapter mismatch, and no demonstrated implementation.
