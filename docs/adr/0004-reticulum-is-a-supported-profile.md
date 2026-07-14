# ADR 0004: Reticulum is the first profile target

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes earlier scope:** Yes — Reticulum no longer defines the entire platform.

**Related RFC:** None; originating maintainer directive.

## Decision

Reticulum is the adopted target for the first integration profile. Reticulum, LXMF, and RNode remain externally governed dependencies and cannot define every platform semantic. The profile remains architecture under design, must declare unsupported semantics, and has no current conformance claim.

## Consequences and limitations

Existing experiments retain a migration path, while Groundwave must avoid silently approximating delivery, identity, or acknowledgment requirements that the profile cannot express.

## Review trigger

Reconsider target priority if maintained upstream behavior, security posture, licensing compatibility, or conformance evidence makes a responsible profile infeasible.
