# RFC 0001: Adopt Harriet as the public project name

**Status:** accepted

**Date:** 2026-07-14

**Authors:** Jack

**Discussion deadline:** Not applicable to this founder-steward disposition; later identifier migrations require separate review.

**Decision owner:** Jack

**Target disposition:** accept

## Summary and user need

Adopt **Harriet** as the public name of the project and adaptive communications platform, in honor of Harriet Tubman. Groundwave becomes the historical name and remains in legacy repository identifiers during a staged migration.

The project needs a name that ordinary people can understand and remember, that expresses finding another way through when official or expected paths are closed, and that carries a clear public-interest obligation rather than sounding like an invented technology brand.

The tribute is not a claim that software is equivalent to Harriet Tubman's courage, work, or the liberation of enslaved people. It is a commitment to human freedom, ordinary-person usability, decentralized trust, adaptive routes, honest limits, and infrastructure that cannot be made dependent on one corporation or operator.

## Existing standards and evidence

The [National Park Service](https://www.nps.gov/hatu/index.htm) describes Harriet Tubman as the Underground Railroad's best-known conductor and records that she repeatedly risked her life guiding enslaved people to freedom. The wider Underground Railroad was a network of freedom seekers and people who assisted them rather than a single centrally operated route.

A preliminary name search did not identify a same-category adaptive communications platform called Harriet. It did identify unrelated software using the bare name, including the [`harriet` Rust crate](https://github.com/field33/harriet), a Turtle/RDF parser, and an older [Perl test-daemon manager](https://github.com/tokuhirom/Harriet). This is not legal, trademark, package, domain, or availability clearance.

## References

- [Why Harriet](../../WHY_HARRIET.md)
- [National Park Service: Harriet Tubman and the Underground Railroad](https://www.nps.gov/hatu/index.htm)

## Proposed ownership boundary

This decision governs the project's use of the public name, explanation, stewardship commitments, and documentation migration. It does not claim ownership of Harriet Tubman's legacy, historical terminology, unrelated software called Harriet, or any upstream project.

No descendant, museum, historical organization, government agency, or National Park Service unit is represented as endorsing, authorizing, or affiliating with the project.

## Alternatives and upstream path

- **Groundwave:** retained as historical context and legacy repository naming, but it overemphasizes one physical transport class.
- **Chaski:** carries an excellent relay-messenger meaning but requires explanation for much of the intended audience.
- **Shannon:** honors foundational communications science but is widely used and does not express the human mission as directly.
- **Generic pathfinding names:** understandable but crowded and easy to mistake for navigation products.

Harriet was selected because the name already carries a broadly understandable human story: when a system denies a path, people can create another way through. No upstream software project is being renamed or forked by this decision.

## Security, privacy, safety, and resource effects

The name does not alter the threat model or authorize operation outside existing policy, safety, legal, privacy, resource, or spectrum constraints. It must not be used to imply guaranteed escape, anonymity, delivery, secrecy, censorship resistance, or safety.

The project must not use Tubman's likeness as a mascot, trivialize slavery, gamify the Underground Railroad, or convert historical roles and locations into cute product vocabulary. Public materials must keep the attribution visible and must accept good-faith correction from historians and affected communities.

Ordinary-person usability becomes an explicit architectural requirement. A future user should be able to install or download Harriet, identify who must be reached, express simple privacy, urgency, acceptable-degradation, and acknowledgment choices, and let technical profiles operate underneath. This is a design requirement, not a present implementation claim.

## Compatibility, migration, and rollback

1. **Public-document stage:** current normative documents use Harriet for the project and platform. Groundwave remains in historical records and legacy identifiers.
2. **Identifier review stage:** inventory repository, organization, package, executable, module, crate, domain, protocol, compatibility, signing, and update identifiers. Perform cultural, availability, legal, accessibility, and migration review.
3. **Separately approved migrations:** rename only identifiers covered by an explicit decision, with redirects, compatibility periods, rollback steps, and preserved history.

This RFC does not rename `GroundWaveJack`, `GroundWave`, any `groundwave-*` repository, local paths, branches, remotes, packages, executables, domains, modules, crates, or protocol identifiers.

A rollback may restore a different public name if material cultural harm, collision, legal advice, or sustained confusion makes Harriet unsuitable. Rollback must preserve this RFC, ADR 0010, and the reason for the change. It must not rewrite archives or claim the prior decision never occurred.

## Conformance and acceptance criteria

- Current entry points name Harriet and link the explanation.
- Historical files remain byte-for-byte unchanged.
- Remaining uses of Groundwave are historical references, repository identifiers, migration explanations, or superseded decision records.
- Harriet is not presented as implemented, released, certified, universally lawful, or guaranteed to deliver.
- No package, executable, domain, repository, organization, crate, module, or protocol identifier is represented as selected or available.
- Documentation, links, spelling, whitespace, YAML, and identity checks pass or any unavailable check is reported honestly.

## Rollout evidence and documentation impact

The initial rollout is confined to the existing draft documentation pull request. It adds [WHY_HARRIET.md](../../WHY_HARRIET.md), [ADR 0010](../adr/0010-adopt-harriet-as-public-project-name.md), this RFC, decision-log entries, and consistent current terminology. Repository and account names remain unchanged.

## Open questions

- Which repository, organization, domain, package, executable, crate, module, and protocol identifiers are usable and defensible?
- What cultural or historical review should precede wider public launch and visual identity work?
- How should legacy Groundwave links and compatibility identifiers be preserved if repositories are later renamed?
- Which acceptance tests demonstrate that ordinary people can participate without command-line or networking expertise?

## Disposition

**Accepted by Jack on 2026-07-14 under the documented founder-steward process.** This records an explicit maintainer decision, not community consensus, trademark clearance, endorsement, or implementation evidence.

ADR 0009 is superseded by [ADR 0010](../adr/0010-adopt-harriet-as-public-project-name.md). Follow-up work is limited to documentation adoption and separately governed identifier, cultural-stewardship, and migration reviews.
