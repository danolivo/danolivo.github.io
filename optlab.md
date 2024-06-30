---
layout: page
title: "Optimisation Lab"
permalink: /OptLab
---

On this page you can find list of our crazy projects:

# GROUP-BY Optimisation, part 2
Optimiser has freedom to choose order of grouping columns. Here we try to add one more strategy - put in the first position the column with greatest number of distict values.

https://github.com/postgrespro/postgres/tree/sort-columnsnum

# Assymetric JOIN
Thhis feature mostly oroiented to distributed execution. Works likewise partitionwise join feature. Allows to JOIN plain table and partitioned one.

https://github.com/postgrespro/postgres/tree/asymmetric-join

# Self-Join Elimination
Remove unnecessary join from the query tree if is proved that single scan return the same data.

https://github.com/postgrespro/postgres/tree/self-join-elimination

# Auto-generation of extended statistics
It is impractical to compute multivariate statistics automatically. Our conjecture here is that index structure reflects that a specific set of columns and extensions is most frequently used for extracting data, and it is critical to build optimal query plans when combinations of these columns are involved.

https://github.com/danolivo/pg_index_stats
