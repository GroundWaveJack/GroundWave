# Ambient node

**State:** proposed reference class

An ambient node is a cheap, plug-anywhere relay or cache with no assumption of trusted location or continuous connectivity. It advertises constrained capabilities, accepts bounded work, and protects owner power, storage, and network budgets.

The existing FieldNode documentation may inform this class after measurements and scope reconciliation. Unattended operation, weather resistance, solar autonomy, and legal RF behavior require testing and cannot be inferred from parts lists.

## Profiles and threats

Power profiles must distinguish mains/USB powered, battery buffered, and energy-harvesting operation. Each declares startup surge, steady and peak consumption, reserve floor, brownout behavior, duty cycle, load-shedding order, and measured environmental assumptions. “Solar” is not an autonomy claim without site, season, orientation, storage, load, and test duration.

Ambient nodes are assumed physically accessible to untrusted people and networks. Threats include theft, replacement, probing, hostile USB power, malicious peripherals, storage extraction, radio abuse, traffic analysis, update compromise, and resource exhaustion. Profiles therefore minimize retained secrets and plaintext, authenticate updates, rate-limit work, bound cache and airtime, fail safely on corrupt state, and make reset and decommissioning possible. Tamper resistance is not currently claimed.

Qualification is separate for indoor, sheltered outdoor, and exposed environments. Applicable gates include long-duration power interruption, brownout cycling, thermal limits, ingress, electrostatic discharge, recovery, cache eviction, hostile-input, regional RF, and owner-limit tests.
