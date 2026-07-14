# ADR 0005: The core does not silently translate

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes earlier scope:** No explicit prior translation decision; this constrains the broadened platform scope.

**Related RFC:** None; originating maintainer directive.

## Decision

The ordinary-relay role does not require plaintext or content authority. A gateway may translate only with explicit policy and trust, and must produce a receipt containing original and derived media types and digests, method, known loss, uncertainty, and retention state.

## Consequences and limitations

Some paths are unusable when translation is forbidden. Receipts establish provenance and declared loss, not semantic equivalence or translator honesty.

## Review trigger

Reconsider receipt fields or authorization boundaries when adversarial tests reveal an undeclared downgrade, confused-deputy path, or unverifiable provenance transition.
