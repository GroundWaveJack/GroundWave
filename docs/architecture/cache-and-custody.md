# Cache and custody

Bases may offer encrypted durable cache and store-and-forward service within owner limits. Storage is partitioned into system/recovery, owner-reserved, network operations, public/community cache, and elastic reserve. Network content never silently consumes owner-reserved capacity.

Upstream deletion requires authenticated custody acknowledgment and policy satisfaction. Authentication identifies the claimant; it does not prove honest durable storage. Where policy requires resilience, satisfaction includes defined failure-domain diversity, replica evidence, and acknowledgment timeouts. A custodian is not a final-delivery witness, and single-custodian acceptance retains an explicit acknowledge-and-drop risk.

Before emitting custody acceptance, a node must durably store and verify the protected object and required metadata, reserve bounded capacity, and record expiration, replica, confidentiality, and deletion policy. Restart recovery must not invent acceptance or silently lose an accepted obligation. Required states include offered, refused, retained, accepted, transferred, delivered, expired, and released, with authenticated evidence for transitions that authorize upstream deletion.

A next-hop transfer is not sufficient for deletion unless policy explicitly permits it. Profiles must define disk-exhaustion, corruption, clock-uncertainty, revocation, restart, and unavailable-successor behavior. Custody, endpoint delivery, rendering, and human acknowledgment remain separate events.
