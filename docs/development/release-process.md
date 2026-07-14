# Release process

No releases exist. A future release requires a versioned scope, changelog, license inventory, dependency record, reproducible build or document artifact, conformance results, threat-model delta, migration notes, supported profiles, known limitations, and signed provenance.

Use semantic versioning where APIs have compatibility meaning; specifications may use explicit maturity plus major/minor revisions. Release candidates cannot be labeled qualified without the qualification evidence. Rollback and key-compromise procedures precede production distribution.

## Release gates

1. Freeze the exact source revision, scope, maturity, and compatibility promise.
2. Resolve blocking security, licensing, identity-boundary, and documentation findings.
3. Run and retain required tests and conformance artifacts; list skips and waivers.
4. Review dependencies, generated artifacts, supported profiles, migration, rollback, and known limitations.
5. Produce provenance from the clean revision and verify it independently where practical.
6. Obtain the documented maintainer decision, publish the changelog, and retain artifacts.

An archive snapshot is not automatically a release. A release is not automatically tested at every conformance level or qualified for hardware use. No release service-level or maintenance-duration commitment exists until a release explicitly states one.
