# NoSQL
Feature matrix for data persistence
[ no graph DBs? lame ]

Primary motivation for NoSQL: scaling
[ meh ]

# Eventual consistency
Need to support high availability and updates
Two-phase commit (prepare => ready => commit)
Alternatives to 2PC: 
* MVCC
* Paxos

Eventual consistency: write conflicts will eventually propagate through the system

CAP theorem:
* consistency
* availability
* partitioning

RDBMS downplay partitioning, many NoSQL systems downplay consistency

# Memcached
ACID
* Atomicity
* Consistency
* Isolation
* Durability

Major systems
* Memcached
* Dynamo
* BigTable

Memcached: important concept - consistent hashing
* limits movement of data when adding new servers

# Dynamo
ultra high availability and performance
writes do not fail; last write wins
reconciliation happens at read time
configurable consistency
R = nodes for a good read
W = nodes for a good write
N = replication factor
R+W > N => consistency
R+W < N => lower latency
