# Overview
Cypher is a high-level query language for the property graph datamodel.
Cypher is very much like SQL. Some of its main differences are: 
 - Instead of SQL's SELECT/FROM/WHERE, Cypher has MATCH (equivalent to FROM) WHERE, 
   and RETURN (equivalent to SELECT) as its main query clauses.
 - Instead of SQL's INSERT/UPDATE, Cypher has CREATE and SET data manipulation clauses. 
 - Joins between the records of different (node/rel) tables are specified using a graph-syntax.
 - There are special syntax, such as the Kleene star, or min...max, to describe variable-length
   and recursive joins.
There are other differneces between SQL and Cypher. Yet, similar to other high-level database
query languages, it is very much like SQL and most of its semantics can be understood
as mappings to relational algebra operations of selections, joins, projections, or 
group-by and aggregations.

Kùzu's query langugage is based on the openCypher variant of the Cypher query language. 
In this part of the documentation, we cover those clauses that are implemented in Kùzu. 
