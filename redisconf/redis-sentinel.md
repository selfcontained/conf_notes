# Redis Sentinel

---

Salvatore Sanfilippo

	distributed monitoring and HA for Redis

## What is Sentinel?

+	comes with Redis >=2.4.16
+	notification system
+	automatic failover
+	client configuration server

## Monitoring

+	are my Redis servers up?
+	Are they up from a reasonable point of view?
+	Distributed monitoring
	+	every sentinel can monitor ever master, gain a consensus
	+	place sentinels wherever the clients of Redis are?
+	redis-sentinel is the same binary as redis-server, just acts different if it's called via sentinal
+	when configuring sentinel, can specify (quorum) how many sentinels are a consensus for a master being down
	+	consensus is only required for masters (slave going down doesn't trigger consensus)

## Notifications

+	Pub/Sub channel available (+sdown, -sdown, etc)
+	Can use scripts everytime a worthwhile even is generated

## Automatic Failover

+	O_DOWN state triggered
+	failover sentinel leader is elected and slave selected for new master
	+	best candidate is determined
+	slave promoted to master, other slaves reconfigure accordingly
