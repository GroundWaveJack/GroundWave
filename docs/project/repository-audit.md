# HarrietProject repository audit

**Audit date:** 2026-07-14

**Evidence:** GitHub repository metadata, default-branch trees, README and governance content, and commit metadata.

**Scope:** All eight public repositories owned by `HarrietProject` at the audit date.

## Executive finding

The account contains one canonical planning repository, one substantive hardware-documentation repository, and six single-README placeholders. The placeholders were created around a sensor-network interpretation that conflicts with both the older emergency-radio framing and the newly adopted adaptive-communications direction. Consolidation is recommended, but deletion and archival are explicitly deferred.

At the initial audit, all repositories used only `main` and no unmerged branches were visible. Published commits inspected used the author name Jack; immutable history retains its original metadata. No prohibited identity strings, secrets, or personal filesystem paths were found in tracked content or published commit metadata.

## Inventory

| Repository | Current contents and stated purpose | Assessment | Recommendation |
| --- | --- | --- | --- |
| `Harriet` | Five planning documents; describes a Reticulum-centered emergency hardware kit | Canonical repository, but stale scope, broken document references, no license file, and unsupported governance claims | Retain as platform, architecture, governance, and cross-repository documentation home |
| `harriet-fieldnode` | Hardware spec, BOM, build/deployment/firmware guides, contribution guide, and license | Only substantive satellite repository; pre-prototype claims sometimes sound qualified | Retain as an experimental ambient/field relay reference; reconcile terminology and evidence later |
| `harriet-analog` | One README describing analog sensor acquisition | Empty placeholder; purpose is outside the communications north star | Consolidation candidate; do not build until a communications use case is approved |
| `harriet-anchor` | One README describing a sensor-data aggregation hub | Empty placeholder; name overlaps the future Base concept but description is contradictory | Supersede conceptually with Base architecture; archival decision deferred |
| `harriet-app` | One README describing sensor dashboards and alerts | Empty placeholder; user interface scope may later be useful but stated purpose is stale | Reserve pending an edge-application RFC; do not implement activity theater |
| `harriet-brick` | One README describing mandatory cloud ingestion and storage | Empty placeholder; directly contradicts the no-required-central-service doctrine and older handheld meaning | Highest-priority consolidation or archival candidate; decision deferred |
| `harriet-docs` | One README claiming to be central documentation | Empty placeholder duplicating this repository's canonical role | Consolidation candidate; keep canonical docs here unless scale justifies a split |
| `harriet-kits` | One README describing FieldNode kit designs and provisioning | Empty placeholder duplicating `harriet-fieldnode` and prospective hardware repositories | Consolidation candidate; commerce/procurement concerns must remain separate from requirements |

## Contradictions and stale decisions

- The main repository says the former working name is only a hardware lane built on Reticulum. This is superseded by the platform doctrine recorded in ADRs 0001–0005.
- Placeholder repositories describe an analog sensor network, cloud-side Brick, and dashboards. These are not supported by the main repository history and are superseded as project definitions.
- `PROJECT_STATE.md` says the repository was not created even though it is stored in that repository.
- Governance says fiscal sponsorship exists, while the state document says sponsorship is merely being explored. No evidence of sponsorship or a legal entity was found; both remain proposals.
- The main README links to absent `CONTRIBUTING.md` and claims license terms without carrying license texts or a licensing map.
- Earlier hardware tiers and exact component selections are design history, not qualified requirements.
- Earlier channel-plan, legal-operation, weatherproofing, cost, and autonomous-runtime assertions lack test evidence and must not be treated as qualified.

## Licensing and governance consistency

The intended policy names CERN-OHL-S-2.0 for hardware, AGPL-3.0 for software, and CC-BY-SA-4.0 for documentation. Only `harriet-fieldnode` contains a license file, and its combined prose/hardware language needs specialist review before reuse. This program does not change licenses. `LICENSES.md` records intent and the gap without making legal claims.

Founder stewardship, pseudonymous contribution, copyleft intent, fork rights, documented decisions, resistance to sponsor control, and eventual distributed maintainership are retained. Fiscal sponsorship, a nonprofit foundation, board composition, and legal-persona assertions are marked proposed until supported.

## Documentation gaps

Before this branch there was no threat model, security reporting process, contribution guide, code of conduct file, support policy, release process, test strategy, architecture decomposition, ADR system, RFC system, glossary, maturity vocabulary, documentation CI, or repository map. Existing cross-links referenced missing files.

## Technical-debt register

| ID | Debt | Risk | Disposition |
| --- | --- | --- | --- |
| TD-001 | Mission differs across repository READMEs | Contributors build incompatible systems | Canonicalize here; open follow-up PRs per satellite repository |
| TD-002 | No implemented connective-layer software | Architecture can outrun evidence | Keep interfaces under design; require conformance fixtures before implementation claims |
| TD-003 | FieldNode requirements mix targets, SKUs, and qualification | Unsafe procurement and false confidence | Split HRS, qualified BOM, and procurement manifest in satellite follow-up |
| TD-004 | Security model absent | Translation, caches, and metadata risks are underspecified | Add threat model and security-boundary documents |
| TD-005 | License declarations lack canonical files | Ambiguous reuse terms | Maintainer/legal review required; no license change in this PR |
| TD-006 | Unsupported regulatory and RF claims | Operational and safety risk | Mark jurisdiction-specific and require evidence/review |
| TD-007 | No tests, releases, or CI | Claims cannot be reproduced | Add docs CI now; specify later conformance and hardware-in-loop gates |
| TD-008 | No community workflow | Decisions remain implicit | Add issues, RFCs, ADRs, security, conduct, and contribution paths |

## Canonical repository map

- `Harriet`: canonical vision, doctrine, architecture, governance, security model, standards posture, and cross-project development rules.
- `harriet-fieldnode`: experimental low-power relay hardware; candidate for later alignment with the ambient-node embodiment.
- `harriet-app`: reserve for a future phone/desktop edge client only after an approved scope RFC.
- Other existing placeholders: hold without active implementation; decide consolidation or archival through a public RFC after this reframe.

Recommended future repositories should be created only when code, hardware source, independent release cadence, or access controls make separation necessary. Repository count is not a progress metric.

## Follow-up audit limits

This was a repository-content audit, not a security penetration test, legal opinion, hardware qualification, or review of untracked maintainer systems. GitHub issues, discussions, packages, releases, and branch protections should be reviewed when those features become active.
