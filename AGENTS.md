# Harriet repository operating contract

This repository is canonical for Harriet direction, platform architecture, governance, and cross-repository standards.

## Identity boundary

- GitHub operations use `HarrietProject`.
- Repository-local commits are authored exactly as `Jack <278731599+HarrietProject@users.noreply.github.com>`.
- Never change global Git identity or disclose another identity, private contact data, filesystem paths, machine names, credentials, or infrastructure.
- Classify sandbox network failures as network failures; re-verify identity before publishing.
- Never push to `main`, rewrite history, force-push, or add collaborators without an explicit decision.

## Truth and maturity

Use these states: **Vision**, **Adopted doctrine**, **Architecture under design**, **Reference design**, **Prototype**, **Tested**, **Qualified**, and **Released**. Never present city-scale federation, automated translation, HF custody, router packages, satellite/optical links, or other roadmap concepts as implemented.

Hardware qualification states—Reference, Qualified, Compatible, Community-tested, Experimental, Deprecated, and Unsupported—describe evidence for a configuration, not project maturity.

## Delegation for broad work

- Treat cross-disciplinary or repository-wide programs as multi-agent work by default.
- Begin with read-only specialist reconnaissance and reconcile overlaps and disagreements before writing.
- Assign non-overlapping file ownership during writing; only the coordinating agent performs Git operations.
- The coordinator reviews every draft and retains root-document/editorial ownership.
- Finish with independent identity, security, unsupported-claim, link, and consistency reviews.

## Change discipline

- Preserve history and record superseded decisions in the decision log or an ADR.
- Prefer open standards and upstream contributions; justify new protocols or forks through an RFC.
- Keep vision, doctrine, architecture, current implementation, and roadmap separate.
- Use `Harriet` as the adopted public project and platform name, `HarrietProject/Harriet` as the canonical repository, and `harriet-*` for satellite repositories. Refer to earlier naming only as the former working name or pre-Harriet identifier.
- Do not change licenses, core governance protections, repository names, or hardware requirements without required evidence and review.
- Hardware claims require datasheets or measurements. Commercial SKUs belong in a qualified BOM or procurement manifest, not permanent requirements.
- Ordinary relays handle opaque protected payloads. Trusted translation is explicit, bounded, and auditable.

## Documentation

- Use plain language, relative links, source-controlled Mermaid where useful, and descriptive headings.
- Define acronyms. Avoid literal resilience guarantees, militarized framing, and future tense that sounds implemented.
- Keep lifetime, hop budget, replica budget, priority, deadline, custody, acknowledgment, payload class, minimum representation, preferred relay, and confidentiality independent.
- Run documentation checks and identity scanning before committing.
- Pseudonymous contributions are welcome; do not demand unnecessary identity disclosure.

## Stop conditions

Stop for maintainer direction before future repository renames or archival, changing the adopted public name, changing licenses or core governance protections, deleting or rewriting history, making legal claims, or materially changing hardware requirements without evidence. RFC 0003 and ADR 0011 authorize only the completed Harriet identifier migration.
