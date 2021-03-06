# From data models to databases
How do we store data? How is it organized? 
Three components to a data model:
1. Structures
2. Constraints
3. Operations
[ weird collapsing of schema and DB here - operations? ]

What's a database? 
* "A collection of information organized to afford efficient retrieval"
* "The data should be self-describing and their should be a schema"

What's a database good for?
1. Sharing - concurrent access
2. Data model enforcement - clean the data
3. Scale - too much data to fit into memory
4. Flexibility - new uses for the data

# Motivating relational databases
Organization on disk affects querying, access methods, etc.
Network database => hierarchical databases => relational databases -- increasing flexibility
RDBMS => organizing the database in such a way that novel queries and uses of data are possible
* everything is a table
* every row in a table has the same columns
* relationships are implicit (a-id => a.id)

# Relational algebra intro
Pre-RDBMS: data change => broken application
RDMBS => abstraction of the data

RDBMS exhibit an algebraic structure allowing manipulation independent of physical organization/storage
Algebraic optimization - simplification / reduction of equations; do the same in relational algebra (DBs)
- particularly important for determining the fastest/most efficient query

# Diff/union/select
Relational algebra operations: union, intersection, difference, selection, projection, join; (extended RA) duplicate elimination, grouping/aggregation, sorting
Sets vs. bags
* set members are unique
* bags need extended RA
* papers assume set semantics
* implementations assume bag semantics

Union: UNION vs UNION ALL (suppress dupes vs. not)
Difference: EXCEPT
Intersection = R1 - (R1 - R2) (or inner join)
Selection: return tuples which satisfy a condition

# Project/cross product/equi-join
Project: eliminates columns
Cross product: Cartesian product; becoming more common
Equi-join: join on equality condition

# Theta-join
Any condition - not usually expressed with the JOIN keyword in SQL
Ex: `SELECT DISTINCT h.name FROM hospitals h, schools s WHERE distance(h.location, s.location) < 5`

Outer join (left, right, full)

# Interpreting complicated SQL
Nested queries, meh
Treating CASE as a function

# User-defined functions
Yes, you can define your own functions. [too basic]
* Not in SQLite, sucker

# Physical optimization
A single logical expression can be realized by different physical algorithms

Ex: SELECT * FROM orders, items WHERE orders.order = items.order
Options:
1. Nested for loops (iterate over items, then orders, return matches)
2. hashtable (insert all items into hashtable, iterate over orders and look up matches in hashtable)

EXPLAIN => execution plan, duh
1 can be superior when one side is very small
differences can be *significant*

# Declarative languages
Relational algebra specifies order (join 1 before join 2, etc.); declarative languages just describe the desired output
SQL is *what*, not *how*

# Logical data independence
Views - abstraction over the lower-level logical structure of data
Views are named queries
SQL is algebraically closed
Materializing views - database-specific

Indexes, yay
