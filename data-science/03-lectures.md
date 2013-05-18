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

