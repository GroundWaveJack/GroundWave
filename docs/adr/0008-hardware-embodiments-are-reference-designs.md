# ADR 0008: Hardware embodiments are reference designs

**Date:** 2026-07-14

**Decision owner:** Jack

**Status:** adopted

**Supersedes earlier scope:** Yes — fixed hardware tiers and commercial selections no longer define the platform.

**Related RFC:** None; originating maintainer directive.

## Decision

The platform is defined by interfaces and conformance, not a commercial bill of materials. Zack, Bases, ambient nodes, and expansion modules are reference embodiments. Requirements, qualified BOMs, and procurement manifests remain separate.

## Consequences and limitations

Compatible parts and community designs can evolve, but no embodiment or substitution is qualified without configuration-specific evidence.

## Review trigger

Reconsider an embodiment boundary when measured integration or qualification evidence shows that the shared interface cannot support safe, replaceable implementations.
