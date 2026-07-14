# ADR 0010: Adopt Harriet as the public project name

**Status:** adopted

**Date:** 2026-07-14

**Supersedes / superseded by:** Supersedes [ADR 0009](0009-former-name-was-provisional.md); identifier migration completed by [ADR 0011](0011-complete-harriet-identifier-migration.md)

**Decision owner:** Jack

**Related RFC:** [RFC 0001](../rfc/0001-adopt-harriet-name.md)

## Context

The former working name was retained provisionally by ADR 0009. RFC 0001 records the maintainer's decision, cultural obligations, collision limits, staged migration, and rollback conditions.

## Decision

Adopt **Harriet** as the public project and platform name, in honor of Harriet Tubman. The pre-Harriet identifier becomes decision history while technical identifiers receive separate review.

At adoption, this decision did not rename or select a GitHub account, repository, local directory, branch, remote, domain, executable, package, crate, module, protocol identifier, or external resource. RFC 0003 and ADR 0011 later resolved the controlled owner, repository, local-path, and prefix convention.

## Consequences and limitations

Current normative documentation uses Harriet. RFC 0003 and ADR 0011 later authorize neutral historical wording and complete the controlled-identifier migration without rewriting Git history.

RFC 0001 defines permanent obligations for historical accuracy, ordinary-person accessibility, and prevention of trivialization, gamification, mascot use, and implied endorsement. The collision review is not trademark clearance or exclusivity. Package, domain, protocol, and external-contract identifiers remain unresolved.

## Security and privacy

No trust boundary, security property, privacy claim, or implementation changes. Future ordinary-user experience must expose simple privacy, urgency, degradation, and acknowledgment choices without requiring command-line or networking expertise. That is not a current-interface claim.

## Conformance evidence

Initial adoption evidence was a consistent documentation migration, current entry points, classified pre-Harriet references, preserved archive objects, and passing documentation, identity, and scope checks. RFC 0003 later permits neutral wording in current archive snapshots while the original objects remain available through Git history and the rollback tag.

Adoption records naming only. It does not assert implementation, testing, qualification, or release.

## Follow-up and review trigger

RFC 0003 and ADR 0011 resolve the controlled account and repository migration. Separate decisions must resolve domain, executable, package, crate, module, protocol, redirect, or external compatibility work. Reconsider through a public RFC and ADR if credible evidence shows cultural harm or misuse, material collision or legal risk, accessibility or exclusion concerns, or incompatible migration constraints.
