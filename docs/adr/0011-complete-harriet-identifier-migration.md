# ADR 0011: Complete Harriet identifier migration

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes / superseded by:** Completes [ADR 0010](0010-adopt-harriet-as-public-project-name.md) and supersedes any indefinite live-identifier exception

**Related RFC:** [RFC 0003](../rfc/0003-complete-harriet-identifier-migration.md)

## Context

RFC 0001 and ADR 0010 adopted Harriet while deferring controlled technical identifiers. The migration inventory and rollback preparation now support a bounded change without rewriting history.

## Decision

Adopt `HarrietProject/Harriet` as the canonical GitHub location, `harriet-*` for satellite repositories, `C:\git\HarrietProject\Harriet` for the canonical local checkout, and `harriet` as the prefix convention for future or safely migrated project-controlled implementation identifiers.

Remove the pre-Harriet identifier from current tracked content, paths, and live controlled metadata. Preserve prior Git objects and describe historical scope using neutral terms.

## Consequences and limitations

Current links, remotes, metadata, and contributor instructions use Harriet. Provider redirects are compatibility aids only. External consumers and published contracts require individual verification or explicit deprecated aliases. This ADR does not claim trademark, package, domain, certification, implementation, or release clearance.

## Verification and review trigger

Evidence includes preserved repository IDs, the rollback tag and bundle, zero-occurrence scans of current controlled surfaces, documentation checks, verified commit metadata, and the still-draft pull request. Review if cultural harm, a material collision, redirect failure, or external-contract evidence requires a different migration strategy.
