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

