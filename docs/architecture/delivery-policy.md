# Delivery policy

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
