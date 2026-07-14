# Testing strategy

**State:** Process under design; no platform test suite exists.

Testing proceeds from deterministic schemas and state machines to adapters, adverse networks, hardware benches, and staged deployments. Required classes include unit/property tests, canonical encoding, compatibility fixtures, malformed input, privacy and quota cases, fault injection, simulation, interoperability, hardware-in-loop, and field evidence.

Tests publish versions, seeds, topology, environment, expected result, actual result, and artifacts. A passing happy path cannot establish security, scale, or qualification.

## Documentation checks

From the repository root, run the same commands as CI:

```powershell
npx --yes markdownlint-cli2
typos --config .typos.toml
lychee --config .lychee.toml "**/*.md"
git diff --check main...HEAD
```

Network-backed package resolution may be unavailable in a sandbox. Record any check that could not run; do not report it as passing. Before commit, also run the identity scan required by `AGENTS.md`.
