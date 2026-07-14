# Threat model

**State:** initial design threat model; no security certification

## Assets and goals

Protect content confidentiality and integrity, human intent, identity bindings, transformation provenance, delivery evidence, owner resources, and safe recovery. Availability is best effort and cannot be guaranteed.

## Adversaries

Consider passive observers, malicious peers, compromised relays or gateways, abusive senders, resource-exhaustion attackers, Sybil populations, supply-chain compromise, hostile networks, stolen endpoints, and operators making configuration mistakes. A global observer, compromised endpoint, or coerced authorized translator may defeat important privacy goals.

## Principal risks and controls

| Risk | Design control | Residual limitation |
| --- | --- | --- |
| Content interception | End-to-end protection; opaque relays | Endpoint compromise exposes content |
| Metadata correlation | Minimize, scope, expire, and selectively disclose hints | Timing and RF observation remain powerful |
| Silent semantic loss | Explicit authority and translation receipts | Receipts cannot prove subjective fidelity |
| Cache exhaustion | Quotas, admission control, expiration, replica budgets | Distributed low-rate abuse is difficult |
| Custody black hole | Authenticated acknowledgments, diversity, deadlines | Acknowledgment is not final delivery |
| Flooding and airtime capture | Hop/replica budgets, congestion queues, owner limits | Emergency prioritization can be abused |
| Adapter exploit | Memory-safe implementation preference, limits, fuzzing | Third-party stacks remain dependencies |
| Downgrade | Bind policy and minimum representation to signed intent | Users may authorize unsafe defaults |
| Malicious update | Reproducible releases, signatures, rollback design | Release governance is not implemented |
| Physical capture | At-rest protection, revocation, minimal retained data | Active unlocked devices remain vulnerable |

## Trust boundaries

Edges are trusted for their user's intent only. Relays are not trusted with plaintext. Caches are trusted only for bounded retention. Translators are explicitly trusted for a named transformation. Home relays are relationships, not identity authorities. External profiles retain their own threat models and must document semantic gaps.

## Privacy and safety

Do not collect “user tracking.” Reachability observations are purpose-limited, expiring, and disclosed minimally. Owner policy controls contributed storage, power, bandwidth, and airtime. Jurisdiction, spectrum rules, interference, emergency-service impersonation, and unsafe automatic transmission remain deployment responsibilities.

## Validation plan

Threat-model conformance requires abuse cases, malformed-envelope tests, quota tests, replay and downgrade tests, custody failure injection, receipt verification, metadata review, dependency review, and independent security assessment before a release claim.

Report vulnerabilities through [SECURITY.md](SECURITY.md), not a public issue.
