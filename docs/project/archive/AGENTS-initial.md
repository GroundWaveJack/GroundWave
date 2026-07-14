# Groundwave repository operating contract

This repository is the canonical home for Groundwave project direction, platform architecture, governance, and cross-repository standards.

## Identity boundary

- GitHub operations must use the `GroundWaveJack` account.
- Repository-local commits must be authored exactly as `Jack <groundwavejack@users.noreply.github.com>`.
- Do not change global Git identity or disclose an operator's legal identity, email, filesystem paths, machine names, credentials, or infrastructure.
- Treat sandbox network failures as network failures. Verify identity again before publishing.
- Never push directly to `main`, rewrite history, force-push, or add collaborators without an explicit governance decision.

## Truth and maturity

Every material claim must carry one of these states when context does not make it obvious:

- **Vision**: desired long-term outcome.
- **Adopted doctrine**: a governing design constraint.
- **Architecture under design**: specified direction without a conforming implementation.
- **Reference design**: a documented embodiment intended for evaluation.
- **Prototype**: assembled or executable, but not fully validated.
- **Tested**: evaluated against documented tests with results.
- **Qualified**: meets published acceptance criteria for a defined profile.
- **Released**: versioned and supported under the release policy.

Never present proposed city-scale federation, automated media adaptation, HF custody, router packages, satellite links, or optical links as implemented.

## Change discipline

- Preserve history and document superseded decisions in the decision log or an ADR.
- Prefer open standards and upstream contributions; justify new protocols or forks through an RFC.
- Keep vision, doctrine, architecture, current implementation, and roadmap separate.
- Use `Groundwave` as the provisional legacy working name. Do not select a replacement in routine work.
- Do not change licenses, core governance protections, repository names, or hardware requirements without the required evidence and review.
- Hardware claims require datasheets or measurements. Commercial SKUs belong in a qualified BOM or procurement manifest, not permanent requirements.
- Ordinary relays should handle opaque encrypted payloads. Trusted translation must be explicit, bounded, and auditable.

## Documentation

- Use plain language, relative links, source-controlled Mermaid diagrams, and descriptive headings.
- Define acronyms on first use. Avoid literal resilience guarantees or militarized and survivalist framing.
- Distinguish lifetime, hop budget, replica budget, priority, deadline, custody, acknowledgment, payload class, minimum representation, preferred relay, and confidentiality.
- Run documentation checks and the identity-leak scan before committing.
- Pseudonymous contributions are welcome; never require identity disclosure beyond platform necessities.

## Stop conditions

Stop for maintainer direction before renaming or archiving repositories, choosing a final name, changing licenses or core governance protections, deleting history, making legal claims, or materially changing hardware requirements without evidence.
