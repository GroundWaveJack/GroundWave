# ADR 0001: Platform, not a single protocol

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes earlier scope:** Yes — the April 2026 hardware-kit-only definition.

**Related RFC:** None; originating maintainer directive.

## Decision

Harriet must operate across heterogeneous paths. Defining it as a Reticulum kit prevents principled integration elsewhere. Harriet therefore owns a connective intent, policy, provenance, adapter, and conformance layer. Protocol-specific behavior remains in profiles. Existing Reticulum experiments remain valid inputs.

## Consequences and limitations

The project must define profile-neutral semantics without creating a replacement for mature transport or routing systems. Adoption records direction only; no platform implementation exists.

## Review trigger

Reconsider if conformance work shows the connective semantics cannot be expressed across at least two materially different profiles without becoming a new mandatory transport.
