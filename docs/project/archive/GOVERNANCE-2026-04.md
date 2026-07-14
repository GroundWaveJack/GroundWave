# GOVERNANCE.md

This document describes how decisions are made in the pre-Harriet project, how contributors become maintainers, and how the project is structured to resist capture, censorship, and single-point-of-failure collapse.

## 1. Current Phase

The pre-Harriet project is currently in **Founder Steward** phase. A single pseudonymous steward is responsible for initial architecture, repository structure, and early decisions. This phase is explicitly temporary. The project is designed to transition to distributed governance as contributors join and demonstrate sustained engagement.

## 2. How Decisions Are Made

Decisions are categorized:

- **Architectural decisions** — These affect the system spec, threat model, tier definitions, core principles. During Founder Steward phase, these are made by the steward. Major architectural changes are discussed publicly in an issue or RFC before a decision is made.
- **Implementation decisions** — These affect how a specific repository, subproject, or component is built. During Founder Steward phase, these are made by the steward. Once subproject maintainers exist, these will devolve to them.
- **Community decisions** — Code of conduct enforcement, contributor disputes, governance changes. During Founder Steward phase, the steward decides. As the project matures, these will be handled by a governance committee.

Every significant decision is documented. The `PROJECT_STATE.md` Decision Log records architectural decisions. Implementation decisions are recorded in repository-specific decision logs.

## 3. How Maintainers Are Added

A maintainer is a person who has demonstrated sustained, high-quality contribution to a specific area of the project.

The path:

1. Contribute to a subproject over time. Submit PRs, file issues, answer questions.
2. Be proposed as a maintainer by an existing maintainer or by self-nomination after sustained contribution.
3. Be confirmed by the steward (in Founder Steward phase) or by existing maintainers (in later phases).

Maintainers have commit access to their subproject and can make implementation decisions in their domain.

## 4. How The Project Resists Capture

This section exists because the project's threat model includes state-level and corporate adversaries who may attempt to compromise, coerce, or capture the project.

The project is structurally resistant to capture by design:

- **Copyleft licenses.** CERN OHL v2-S, AGPL v3, and CC BY-SA 4.0 ensure that any fork remains open. A hostile entity cannot take the pre-Harriet project private.
- **Distributed contributors.** As the maintainer base grows, no single person's compromise affects the project's continuity. Any maintainer who becomes unresponsive, hostile, or coerced can have commit access revoked.
- **Documented architecture.** The `PROJECT_STATE.md`, system specification, and decision log are designed so that any reasonably skilled contributor could continue the project without the steward.
- **No single private signing key.** As the project matures, release signing will be distributed across multiple maintainers. Compromise of any single key does not compromise releases.
- **Fork rights explicit.** If the current maintainers go hostile or unresponsive, any community member may fork the project. This right is guaranteed by license and documented here. A legitimate fork is one that carries forward the principles described in `PROJECT_STATE.md`.

## 5. The Legal Entity

The pre-Harriet project operates under fiscal sponsorship during Founder Steward phase. This provides legal shelter for the project without requiring the steward to form their own entity immediately.

Long-term, the project will transition to an independent nonprofit foundation with a three-member board. At least two board members must be active contributors. No board member may hold majority control. Board replacement requires documented process.

Corporate contributions and sponsorships are accepted. Corporate control is not. No corporate sponsor may direct project architecture, require exclusivity, or gate features.

## 6. The Pseudonym

The current steward operates under a pseudonym. This is a deliberate decision, not an accident. The pseudonym is legally a persona of a real person who has fiduciary responsibility for the project, but the real identity is not part of the public project.

Contributors may also operate under pseudonyms. This is explicitly supported. Commit signing with a pseudonymous GPG key is acceptable. The project will never require identification of contributors beyond what is necessary for code contribution.

## 7. Code of Conduct

The pre-Harriet project uses the Contributor Covenant version 2.1. See `CODE_OF_CONDUCT.md`.

Enforcement: During Founder Steward phase, the steward enforces the code of conduct. Enforcement actions are documented. Appeals are heard by the steward and, when the community is large enough to support one, by a rotating community moderation group.

## 8. Amendments

This document may be amended by the steward during Founder Steward phase. Amendments are proposed publicly in an issue with at least a 7-day review period. Amendments after Founder Steward phase require maintainer consensus or governance committee vote as structure evolves.

Changes to this document's core protections — the copyleft licensing, the fork rights, the rejection of corporate control — require a higher bar: public RFC, 30-day minimum review, and broad maintainer consent. These protections are the foundation of the project's resistance to capture and are not casual amendments.
