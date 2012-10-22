# Two things Redis is not (and likely never will be)

---

Pieter Noorhuis

+	easy to get started with, but may cause user's to forget the implications of their choice
	+	people should be well educated when they make that choice
+	not a good fit for all workloads
	+	Redis is not great for big data - bound by memory
	+	trade availability and sacrifice memory to get it's features

## Redis is not an available system

+	state divergence w/ multiple writes to dfiferent nodes
	+	list [1,2,3]
	+	NODE 1 - RPUSH(5) = [1,2,3,5]
	+	NODE 2- RPUSH(7) = [1,2,3,7]
+	Only a single node can take writes for a single key
	+	partition writes for keys across nodes

## Redis can be *highly available*

+	master fails - slave can be promoted
	+	slaves have to detect master failure (consensus)
+	data loss is possible via replication lag
	+	master writes buffer to slaves, can die mid writes
	+	some slaves have writes, some don't
	+	consensus among slaves can pick whoever has the *latest* version - doesn't currently do this
+	time between master failure and slave promotion = unaivalable time

Ways to overcome these points:

+	Redis Sentinel
+	Reids Failover - ryanlecompte/redis_failover (Zookeeper)

## Redis does not grow beyond RAM

+	when you run out...
	+	swap to disk
		+	user space (redis) can't control this (kernel), can block and slow everything down (single threaded)
	+	can swap out values
		+	divergence between disk and memory
	+	diskstore experiment
		+	values can be large (zset w/ 1 million records)
		+	can cause huge writes to disk to update that entire record on disk