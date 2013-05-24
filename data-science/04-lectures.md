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

# CouchDB
transactional within a document
lock-free concurrency (optimistic)
views - JS map-reduce functions
view collation

# BigTable/HBase
sparse, distributed, persistent, multidimensional sorted map
data is sorted lexicographically by row key
row key range broken into tablets (unit of distribution and load balancing)
column families - access control, memory & disk accounting
cells can be versioned
compression, bloom filters, locality groups, immutability

# Other 
HBase = BigTable, compatible with Hadoop
Megastore = entity groups, synchronous replication, full transactions within a partition
Spaner = flexible schemas and strong consistency (transactions)
* directories (contiguous keys with shared prefix)
* hierarchy from interleaving keys

# Responses to NoSQL
Various efforts underway to add missing features to NoSQL systems
NoSQL criticism

