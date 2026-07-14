# ADR 0001: Platform, not a single protocol

**Status:** adopted, 2026-07-14

Groundwave must operate across heterogeneous paths. Defining it as a Reticulum kit prevents principled integration elsewhere. Groundwave therefore owns a connective intent, policy, provenance, adapter, and conformance layer. Protocol-specific behavior remains in profiles. This broadens and supersedes the hardware-only definition without rejecting existing Reticulum experiments.
