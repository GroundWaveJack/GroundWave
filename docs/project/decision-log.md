# Decision log

**State:** Adopted decision index; implementation and evidence status remain separate.

| Decision | Status | Record |
| --- | --- | --- |
| Platform, not a single protocol | Adopted; supersedes hardware-only scope | [ADR 0001](../adr/0001-platform-not-single-protocol.md) |
| Human intent is stable abstraction | Adopted | [ADR 0002](../adr/0002-human-intent-is-the-stable-abstraction.md) |
| Adopt before inventing | Retained and broadened | [ADR 0003](../adr/0003-adopt-before-invent.md) |
| Reticulum is the first profile target | Supersedes Reticulum-as-platform; profile remains under design | [ADR 0004](../adr/0004-reticulum-is-a-supported-profile.md) |
| Translation is explicit | Adopted | [ADR 0005](../adr/0005-core-does-not-silently-translate.md) |
| BPv7 profile | Proposed evaluation | [ADR 0006](../adr/0006-bpv7-for-delay-tolerant-delivery.md) |
| OpenWrt first router target | Proposed target | [ADR 0007](../adr/0007-openwrt-first-router-target.md) |
| Hardware is reference design | Adopted | [ADR 0008](../adr/0008-hardware-embodiments-are-reference-designs.md) |
| Former working name provisional | Superseded | [ADR 0009](../adr/0009-former-name-was-provisional.md) |
| Harriet public project name | Adopted | [RFC 0001](../rfc/0001-adopt-harriet-name.md), [ADR 0010](../adr/0010-adopt-harriet-as-public-project-name.md) |
| Harriet controlled identifiers | Adopted migration; history preserved | [RFC 0003](../rfc/0003-complete-harriet-identifier-migration.md), [ADR 0011](../adr/0011-complete-harriet-identifier-migration.md) |

Fiscal sponsorship, a nonprofit entity, board structure, exact channel plans, fixed hardware SKUs, FieldNode-first delivery, and mandatory zero-subscription rules are not established facts. They require evidence or new decisions.

## Decision lifecycle

An RFC moves through proposed, discussion, disposition, and closed states. The decision owner closes it as accepted, revise, deferred, rejected, or withdrawn and records rationale, unresolved objections, and follow-up. Accepted architecture is captured in an ADR; acceptance alone does not imply implementation.

An ADR moves from proposed to adopted only through an explicit maintainer decision. It may later be superseded or deprecated, but remains in place with forward links. Implementation issues and evidence link back to the decision. Historical source documents move to the archive only when a file banner or adjacent archive manifest names their date, original status, current status, and superseding record. Authentic source snapshots may remain verbatim; archive files are never silently rewritten into current policy.
