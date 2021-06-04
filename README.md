System Design Papers
==========

Collection of papers that I have personally found helpful for system design (updating).

## System design talks

## My personal notes / ideas on papers

Wormhole vs Scribe
- data loss: Scribe is tailored for high availability and may lose data in case of machine failures; Wormhole has minimal data loss. 
- order of updates: Wormhole maintains oder; Scribe may deliver updates out of order.
- latency: Wormhole has a lower latency than Scribe. 
- intermediate broker: Scribe uses broker; Wormhole does not, and Wormhole publishers are specialized for different data systems. 
