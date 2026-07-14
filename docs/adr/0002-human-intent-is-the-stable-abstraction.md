# ADR 0002: Human intent is the stable abstraction

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes earlier scope:** Yes — transport and hardware are no longer the user-level abstraction.

**Related RFC:** None; originating maintainer directive.

## Decision

Links and media representations change more quickly than a person's purpose. Interfaces express recipient, purpose, urgency, acceptable degradation, and acknowledgment requirements. Implementations must not infer permission for lossy transformation merely from path scarcity.

## Consequences and limitations

The platform can preserve declared constraints, provenance, and refusal behavior; it cannot prove that arbitrary human meaning survived a transformation.

## Review trigger

Reconsider if user research or conformance fixtures show that the intent contract cannot be made understandable, bounded, and interoperable without exposing unsafe ambiguity.
