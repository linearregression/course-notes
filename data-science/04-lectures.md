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

