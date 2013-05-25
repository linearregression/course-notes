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

# Pig
Layer on top of Hadoop, generates map-reduce jobs automatically
Easier to represent certain sorts of queries, but retain scaling benefits of MR jobs

Data model
* atom
* tuple (<...,...>)
* bag (collection of tuples; allows duplicates) ({<>,<>})
* map (keys mapped to any time - allows nesting) ([...:...'])

Operators
* . => project (e.g., f2#$0 => first element of each tuple in bag f2)
* # => value (e.g., f3#'apache' => value for key 'apache' in f3)

Commands
* LOAD - input is assumed to be a bag; specify parsing function with USING; specify schema wish AS
* FILTER - arbitrary boolean conditions, regex allowed
* GROUP - first field is named "group", second field is named after the original dataset
* DISTINCT
* FOREACH - manipulate each tuple; GENERATE to specify output; FLATTEN to unnest
* COGROUP - aggregate multiple datasets (A by f1, B BY f2; groups by same values in A.f1 and B.f2)
* JOIN - flattened union of rows from A and B where the join values are the same
  * multiple algorithms available to optimize various cases (small tables, skewed joins, presorted tables)
  * skewed datasets/stragglers (where one key has most of the data) are one of the biggest performance issues in MR



