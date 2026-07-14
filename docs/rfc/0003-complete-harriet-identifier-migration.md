# RFC 0003: Complete Harriet identifier migration

**Status:** accepted

**Date:** 2026-07-14

**Author and decision owner:** Jack

**Disposition:** accepted for the bounded migration described here

## Summary

Complete the migration of current, controlled project identifiers to Harriet. The canonical GitHub owner is `HarrietProject`, the canonical repository is `Harriet`, satellite repositories use `harriet-*`, and project-controlled package, executable, module, crate, image, and namespace identifiers use `harriet` when such identifiers are introduced or safely migrated.

This decision removes the pre-Harriet identifier from the current tracked tree and live resources under project control. It does not rewrite Git history, erase third-party caches or forks, or promise that platform redirect records disappear.

## Authority and stewardship

This RFC supersedes RFC 0001's staged exception that allowed live pre-Harriet identifiers to remain during review. It does not weaken the attribution, cultural-stewardship, accessibility, anti-trivialization, or anti-endorsement obligations in [Why Harriet](../../WHY_HARRIET.md) and [RFC 0001](0001-adopt-harriet-name.md).

The decision is not trademark, domain, package-registry, certification, or legal clearance. Unpublished identifiers are not registered merely to occupy names.

## Mapping

| Surface | Pre-migration role | Canonical target |
| --- | --- | --- |
| GitHub owner | Pre-Harriet account | `HarrietProject` |
| Canonical repository | Pre-Harriet canonical repository | `HarrietProject/Harriet` |
| Satellite repositories | Pre-Harriet prefix plus suffix | `HarrietProject/harriet-*` with the suffix retained |
| Local checkout | Pre-Harriet owner and repository directories | `C:\git\HarrietProject\Harriet` |
| Packages, executables, modules, crates, images, namespaces | Any project-controlled pre-Harriet prefix | `harriet` or `harriet-*` after compatibility review |
| Documentation and links | Pre-migration owner or repository references | Harriet canonical names and URLs |

No package, executable, module, crate, image, protocol identifier, or domain is claimed to exist merely because this convention is adopted. Existing external contracts require a separately documented deprecated alias or redirect before a breaking change.

## Migration order

1. Verify the clean branch, draft pull request, authentication, and expected commits.
2. Record controlled GitHub state, create and push the annotated rollback tag, and verify a bundle containing all refs.
3. Rename the GitHub account through account settings and verify authentication.
4. Select an API-confirmed verified non-legacy commit email without changing prior commits.
5. Recheck each target immediately before renaming the canonical and satellite repositories.
6. Update controlled metadata, current trees, cross-repository links, remotes, and local checkouts.
7. Validate zero current-tree and live-controlled-resource occurrences, then commit and push the existing feature branch.
8. Keep pull request 1 open, draft, and unmerged with current migration evidence.

## Redirects, compatibility, and rollback

Provider redirects are temporary compatibility aids, not canonical identifiers. Actions references, Pages project URLs, package coordinates, container names, release assets, badges, dispatch targets, and external integrations must be checked individually; no redirect is assumed safe for them.

Rollback evidence is the annotated `pre-harriet-identifier-migration-20260714` tag, a verified all-refs Git bundle stored outside the tracked tree, and a machine-readable pre-migration map under local Git metadata. Rollback may restore names and remotes if a material collision or operational failure occurs, but it must preserve this decision and disclose the reason. No rollback rewrites history.

## Verification and limitations

Acceptance requires zero case-insensitive occurrences of the pre-Harriet identifier or its separator variants in current tracked content, tracked paths, and live controlled metadata. It also requires preserved repository IDs, unchanged visibility and archive state, a verified commit identity, clean documentation checks, valid links, and an open draft pull request.

Immutable prior commits, tag contents, Git objects, historical pull-request events, provider redirect records, third-party forks, caches, and uncontrolled external references are outside that claim. Package inventory that cannot be queried with available permissions remains an explicit limitation rather than an assumed absence.

## Consequences and review trigger

Canonical names become simpler and current documentation no longer carries a permanent legacy exception. Redirect dependence, external consumers, and possible package collisions remain risks. Reconsider this decision if a material cultural concern, naming collision, verified compatibility failure, or legal instruction makes the convention unsafe or misleading.
