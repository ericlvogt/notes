#scalable-compute 
[[Open Source]]
[[Apache Software Foundation]]
Unified analytics engine for large scale data processing

Spark requires a pool of separate compute instances. It utilizes the map reduce technique and is the successor to [[Hadoop Map-Reduce]].

Seems like [[Ray]] may be a successor to this.

Alternative approach to parallel processing includes [[Dask]] and [[Polars]]

Has more advanced analytic capability than [[Apache Hadoop]] but does not have a [[Hadoop Distributed File System (HDFS)]] so spark may be installed on top of [[Apache Hadoop]] to leverage its distributed file system.

Spark copies its data to [[Random Access Memory (RAM)]] which makes it faster than [[Apache Hadoop]] which takes a backup of all data onto the local server. This makes Spark more preferable when processing real time data.
[[Python]]
[[Structured Query Language (SQL)]]
[[Scala]]
[[Java]]
[[R (Programming Language)]]