# Multipath

Planners may use multiple viable paths when policy and replica budgets allow. Metrics can include latency, capacity, energy, trust, congestion, scheduled availability, administrative preference, and delivery history. Path diversity must be real; nominally different links sharing one failure domain should not be counted twice.

The project may borrow ECMP, MPTCP concepts, anycast-like rendezvous, and scheduled contacts at the appropriate layer. It will not mechanically merge routing protocols.
