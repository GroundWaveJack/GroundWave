# Multipath

**State:** Architecture under design; not implemented.

Planners may use multiple viable paths when policy and replica budgets allow. Metrics can include latency, capacity, energy, trust, congestion, scheduled availability, administrative preference, and delivery history. Path diversity must be real; nominally different links sharing one failure domain should not be counted twice.

The project may borrow ECMP, MPTCP concepts, anycast-like rendezvous, and scheduled contacts at the appropriate layer. It will not mechanically merge routing protocols.

Each carriage profile owns route discovery, loop prevention, metrics, and congestion behavior. The delivery overlay consumes only exposed capabilities and selects bounded attempts and replicas; it does not inject one protocol's routes into another. Adapters must declare metric meaning, freshness, uncertainty, and known shared failure domains.
