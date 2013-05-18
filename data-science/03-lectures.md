# Scalability basics
(past / now / soon)
Operationality: data doesn't fit in memory / use a cluster (scale up / scale out)
Algorithmically: avoid polynomial time algos / parallelize / one pass at analysis

Relational DBs are good at first type of algorithmic scalability (indexing, etc.)

Map transforms: parallelize (ex: read trimming)

# Parallel processing patterns
Continuing with mappable tasks (image conversion, simulation runs, word frequency in documents, etc.)
Adding reduce: word frequency across all documents

map = distributes multiple inputs to worker nodes for individual processing
reduce = combines multiple inputs into the output

# MapReduce abstractions
Map is called once per input objects
Reduce is called once per group of input

Thanks, Google!
Hadoop is free

Map-reduce input/output characteristics

# MapReduce pseudocode
Looking at MR example pseudocode for word frequencies across documents
Tweak performance within the map and reduce functions

# MapReduce: more examples
Look at categories of words in a document (e.g., long, short, medium words)
Illustration that documents are not atomic

Inverted index: all documents that contain a word

# MapReduce: relational joins
Multiple tables, prepend a table (or record type) field, then smush all the records into a single stream
Map to (foreign key, fields)
Reduce merges fields for same foreign key (with the parent table being identified by the type label)

Counting friends

# MapReduce: matrix multiplication
Map phase: for each element (i,j) of matrix A, emit ((i,k), A[i,j]) for k in 1..N (number of cols in B)
           for each element (j,k) of matrix B, emit ((i,k), B[j,k]) for i in 1..L (number of rows in A)
Reduce phase: emit key = (i,k), value = sum(A[i,j] * B[j,k]) 

One reducer per output matrix cell
Each reducer (i,k) gets all values from row i in A and from col k in B; the reduce function multiplies them out and sums them

# MapReduce implementation overview
Architectures:
* shared memory
* shared disk
* shared nothing <= map-reduce's sweet spot

Cluster computing: you will see failures
Distributed filesystems - Google DFS, Hadoop's HDFS
* files are partitioned into chunks, replicated across machines

Phases of MapReduce
* Split
* Record Reader => Map => Combine
* Copy
* Sort
* Reduce

Combine = optional function, same method signature as the reducer, applied locally (before sending data across the network)

# Parallel databases
Large-scale database processing - parallel DBs are a pain
MapReduce is a lightweight solution

Parallel processing for declarative querying
* distributed query - union of subqueries, run across many nodes; implemented as a view
* parallel query - operators implemented with parallel algorithms

Pig: relational algebra on top of Hadoop
Hive: SQL over Hadoop
Impala: SQL over HDFS
etc.
