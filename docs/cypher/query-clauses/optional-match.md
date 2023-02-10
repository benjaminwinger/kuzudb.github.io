---
layout: default
title: Optional match
parent: Query clauses
grand_parent: Cypher
nav_order: 2
---

# Database
We will use the database, whose schema and data import commands are given [here](example-database.md):

<img src="../../../img/running-example.png" width="800">

You can import this database by copy pasting the comands on that page. 

# Optional-match
`OPTIONAL MATCH` is another clause where you define a pattern to find in the database. The difference between `MATCH` is that 
if the system cannot match a pattern defined by OPTIONAL MATCH, it will set the values in the variables defined only in 
the OPTIONAL MATCH, to NULL. If you consider the patterns defined in a query that combines `MATCH` and `OPTIONAL MATCH`,
you can understand the semantics as follows: perform the join inside `MATCH` and store it as an intermediate table L; 
(ii) perform the join inside the `OPTIONAL MATCH` and store it as an intermediate table R. Then take the left
outer join of L and R (where L is on the left) on their common variables (i.e., `L ⟕ R` in relational algebra).

For example, the following query returns the followees of each user or NULL if a user doesn't follow anyone.

Query:
```
MATCH (u:User)
OPTIONAL MATCH (u)-[:Follows]->(u1:User)
RETURN u.name, u1.name;
```
Result:
```
---------------------
| u.name  | u1.name |
---------------------
| Adam    | Karissa |
---------------------
| Adam    | Zhang   |
---------------------
| Karissa | Zhang   |
---------------------
| Zhang   | Noura   |
---------------------
| Noura   |         |
---------------------
```
