System Design Papers
==========

Collection of papers that I have personally found helpful for system design (updating).

## System design talks

Dissecting Dynamo: Highly available key value store at Silicon Valley Code Camp 2018
- https://www.youtube.com/watch?v=lB5gNAHUR_8

USENIX ATC '13 - TAO: Facebook’s Distributed Data Store for the Social Graph
- https://www.youtube.com/watch?v=sNIvHttFjdI

Scaling Memcache at Facebook
- https://www.youtube.com/watch?v=6phA3IAcEJ8&t=375s

Turning Caches into Distributed Systems with mcrouter - Data@Scale
- https://www.youtube.com/watch?v=e9lTgFO-ZXw&t=1135s

Large-Scale Low-Latency Storage for the Social Network - Data@Scale
- https://www.youtube.com/watch?v=5RfFhMwRAic&t=1344s

Dataswarm
- https://www.youtube.com/watch?v=M0VCbhfQ3HQ

Large-scale cluster management at Google with Borg
- https://www.youtube.com/watch?v=7MwxA4Fj2l4
- https://www.youtube.com/watch?v=0W49z8hVn0k

Scaling YouTube's Backend: The Vitess Trade-offs - @Scale 2014 - Data
- https://www.youtube.com/watch?v=5yDO-tmIoXY

GOTO 2016 • What is a CDN and why Developers should Care about using one
- https://www.youtube.com/watch?v=farO15_0NUQ&t=309s

Scaling Uber's Real-time Market Platform
- https://www.infoq.com/presentations/uber-market-platform/

The Paxos Algorithm
- https://www.youtube.com/watch?v=d7nAGI_NZPk

CONSOLIDATING STORAGE BACKENDS AT SCALE WITH TECTONIC FILESYSTEM
- https://www.facebook.com/watch/?v=520707222455400

## My personal notes / ideas on papers

Wormhole vs Scribe
- data loss: Scribe is tailored for high availability and may lose data in case of machine failures; Wormhole has minimal data loss. 
- order of updates: Wormhole maintains oder; Scribe may deliver updates out of order.
- latency: Wormhole has a lower latency than Scribe. 
- intermediate broker: Scribe uses broker; Wormhole does not, and Wormhole publishers are specialized for different data systems. 

Paxos: concensus algorithm
- Chubby: Google's lock service
- Zookeeper

Dataswarm: dependency graph description language
- fault tolerance
- selectivity
- remote execution

Kubernetes, Borg, Tupperware
- robust to failures
- multiple regions
- monitoring
- consistent environments
- updates

BigTable
- write append
- Sstable
- bloom filter

Kafka
- message queuing system with twists (could work as low-latency message queues, or log aggregator)
- high throughput, thanks to sequential I/O, and fewer data copies / system calls
- pull model: consumer can rewind back and re-consume data
- pulisher-subscriber patterns

Cassandra
- consistent hashing: move nodes on the ring to adjust load
- data model: column family
- replication policy: next N-1 nodes on the ring
- local persistence: commit logs, Sstable, bloom filter (similar to bigtable)

Dynamo
- consistent hashing: virtual nodes
- data model: key-value store
- replication policy: next N-1 nodes on the ring