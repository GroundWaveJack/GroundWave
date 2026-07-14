# Base

**State:** architecture under design

A Base is an owner-controlled resource contributor. Depending on capability and policy, it may provide encrypted durable cache, store-and-forward relay, bundle custody, home relay, public emergency-information cache, map/software cache, synchronization, HF gateway, neighborhood federation, multipath coordination, or intermittent-region bridging.

Capacity is partitioned among system/recovery, owner-reserved, network operations, public/community cache, and elastic reserve. Automatic contribution always remains bounded, observable, revocable, and subordinate to owner policy.

Owner policy sets independent ceilings for storage, bandwidth, airtime, energy, compute, retention, replica count, custody, and permitted interfaces. Safety reserve, local administration, and recovery capacity cannot be consumed by network demand. Default-deny exposure, authenticated administration, audit visibility, per-peer admission control, and graceful shedding are design requirements; contribution does not grant access to owner plaintext.

Base qualification is profile-specific. Tests cover reserve enforcement under saturation, quota and eviction behavior, authenticated custody acknowledgment before deletion, restart and clock faults, storage corruption and recovery, network isolation, thermal and power-loss behavior, update rollback, malicious-input handling, and the failure of every advertised interface. HF, public cache, home-relay, and federation roles require separate profiles and are not implied by the Base label.
