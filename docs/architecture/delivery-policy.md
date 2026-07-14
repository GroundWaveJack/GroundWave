# Delivery policy

**State:** Architecture under design; not implemented.

Delivery dimensions remain independent:

| Dimension | Question |
| --- | --- |
| Lifetime | When is the message no longer useful? |
| Hop budget | How much forwarding depth is allowed? |
| Replica budget | How many concurrent copies are allowed? |
| Priority | Which local queue should serve it first? |
| Deadline | When must useful delivery occur? |
| Custody | Who may accept retention responsibility? |
| Acknowledgment | What evidence ends sender action? |
| Payload class | What handling constraints apply? |
| Minimum representation | What is still meaningful? |
| Preferred relay | Is an explicit relationship favored? |
| Confidentiality | Who may access content and metadata? |

A single TTL cannot represent these policies. Implementations must enforce local quotas and avoid turning priority into unlimited preemption.

Routing answers how a carriage system reaches a next hop or destination. Harriet's delivery overlay answers whether, when, in what representation, and under whose custody another attempt is permitted. Adapters must map each policy dimension with documented semantics, narrow it safely, or refuse it.

Acknowledgment classes are distinct: profile acceptance proves only queuing; custody acceptance proves bounded retention responsibility; next-hop transfer proves authenticated receipt by that peer; endpoint receipt proves object receipt; representation acceptance proves validation of a derivative; and explicit human acknowledgment proves only the defined user action. Evidence must bind the event class, issuer, intent contract, object digest, and replay context.

For proposed Red Distress stop conditions and responder acceptance, see [RFC 0002](../rfc/0002-compact-rescue-vertical-slice.md).
