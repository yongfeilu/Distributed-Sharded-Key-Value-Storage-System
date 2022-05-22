# Distributed-Sharded-Key-Value-Storage-System
__The MIT 6.824 course project: a distributed key/value storage system with Golang that shards data over a set of Raft-based replica server groups and achieved high throughput, fault tolerance, consistency and load balance among them.__

* 1. Implemented Raft Consensus Algorithm, which supports the shard controller and key/value servers running on its top, and enables fault tolerance, consistency, and high performance. Major features include leader election, log replication and compaction, state persistence, snapshot and crash recovery.
* 2. Built a shard controller to manage the configuration of shards and server groups efficiently. Implemented methods to support load balancing among server groups, and increasing system capacity by linear magnitude.
* 3. Built key/value servers that can process concurrent client requests during reconfiguration via Raft to enforce linearizability, and efficient design to reduce latency by 320%. Used Goroutines to achieve garbage collection of server state, saving 200% storage space and speeding up server reboot after crashes by over 3x.
* 4. Applied Goroutiones to execute client commands concurrently and parallelly, used sync.Mutex to avoid race conditions, used Go Channel and RPC to enable communication among goroutines, clients and servers.
